# ✆ Click-to-Call WebComponent

<p>
    <img src="https://user-images.githubusercontent.com/29258951/73121083-687dff00-3f76-11ea-8d89-cf8b53863c54.jpg">
</p>

[![Strict TypeScript Checked](https://badgen.net/badge/TS/Strict 'Strict TypeScript Checked')](https://www.typescriptlang.org)
[![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/cubase/call-to-webrtc.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/cubase/call-to-webrtc/context:javascript)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat)](https://github.com/cubase/call-to-webrtc/blob/master/LICENSE.md)

## What is Click-to-Call?

The definition of click-to-call (which is sometimes called click-to-talk, or click-to-text) refers to a type of digital communication in which a person clicks a button or text in order to be connected with another individual in real-time. These connections can occur via phone call, SMS or Voice-over-Internet-Protocol (VoIP). These click-to-call links are commonly found as buttons on websites. But often, click-to-call can be initiated by hyperlinks over emails and videos.

[**More informations**](https://www.ringdna.com/inside-sales-glossary/what-is-click-to-call)

## List of used technologies

- [Preact + preact-custom-element](https://github.com/preactjs/preact)
- [TypeScript](https://github.com/microsoft/TypeScript)
- [JsSIP](https://github.com/versatica/JsSIP)
- [Rollup](https://github.com/rollup/rollup)

## Getting started

After `npm install` run:

```
npm run dev
```

Development server serves `index.html` file in root direactory

> Note: Rollup automatically takes care about
> hot reloading after source files change.

## Production build

Production build is generated using:

```
npm run build
```

into `dist/ctc.min.js`.

## Using on webpage

After project is built paste this code snippet into website `<head />` tag:

> **View** `index.html`

```
<script
      async
      defer
      src="dist/ctc.min.js"
      data-uri="sip:<USERNAME>@<PBX_URL>"
      data-user="<USERNAME>"
      data-password="<PASSWORD>"
      data-socket="wss://<PBX_WEBSOCKET_URL>"
      data-callto="sip:<NUMBER_TO_CALL>@<PBX_URL>"
      <!-- data-color="green"  -->  Custom color
      <!-- data-position="left"  -->  Custom position ('right' is default)
      <!-- data-text="Call us!"  -->  Custom bubble text
>
</script>
```
> **Do not forget**: Update `src` path if you will be using different folder structure!


#### `c2c` API
You can initialize Click-To-Call button on your own.
##### c2c.init([config])
```
c2c.init({
    uri: 'sip:myusername@<pbx.hostname.com>',
    user: 'myusername',
    password: 'mypassword',
    socket: 'wss://pbx.websockethostname.com',
    callto: 'sip:callto@<pbx.hostname.com>',
    color: 'green',
    position: 'left',
    text: 'Call us!'
})
```


## Customizing automatic run

Current version is developed with running script immediately after its load if script contains required `data-` attributes. You can modify this behavior in `src/click-to-call.ts` file.

## License

[MIT](https://github.com/cubase/call-to-webrtc/blob/master/LICENSE.md)
