Note: This is a fork of the SimpleImage repository. It adds in extra functionality such as a toolbar to add images (rather than just drag and drop) and uses blob URL's
to improve memory usage.

This can also be used to display a timestamped image and a play button to play from that timestamp.

# Simple Image Tool

Provides Image Blocks for the [Editor.js](https://editorjs.io).

Works only with pasted image URLs and requires no server-side uploader.

![](assets/image-uploading.gif)

## Installation

### Install via NPM

Get the package

```shell
npm i --save-dev simple-image-editorjs
```

Include module at your application

```javascript
const SimpleImage = require('simple-image-editorjs');
```

### Download to your project's source dir

1. Upload folder `dist` from repository
2. Add `dist/bundle.js` file to your page.

### Load from CDN

You can load specific version of package from [jsDelivr CDN](https://cdn.jsdelivr.net/gh/shanku007/simple-image-with-timestamp/dist/bundle.min.js).

`https://cdn.jsdelivr.net/gh/shanku007/simple-image-with-timestamp/dist/bundle.min.js`

Then require this script on page with Editor.js.

```html
<script src="..."></script>
```

## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...
  
  tools: {
    ...
    image: SimpleImage,
    config: {
            onPlayClick: (timeStamp) => { //The function to handle play button click
              console.log(timeStamp);
            },
          }
  }
  
  ...
});
```

## Config Params

1. onPlayClick

## Tool's settings

![](https://capella.pics/c74cdeec-3405-48ac-a960-f784188cf9b4.jpg)

1. Add border

2. Stretch to full-width

3. Add background

## Output data

| Field          | Type      | Description                     |
| -------------- | --------- | ------------------------------- |
| url            | `string`  | image's url                     |
| caption        | `string`  | image's caption                 |
| withBorder     | `boolean` | add border to image             |
| withBackground | `boolean` | need to add background          |
| stretched      | `boolean` | stretch image to screen's width |
| timeStamp      | `string`  | The timestamp for the image     |


```json
{
    "type" : "image",
    "data" : {
        "url" : "https://www.tesla.com/tesla_theme/assets/img/_vehicle_redesign/roadster_and_semi/roadster/hero.jpg",
        "caption" : "Roadster // tesla.com",
        "withBorder" : false,
        "withBackground" : false,
        "stretched" : true,
        "timeStamp": "164"
    }
}
```
