---
title: Client Theming
description: 
published: true
date: 2023-01-21T19:20:14.525Z
tags: 
editor: markdown
dateCreated: 2023-01-21T19:20:14.525Z
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

### CSS

Java FX uses CSS to style the application. Be aware that it uses special properties, that can be found in the java fx [documentation](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/doc-files/cssref.html). You probably want to make changes to the `style.css` file found in `src/main/resources/theme`. You can either provide that very file or better provide the `style_extension.css` and overwrite values from `style.css` there. The later version increases compatibility with future versions.

### Images
Are in `images/*` just provide your own.

### FXML Files

Try to avoid changing fxml files. This might make your theme fragile. Rather try to give certain items styleclasses. We are happy to accept Pull Requests that simply add styleclasses. You can then style them in the css. Although if you want major changes to layout that is a valid strategy. The fxml files still need to fit on their Controllers though. That would be something for an advanced theme.

## Example

[Here](https://github.com/FAForever/downlords-faf-client/files/4967300/Alex.zip) is a simple theme that sets accent color to green.

### Replacing the loading gif for ladder
If you wanted to replace the loading gif that is showing while searching for ladder you just need to replace the gif. The default gif is found in images/ladder_loading.gif (since v1.2.1). Put another gif file in your theme folder under the images directory. Also you need the theme.properties in your root directory.

## Development
You should probably have a look at the original files. And here a little tip: The client refreshes the stylesheets on the fly if you change them.

![85212411-b0048d80-b352-11ea-8a0f-71846316f420.gif](/images/client-icons/85212411-b0048d80-b352-11ea-8a0f-71846316f420.gif)