# Screen capture and sharing

This repo is an exploration of screen capture in browsers.

You can read about these examples on the Blog:

- [Screen capture in Google Chrome](https://www.twilio.com/blog/2017/10/screen-capture-in-google-chrome.html)

## Chrome extension

In the `/extension` directory is a minimal implementation of a Chrome extension that will give access to streams from the [`chrome.desktopCapture` API](https://developer.chrome.com/extensions/desktopCapture).

## Screen capture in Chrome

In the `/chrome` directory is an HTML page that takes advantage of the extension and captures the desktop to show within a `<video>` element on the page.

### _Note_

You will need to load your own version of the Chrome extension into your browser and replace `YOUR_EXTENSION_ID_HERE` with your own extension ID.

You will also need to serve the file from a local web server so that you can visit it on localhost.

### _Production Note_

If you wish to deploy the Chrome extension to the Chrome web store you will need to update the extension's `manifest.json` to include your own site's URL in the `externally_connectable.matches` key. You can add more than one URL as this is an array. For example:

```json
  "externally_connectable": {
    "matches": ["*://localhost/*", "https://yourdomain.com/*"]
  },
```