# nuxeo-googlemap-elements

Allows for displaying a Google Map, with 0-n markers, handling a click on markers, etc.


# Usage

1. In Nuxeo Studio Designer, "Resources", import the `nuxeo-google-map` folder and its elements, `nuxeo-google-map.html` and `nuxeo-google-maps-api.html`
2. In a custom element using them:
  * Import `nuxeo-google-map.html`, according to its path in your configuration
  * For example, `<link rel="import" href="nuxeo-google-map/nuxeo-google-map.html">`
3. It is required to give a height to the element, in the `<style>` part. Then, use the element and set its different values. For example, with an existing `geloc` schema:

```
<link rel="import" href="nuxeo-google-map/nuxeo-google-map.html">
<dom-module id="my-element">
  <template>
    <style>
	  nuxeo-google-map {
		height: 500px; /* Settings the height is a requirement */
	  }
    </style
	<nuxeo-google-map
      id="gmap"
      latitude="[[document.properties.geoloc:latitude]]"
      longitude="[[document.properties.geoloc:longitude]]"
      zoom="10"
      api-key="your-API-key"
      markers="[[markers]]"
      fit-to-markers>
   </nuxeo-google-map>
 </template>
. . .
```

Please, see the explanations in nuxeo-google-map.html for details about the markers.


# Support

**These features are not part of the Nuxeo Production platform, they are not supported**

These solutions are provided for inspiration and we encourage customers to use them as code samples and learning resources.

This is a moving project (no API maintenance, no deprecation process, etc.) If any of these solutions are found to be useful for the Nuxeo Platform in general, they will be integrated directly into the platform, not maintained here.

# Licensing

[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)

# About Nuxeo

Nuxeo dramatically improves how content-based applications are built, managed and deployed, making customers more agile, innovative and successful. Nuxeo provides a next generation, enterprise ready platform for building traditional and cutting-edge content-oriented applications. Combining a powerful application development environment with SaaS-based tools and a modular architecture, the Nuxeo Platform and Products provide clear business value to some of the most recognizable brands including Verizon, Electronic Arts, Sharp, FICO, the U.S. Navy, and Boeing. Nuxeo is headquartered in New York and Paris.

More information is available at [www.nuxeo.com](http://www.nuxeo.com).  
