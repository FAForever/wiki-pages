---
title: Theming
description: Change how the client looks
published: true
date: 2022-06-15T14:28:26.996Z
tags: client
editor: markdown
dateCreated: 2021-11-07T18:14:37.054Z
---

## Structure of a theme
A theme is a folder in the `C:\ProgramData\FAForever\themes` directory. You can call the folder for your theme whatever you like. The important info is taken from the theme.properties file in the root directory. Also in the folder can be images, fxml files and css stylesheets.

### The theme.properties

Looks like that:

```
displayName=test
author=alex
compatibilityVersion=1
themeVersion=1
```
The values are pretty self explanatory. At the moment only displayName is actually used. You still need the other values. Also make sure the versions are whole numbers.

### Selecting a theme

After restarting the client and putting the theme folder in the `C:\ProgramData\FAForever\themes` directory, a user should be able to select the theme in a dropdown in the settings. Selected style changes are immediately loaded, although changes to images and fxml files might only take effect after a restart.

## The different files

You can change the following.

1. Style via css files
2. Images by providing them
3. FXML files (they are similar to HMTL) that define the layout If a file is not in your theme the client will use the default ones as a fallback. So try to only provide files you really changed. This increases compatibility with future versions. All this files from `src/main/resources/theme` in the client can be overwritten with your own.

[That's](https://github.com/FAForever/downlords-faf-client/tree/develop/src/main/resources/theme) where you can find files that can be overwritten.