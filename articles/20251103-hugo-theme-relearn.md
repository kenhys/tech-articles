# Migrating from hugo-theme-learn to alternative theme

## Introduction

For personal web site, I use hugo and hugo-theme-learn for statically generated contents.

Recently I've noticed that these combination of specific version is not compatible with.

(Not so frequently update contents, so it was delayed to found this situation)

## What was the actual error?


```
ERROR deprecated: .Site.IsMultiLingual was deprecated in Hugo v0.124.0 and subsequently removed. Use hugo.IsMultilingual instead.
Total in 21 ms
```

It seems that hugo-theme-learn is not compatible with recent Hugo anymore.

## How to deal with it?

With checking upstream issue, I've found the following issue.

[What are people migrating too?](https://github.com/matcornic/hugo-theme-learn/issues/557)

'hugo-theme-relearn' was noted as an alternative.

As 'hugo-theme-learn' is not actively maintained anymore, so it is easy to migrate from hugo-theme-learn to hugo-theme-relearn.

For example, it needs just a few lines of configuration.

```toml
diff --git a/website/config.toml b/website/config.toml
index 702d4da..99ddf03 100644
--- a/website/config.toml
+++ b/website/config.toml
@@ -3,7 +3,7 @@ languageCode = "en-US"
 defaultContentLanguage = "en"

-theme = "hugo-theme-learn"
+theme = "hugo-theme-relearn"
 themesdir = "themes"
 metaDataFormat = "yaml"
 defaultContentLanguageInSubdir= true
@@ -16,6 +16,7 @@ defaultContentLanguageInSubdir= true
   disableNextPrev = true
   disableSearch = true
   disableShortcutsTitle = true
+  themeVariant = 'learn'

 [markup]
   [markup.goldmark]
```


It was sad that hugo-theme-learn is not maintained actively, but many thank to this greateful hugo theme.
And also thanks the effort to fork it as hugo-theme-relearn.
