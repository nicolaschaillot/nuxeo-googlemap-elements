# nuxeo-googlemap-elements

<hr>

**THIS WORK IN PROGRESS => DO NOT USE, IT'S NOT WORKING YET :-)**

<hr>

This plugin for [Nuxeo Platform](http://www.nuxeo.com) allows for deploying the [`google-map` Google Web Component](https://www.webcomponents.org/element/GoogleWebComponents/google-map) in Nuxeo Web UI, making it easy to display a GoogleMap with markers, etc.

[![Build Status](https://qa.nuxeo.org/jenkins/buildStatus/icon?job=Sandbox/sandbox_nuxeo-googlemap-elements-master)](https://qa.nuxeo.org/jenkins/view/Sandbox/job/Sandbox/job/sandbox_nuxeo-nuxeo-googlemap-elements-master/)


# Usage

1. Install the `nuxeo-googlemap-elements` marketplace package in your Nuxeo Server:
  * `google-map`, `google-apis` and their dependencies will be deployed in the  `ui/bower_components` folder
2. Your elements can now use the `google-map` element (and its `google-map-marker` and other elements). This requires to explicitly import them from the `bower_components`  folder.

For example, with a ui folder organized like this...

```
ui
  bower_components
  . . .
  document
    mydoc
      . . .
      nuxeo-mydoc-view-layout.html
  . . .
```

... you would use the Google Map component like:

```
<!-- from ui/mydoc/nuxeo-mydoc-view-layout.html
       to ui/bower_components/google-map/google-map.html -->
<link rel="import" href="../../bower_components/google-map/google-map.html">
<dom-module id="nuxeo-mydoc-view-layout">
  <template>
    <style>
      . . .
      google-map {
        height: 500px;
      }
    </style>

    <google-map
        latitude="[[latitude]]"
        longitude="[[longitude]]"
        zoom="11"
        api-key="[[apiKey]]"
        fit-to-marker>
      <google-map-marker latitude="[[latitude]]" longitude="[[longitude]]"
            title="[[title1]]"></google-map-marker>
    </google-map>
    . . .
```
`apiKey`, `latitude` and `longitude` could be properties, functions, ... whatever is best in your context. For example, they could be fields:

```
<google-map
    latitude="[[document.propertties.geoloc:latitude]]"
    longitude="[[document.propertties.geoloc:longitude]]"
    . . .
```


# Build

```
git clone https://github.com/nuxeo-sandbox/nuxeo-googlemap-elements.git
cd nuxeo-googlemap-elements
mvn clean install
```

# Support

**These features are not part of the Nuxeo Production platform, they are not supported**

These solutions are provided for inspiration and we encourage customers to use them as code samples and learning resources.

This is a moving project (no API maintenance, no deprecation process, etc.) If any of these solutions are found to be useful for the Nuxeo Platform in general, they will be integrated directly into the platform, not maintained here.

# Licensing

[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)

# About Nuxeo

Nuxeo dramatically improves how content-based applications are built, managed and deployed, making customers more agile, innovative and successful. Nuxeo provides a next generation, enterprise ready platform for building traditional and cutting-edge content-oriented applications. Combining a powerful application development environment with SaaS-based tools and a modular architecture, the Nuxeo Platform and Products provide clear business value to some of the most recognizable brands including Verizon, Electronic Arts, Sharp, FICO, the U.S. Navy, and Boeing. Nuxeo is headquartered in New York and Paris.

More information is available at [www.nuxeo.com](http://www.nuxeo.com).  
