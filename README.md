## Leaflet-IIIF

A Leaflet plugin for viewing IIIF images. [See the demo](http://mejackreed.github.io/Leaflet-IIIF/examples/example.html)

Requires [Leaflet.js](http://leafletjs.com/) and [jQuery](http://jquery.com/)

### Examples

 - [Demo using the IIIF Image API](http://mejackreed.github.io/Leaflet-IIIF/examples/example.html)
 - [Demo parsing a IIIF manifest](http://mejackreed.github.io/Leaflet-IIIF/examples/manifest.html)

### Install with Bower

```
$ bower install leaflet-iiif
```

### Quick and easy to get going.

```
var map = L.map('map', {
  center: [0, 0],
  crs: L.CRS.Simple,
  zoom: 0
});

L.tileLayer.iiif('http://example.com/iiifimage.jp2/info.json').addTo(map);
```

### With error handler option (Passing in your own custom function, as below)

```
function errorHandler() {
  $('#viewer').removeClass("not_loaded").height("30px")
     .html("<div class='error'>Sorry, an error occurred while loading the image.</div>");
}

L.tileLayer.iiif('http://example.com/iiifimage.jp2/info.json', {errorHandler: errorHandler}).addTo(map);
```

Thanks to [klokantech/iiifviewer](https://github.com/klokantech/iiifviewer) and [turban/Leaflet.Zoomify](https://github.com/turban/Leaflet.Zoomify) who have similar plugins which were used in development of Leaflet-IIIF.

### Options

Leaflet-IIIF extends [L.TileLayer](http://leafletjs.com/reference.html#tilelayer) and so many options available to L.TileLayer can be used with Leaflet-IIIF.

Option | Type | Default | Description
------ | ---- | ------- | -----------
`tileFormat` | `String` | `'jpg'` | The [format](http://iiif.io/api/image/2.0/#format) of the returned image.
`tileSize` | Number | 256 | Tile size (width and height in pixels, assuming tiles are square).
`fitBounds` | Boolean | true | Automatically center and fit the maps bounds to the added IIIF layer
`quality` | String | 'default' | [determines whether the image is delivered in color, grayscale or black and white](http://iiif.io/api/image/2.0/#quality) _Note:_ All IIIF servers do not support this parameter.
`errorHandler` | Function | undefined | Pass a function reference to execute when ajax requests succeed, but the returned data element is empty or undefined.

### Development

Clone the repository

```
$ git clone https://github.com/mejackreed/Leaflet-IIIF.git
```

Install the dependencies

```
$ npm install
```

Run the server

```
$ npm start
```

Access the examples at http://127.0.0.1:8080/examples/example.html

### Leaflet-IIIF Examples

 - [Leaflet-IIIF Basic Example](http://bl.ocks.org/mejackreed/b0aba2ff6f5a54f197767313fbc5a26e)
 - [Leaflet-IIIF Side by Side using IIIF Quality](http://bl.ocks.org/mejackreed/80c4248278517475a30190b427cb5c9c)
 - [Leaflet-IIIF Martellus Map example using IconLayers plugin](http://bl.ocks.org/mejackreed/6e3fb8e69189dadb4be7d0926a6a14a5)
 - [Leaflet-IIIF Magnifying Glass Example](http://bl.ocks.org/mejackreed/f3904b28bb99abea32951f04ce6eb4cd)
 - [Leaflet-IIIF Draw example](http://bl.ocks.org/mejackreed/462e89092ce71ae7dd09e6074d60f2e0)
 - [Leaflet-IIIF Labels example](http://bl.ocks.org/mejackreed/68092c44c95ef31fefcfe6f683116f77)
 - [Leaflet-IIIF Annotation Example](http://bl.ocks.org/mejackreed/2724146adfe91233c74120b9056fba06)

### Leaflet-IIIF in the wild

Princeton Libraries used Leaflet-IIIF for its ["Plan of Versailles"](Plan of Versailles) map. This implementation uses GeoJSON annotation to annotate the map being served out by a IIIF server.

[http://rbsc.princeton.edu/versailles/map](http://rbsc.princeton.edu/versailles/map)