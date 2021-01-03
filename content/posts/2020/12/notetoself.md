---
title: "Hugo Self-Docs"
date: 2020-12-28
draft: true
weight: 1
showToc: true
---
# Shortcodes
## Insert an Image
```
figure src= "insert image link here or relative path to image"
```

## Embed a Youtube Video

If the link is https://www.youtube.com/watch?v=w7Ft2ymGmfc, the shortcode will be:
```
youtube w7Ft2ymGmfc
```

## Embed Spotify

```
spotify "insertlasttextofthesharelink"
```

## Embed Audio

Enter this without the quotes:
```
audio "insertrelativepathofaudiofile"
```

## Embed an iFrame

Enter this with quotes:
```
webembed "insertiframesourcelinkhere"
```

## Add a Dropdown

```
collapse summary="Your summary" content="your content"
```

## Embed a Gist

If we want to embed the Gist at the url https://gist.github.com/spf13/7896402:
```
gist spf13 7896402
```

## Embed Instagram Posts

If the link is https://www.instagram.com/p/BWNjjyYFxVx/, the shortcode will be:
```
instagram BWNjjyYFxVx
```

## Embed a Tweet

If the link is https://twitter.com/spf13/status/877500564405444608, the shortcode will be:
```
tweet 877500564405444608
```
# Formatting
## Add a Table

```
|Processor|RAM|Storage|GPU|
|---|---|---|---|
|2.3 GHz Intel i9|16 GB|1 TB|AMD Radeon Pro 5500M|
```
The output will be:
|Processor|RAM|Storage|GPU|
|---|---|---|---|
|2.3 GHz Intel i9|16 GB|1 TB|AMD Radeon Pro 5500M|

## Center an Image
```
|||
||insert image shortcode||
```