---
title: "DebGPT+text-generation-webuiでVRAM少ないGPUでテキスト生成AIに入門してみる方法(2024年2月時点)"
emoji: "🪔"
type: "tech"
topics: ["Debian", "Linux"]
published: true
---


本記事はDebGPTをきっかけにテキスト生成AIを試してみようと思った人のための記事です。

[ひとりしずかに。- DebGPT+text-generation-webuiでテキスト生成AIに入門してみる方法(2024年2月時点)](https://kenhys.hatenablog.jp/entry/2024/02/19/203943)とのクロスポスト記事です。

[2024/02/17(土)のDebian勉強会(オンライン開催)](https://debianjp.connpass.com/event/309003/)の内容をきっかけにこの記事は執筆されました。

# はじめに

Debian勉強会で、野首さんにより「RAGとLLM そしてDebGPT」というセミナーがありました。

> DebGPTというツールが公開されています。主にDebianのリソース(BTS, buildd等)を参照し、OpenAI APIを経由したChatGPTによる要約、説明といったことが可能です。また、Mistral AI社の公開しているローカル向けLLMにも対応しています。
このツールを実際にローカルで動作させてみるまでのステップや、 内部の挙動の解説、そしてtext-generation-webuiというツールを介して他のLLMを使う手順などを紹介します。

当日の資料は [RAGとLLM そしてDebGPT](https://t.co/MpIALwfqf5)として公開されています。

いわゆる生成AI系はVRAMを大量に積んだGPUを使っている人のためのものという印象が強かったので、
興味がひかれるものの、これまで手をだすことはありませんでした。

現在利用しているPCではGTX 1660なので搭載しているVRAMは6GBと、PCでゲームをしない用途では十分ですが、生成AIを活用するには不向きです。

やれGTX3090がいいとか札束で殴ることで解決できる世界ではありますが、そもそも手持ちのGPUを刷新しようにも、
電源の都合で補助電源8pin x 1の制約があるので、それほど強力なGPUはそもそも積めません。
(補助電源8pin x 1だとRadeonだとRX7600あたりまで、NVIDIAならGTX 3070 or GTX4060あたりまでのはず。)

それでも、最近は混合メモリ方式により、搭載VRAMがすくなくても動作させられるという話を聞いたので試してみることにしました。

# 環境構築をする

本記事では、Debian sid with GTX 1660で環境構築する前提とします。
他の環境では適宜読み替えてください。

* nvidia-driverのインストール (525.147.05-7)
* text-generation-webuiのセットアップ
* LLMのダウンロード
* DebGPTをインストールする

## nvidia-driverのインストール

残念なことに、GPUをフルに活かすには、自由なnouveauドライバではなくプロプライエタリなnvidia-driverを使ったほうが都合がよさそうなので、
nvidia-driverをインストールしておきます。

```
$ sudo apt install -y nvidia-driver
```

すると、nouveauドライバを利用しないように設定がなされます。

```
$ cat /etc/modprobe.d/nvidia-blacklists-nouveau.conf
# You need to run "update-initramfs -u" after editing this file.

# see #580894
blacklist nouveau
```

再起動するとnvidia-driverが使われるようになっているはずです。

nouveauドライバとnvidia driverのパフォーマンスについてはいくつか参考資料があります。
ちょっと古いとはいえまだまだ結構な差をつけられているようです。

* [The Open-Source NVIDIA/Nouveau vs. NVIDIA Linux Driver At The End Of 2019 - Poor But A Lot Of Hope](https://www.phoronix.com/review/nvidia-nouveau-2019/2)
* [Nouveau 2021 Performance on Kepler vs. NVIDIA Linux](https://openbenchmarking.org/result/2106300-IB-NOUVEAU2060)

## text-generation-webuiのセットアップ

テキスト生成AIをWebUI経由で簡単に利用するために、text-generation-webuiのセットアップを行います。

```bash
$ git clone https://github.com/oobabooga/text-generation-webui.git
$ cd text-generation-webui.git
$ ./start_linux.sh
```

途中で環境に関して聞かれるので、適宜選択します。

```bash
What is your GPU?

A) NVIDIA
B) AMD (Linux/MacOS only. Requires ROCm SDK 5.6 on Linux)
C) Apple M Series
D) Intel Arc (IPEX)
N) None (I want to run models in CPU mode)

Input> A

Do you want to use CUDA 11.8 instead of 12.1? Only choose this option if your GPU is very old (Kepler or older).
For RTX and GTX series GPUs, say "N". If unsure, say "N".

Input (Y/N)> N
```

GTX1660なのでTuring世代だから12.1系のCUDAが利用できるはずなので、Nを選択します。

これでinstall_files配下に必要なランタイム等がインストールされます。

もろもろセットアップが終わったら、再度次のようにして./start_linux.shを実行します。

```
$ ./start_linux.sh --api --listen --api-port 5000
```

すると、Web UIは http://localhost:7860 でアクセスでき、生成AIのAPIは http://localhost:5000/v1 としてアクセスできるようになります。

## LLMのダウンロード

LLMを動作させるために、モデルがないとどうしようもないので必要なファイルをダウンロードします。

* http://localhost:7860 にアクセスする
* Modelタブをクリックする
* Download model or LoRAに「TheBloke/Mistral-7B-Instruct-v0.2-GGUF」を入力する
* File name (for GGUF models)に「mistral-7b-instruct-v0.2.Q5_K_M.gguf」を入力する
* Downloadをクリックする

上記により、必要なGGUFファイルがmodel/配下にダウンロードされます。

[mistral-7b-instruct-v0.2.Q5_K_M.gguf](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.2-GGUF] はサイズが大きいものの、品質低下が少ないということで
おすすめとされているモデルです。

速度をとるか、品質をとるかでいくつか異なるモデルが提供されています。

モデルがダウンロードできたら、リフレッシュボタンをクリックするとダウンロードしたモデルが選択できるようになります。
.ggufファイルを選択するとModel loaderにllama.cppが選択されます。

Model loaderにはいくつか挙動をコントロールするためのパラメータがあります。

* n-gpu-layers: GPUを活用するならこの値を増やします。ただしGTX1660(VRAM: 6GB)では9が上限のようです。
* n_batch: バッチ処理する単位を増やして高速化するならこの値を増やします。ただし、GTX1660ではそれほど増やせず530あたりが上限のようです。
* tensorcores: tensor coreを活用するならチェックを有効にします。

ModelのLoadボタンをクリックするとモデルがロードされます。
メモリが足りていなかったり、パラメータが不適切だとあっさり例外を吐きます。

問題なくロードできたら、Chatタブでwho are you?とか入力してみると、応答が返ってくるはずです。

## DebGPTをインストールする

生成AIをAPI経由で叩けるようになったはずなので、次はDebGTPのインストールを行います。

DebGPTはまだtrixie以降でないとパッケージがないため、DebGPT向けのPythonの分離環境をあらかじめ用意したうえで、リポジトリのソースコードを利用します。
あらかじめpyenvが利用できる前提とします。

```bash
$ pyenv install 3.12.2
$ pyenv virtualenv 3.12.2 py312-debgpt
$ pyenv local py312-debgpt
```

```bash
$ git clone https://salsa.debian.org/deeplearning-team/debgpt.git
$ cd debgpt
$ pip3 install .
```

debgptをインストールしたら、設定ファイルを生成します。

```bash
$ debgpt genconfig > $HOME/.debgpt/config.toml
```

次にconfig.tomlのopenai_base_urlを書き換えます。これは先程の text-generation-webuiを利用してローカルで動かしている生成AIのAPIサーバーを参照するための設定です。

```
#openai_base_url = 'https://api.openai.com/v1'
openai_base_url = 'http://localhost:5000/v1'
```

## DebGPTを使ってみる


README.mdに記述されている、メーリングリストの内容を要約してみましょう。

```bash
$ debgpt -HQ --html 'https://lists.debian.org/debian-project/2023/12/msg00029.html' -A :summary
```

`-HQ`でプロンプトを表示せず、レスポンスを受け取ったら終了するようにします。

```bash
[20:14:52] OpenAIFrontend> Starting conversation 19d6f92e-51f9-427d-9955-8267380e3892                                         frontend.py:66
LLM[2]> Mo Zhou has created a new project repo for DebGPT, a Debian-specific LLM (Large Language Model),
at <https://salsa.debian.org/deeplearning-team/debgpt>.
The project does not require expensive hardware or training, and Zhou plans to wrap debian-specific prompts with an existing chatting LLM.
However, Zhou is uncertain about the performance of smaller LLMs in this case and their quantization to int8 or int4 for laptops.
The dependencies needed by the project are not complete in the Debian archive. Zhou invites interested people to discuss the project in the repo issues.
```


元のHTMLの内容が以下の通りなので、情報欠落しているとはいえ、それっぽく要約してくれるとはいえそうです。

```
On 12/30/23 21:40, Mo Zhou wrote:

> >   I am not
> >   able to develop DebGPT and confess I am not investing my time in
> >   learning to do it.  But can we attract the people who want to tinker in
> >   this direction?

> Debian funds should be able to cover the hardware requirement and training expenses even if they are slightly expensive. The more expensive thing is the time of domain experts. I can train such a model but clearly I do not have bandwidth for that.

No. I changed my mind.

I can actually quickly wrap some debian-specific prompts with an existing chatting LLM. This is easy and does not need expensive hardware (although it may still require 1~2 GPUs with 24GB memory for inference), nor any training procedure.
The project repo is created here https://salsa.debian.org/deeplearning-team/debgpt
I have enabled issues. And maybe people interested in this can redirect the detailed discussions to the repo issues.
I'm sure it is already possible to let LLM read the long policy document, or debhelper man pages for us, and provide some suggestions or patches. The things I'm uncertain is (1) how well a smaller LLM, like 7B or 13B ones can do compared to proprietary LLMs in this case; (2) how well a smaller LLM can be when it is quantized to int8 or even int4 for laptops.
Oh, BTW, the dependencies needed by the project are not complete in debian archive. 
```

# さいごに

本記事は、DebGPT+text-generation-webuiでVRAM少ないGPUでテキスト生成AIに入門してみる方法(2024年2月時点)を紹介しました。

ひとまず英語で試してみましたが、次は日本語で応答を返せるようにしてみたいところです。


この記事はUltimate Hacking Keyboard v2で執筆しました。
