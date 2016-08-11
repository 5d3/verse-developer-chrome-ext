# Verse Developer Chrome extension

Verse Developer Chrome Extension is a tool for developers of IBM Verse Widgets. The Chrome extension allows you to register your widget in Verse locally as you develop it. Widgets registered with the Extension are available only on the developers' computers, with the Google Chrome browser, and cannot be accessed from other devices.

## What's Here
- How to get started with the chrome extension
- How to register a widget


## Getting Started with the Chrome Extension
- Open extensions tab in chrome i.e. `chrome://extensions/`
- Turn on `Developer mode`
- Select `Load unpacked extension...` in Chrome
![Getting Started with the Chrome Extension](/demo/img/rm_01_01_700.png)
- Choose the src folder in your local copy of this repository
![Load Unpacked Extension](/demo/img/rm_01_02_700.png)
- The extension contains the definition of some sample widgets, follow the instructions in the [Documentation][1] to set up the samples. There are currently three samples provided:
  * [Add an action contribution to the business card view][2]
  * [Add an action contribution to the mail compose view][3]
  * [Add an action contribution to the mail read view][4]

## How to Register a Widget
The project contains a manifest file `src\widget.json` (copied below). This file contains a sample widget registration for the person action. It will add an action button at the back of the bizcard.
![Person Action in BizCard](demo/img/bizcard_action.png)

```
[
  {
    "app_id": "com.ibm.verselabs.actions.sample",
    "name": "Person Sample",
    "url": "https://yourcompany/personSample.html",

    "extensions": [
      {
        "type": "com.ibm.verse.action",
        "ext_id": "com.ibm.verselabs.action.sample.person",
        "name": "Person Action Sample",
        "payload": {},
        "object": "person",
        "title": "Person Action"
      }
    ],

    "payload": {
      "features": [
        "core"
      ],
      "preferences": [
        {
          "name": "searchFor",
          "value": "profile.primaryEmail"
        }
      ],
      "renderParams": {
        "width": "900",
        "height": "500"
      }
    },

    "services": [
      "Verse"
    ]
  }
]
```
You need to change the value of the `url` property to point to your web application. We have provided you with a [sample HTML][5] in the [Documentation][1] for you to try out.

The `widget.json` can contain the definition of multiple widgets. For a list of properties contained in each widget. See [Working with the manifest file][6] section in our [Documentation][1].

To learn more about Verse Developer Chrome Extension, check out the [documentation][1].

*Source for documentation is available in the `gh-pages` branch of this repository*

The Verse Developer Chrome extension is © 2016 under the terms of the MIT License.

[1]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/
[2]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/tutorials/business_card.html
[3]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/tutorials/mail.compose.html
[4]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/tutorials/mail.read.html
[5]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/tutorials/sample-html.html
[6]: https://git.swg.usma.ibm.com/pages/IBM-Verse/verse-developer-chrome-ext/tutorials/ext-manifest.html
