---
layout: default-layout
title: How to enable DPM?
keywords: Dynamsoft Barcode Reader, FAQ, tech basic, enable DPM
description: How to enable DPM?
needAutoGenerateSidebar: false
permalink: /faq/general/how-to-enable-dpm.html
---

## How to enable DPM?

[<< Back to FAQ index](index.md)

To enable DPM, assign the `DPMCRM_GENERAL` enumeration to the `DPMCodeReadingModes` array of the furtherModes interface, as such:

```javascript
await settings = await scanner.getRuntimeSettings();
settings.furtherModes.dpmCodeReadingModes[0] = Dynamsoft.DBR.EnumDPMCodeReadingMode.DPMCRM_GENERAL;
await scanner.updateRuntimeSettings(settings);
```
