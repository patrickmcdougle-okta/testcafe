---
layout: docs
title: t.resizeWindowToFitDevice Method
permalink: /documentation/reference/test-api/testcontroller/resizewindowtofitdevice.html
---
# t.resizeWindowToFitDevice Method

Resizes the window to fit the screen of the specified mobile device. Can be chained with other `TestController` methods.

```text
t.resizeWindowToFitDevice(deviceName [, options]) → this | Promise<any>
```

Parameter              | Type   | Description
---------------------- | ------ | -------------------------------------------------------------------------------------------
`deviceName`           | String | The name of the device. See the list of supported devices in [this repository](https://github.com/DevExpress/device-specs/blob/master/viewport-sizes.json).
`options`&#160;*(optional)* | Object | Provide additional information about the device.

The `options` object can contain the following properties.

Property              | Type    | Description
--------------------- | ------- | --------------------------------------------------------------
`portraitOrientation` | Boolean | `true` for portrait screen orientation; `false` for landscape.

> Important! {% include actions/screenshots-prerequisites.md name="`t.resizeWindowToFitDevice`" third-person-singular=true%}

The example below shows how to use the `t.resizeWindowToFitDevice` action.

```js
import { Selector } from 'testcafe';

const header = Selector('#header');

fixture `My fixture`
    .page `http://www.example.com/`;

test('Header is displayed on Xperia Z in portrait', async t => {
    await t
        .resizeWindowToFitDevice('Sony Xperia Z', {
            portraitOrientation: true
        })
        .expect(header.getStyleProperty('display')).notEql('none');
});
```

You can resize window to specified dimensions with [t.resizeWindow](resizewindow.md) method and maximize window with [t.maximizeWindow](maximizewindow.md) method.
