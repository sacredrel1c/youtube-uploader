<h1 align="center">Youtube Videos Uploader</h1>

<p align="center">
  <img width="460" height="300" src="assets/youtube.png">

[![npm version](https://img.shields.io/npm/v/youtube-videos-uploader.svg?style=flat)](https://www.npmjs.com/package/youtube-videos-uploader)

**In the name of God, who have guided me to do this work**

**Note1:** In case you find any issue, please raise an [issue](https://github.com/fawazahmed0/youtube-uploader/issues/new/choose), So that I can fix it.<br>
  
Please star this repo by clicking on [:star: button](#) above [:arrow_upper_right:](#)

### Features:
- No upload Limits (50+ videos/day limit set by youtube for every channel)
- Free & Easy to use

### Prerequisite:
- Install [Nodejs](https://nodejs.org/en/)
  
### Installation:
```js
npm i youtube-videos-uploader
```

### Youtube Setup:
1. Go to your [Google Security settings](https://myaccount.google.com/security) and note down your recovery email and delete recovery phone from your google settings
2. Go to your [Youtube settings](https://studio.youtube.com/) and Setup your upload defaults Settings:


![Upload Defaults Settings](assets/defaultsettings.png)
  



### Usage:
- #### Uploading a Video:  

```js

import { upload } from 'youtube-videos-uploader' //Typescript
//or
const { upload } = require('youtube-videos-uploader'); //vanilla javascript

// recoveryemail is optional, only required to bypass login with recovery email if prompted for confirmation
const credentials = { email: 'Your Email', pass: 'Your Password', recoveryemail: 'Your Recovery Email' }

// minimum required options to upload video
const video1 = { path: 'video1.mp4', title: 'title 1', description: 'description 1' }

const onVideoUploadSuccess = (videoUrl) => {
    // ..do something..
}
// Extra options like tags, thumbnail, language, playlist etc
const video2 = { path: 'video2.mp4', title: 'title 2', description: 'description 2', thumbnail:'thumbnail.png', language: 'english', tags: ['video', 'github'], playlist: 'playlist name', onSuccess:onVideoUploadSuccess }


// Returns uploaded video links in array
upload (credentials, [video1, video2]).then(console.log)

// OR
// This package uses Puppeteer, you can also pass Puppeteer launch configuration
upload (credentials, [video1, video2], {headless:false}).then(console.log)

// Refer Puppeteer documentation for more launch configurations like proxy etc
// https://pptr.dev/#?product=Puppeteer&version=main&show=api-puppeteerlaunchoptions
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Output:**
```js
[ 'https://youtu.be/fh2Kreex5Eg', 'https://youtu.be/fh2Krefx5Eg' ]
```
  
- #### Updating Metadata of a Youtube Video:    
  
 ```js

import { update } from 'youtube-videos-uploader' //Typescript
//or
const { update } = require('youtube-videos-uploader'); //vanilla javascript

const videoUpdate1 = { link: 'https://www.youtube.com/watch?v=w3jLJU7DT5E', title: 'Your New Title' }

const onVideoUpdateSuccess = (videoUrl) => {
    // ..do something..
}
// Extra options like tags, thumbnail, language, playlist etc
const videoUpdate2 = { link: 'https://www.youtube.com/watch?v=w3jLJU7DT5E', title: 'title 2', description: 'description 2', thumbnail: 'thumbnail.png', language: 'english', tags: ['video', 'github'], replaceTags: ['mytag'], playlist: 'playlist name', publishType: 'unlisted', onSuccess: onVideoUpdateSuccess }

update(credentials, [videoUpdate1, videoUpdate2]).then(console.log)
// OR
update(credentials, [videoUpdate1, videoUpdate2], { headless: false }).then(console.log)
  
```
  
### Contributors 🎉:
- [Pierre Miniggio( @pierreminiggio )](https://ggio.link/twitter) - For Adding [Youtube UI English Language Support](https://github.com/fawazahmed0/youtube-uploader/pull/16), [JSDoc](https://github.com/fawazahmed0/youtube-uploader/pull/18), and [debug message](https://github.com/fawazahmed0/youtube-uploader/pull/34)
- [TentacleSama4254 ](https://github.com/TentacleSama4254) - For Adding [Thumbnail option](https://github.com/fawazahmed0/youtube-uploader/pull/22), fixing [tags error](https://github.com/fawazahmed0/youtube-uploader/pull/23), [TypeScript Rewrite, storing login session](https://github.com/fawazahmed0/youtube-uploader/pull/51) and [video metadata update feature](https://github.com/fawazahmed0/youtube-uploader/pull/53)
- [Sai Charan](https://github.com/charan0017) - For [onSuccess Option](https://github.com/fawazahmed0/youtube-uploader/pull/32)
- [Tue Nguyen](https://github.com/TueNguyen2911) - For [Better error messages](https://github.com/fawazahmed0/youtube-uploader/pull/46)
- [weizhiqimail](https://github.com/weizhiqimail) - For [Extra Debug messages](https://github.com/fawazahmed0/youtube-uploader/pull/47)
- [DaddyFrosty](https://github.com/DaddyFrosty) - For [Path Escaping](https://github.com/fawazahmed0/youtube-uploader/pull/55)
  
### Support:
You can help support this package by as little as $3, because this package needs regular maintenance<br>
[Support Link](https://fawazahmed0.github.io/donate)

