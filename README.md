[![Build Status](https://travis-ci.com/terrestris/mapfish-print-manager.svg?branch=master)](https://travis-ci.com/terrestris/mapfish-print-manager) [![Greenkeeper badge](https://badges.greenkeeper.io/terrestris/mapfish-print-manager.svg)](https://greenkeeper.io/)

# Mapfish Print Manager

An interface manager to easily communicate with the MapFish Print module via
an [OpenLayers](https://openlayers.org/) based webapplication.

# Installation

If you're using OpenLayers in version 5 just run:

```
npm i --save @terrestris/mapfish-print-manager
```

For version 4 one might use the manager in version 1:

```
npm i --save @terrestris/mapfish-print-manager@1
```

# Usage

```
// Import the manager. If you're using MapFish in version 2, you might want to
// import the `MapFishPrintV2Manager` instead.
import { MapFishPrintV3Manager } from '@terrestris/mapfish-print-manager';

// Construct the manager with a remote print servlet and an `ol.Map` instance
// (required).
const printManager = new MapFishPrintV3Manager({
  url: 'https://10.10.10.10/print/',
  map: olMap
});

// Initialize the manager. It will return a resolved `Promise` as soon as the
// capabilities are loaded from the given ressource, e.g. https://10.10.10.10/print/info.json.
printManager.init()
  .then(() => {
    // Prepare the print layout via the extent feature on the map and/or the
    // usage of the setters like `printManager.setLayout()` and call
    // `printManager.print()` to create the print document.
  });
```