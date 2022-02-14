# RichMarker

![image-1](https://user-images.githubusercontent.com/31973579/153803043-432b47d9-deea-4142-897a-039904e0ff6d.jpg)

![image-2](https://user-images.githubusercontent.com/31973579/153803073-4d1f2730-cbaa-4d24-a72f-567180890087.jpg)

![image-3](https://user-images.githubusercontent.com/31973579/153803080-d0b311bf-23c5-416a-9cd5-461affe8396c.jpg)

# Introduction
The RichMarker is a plugin for Google Maps ready to be used on mobile and desktop devices. It supports HTML CSS JS Markers and Info Windows. Info Windows with IntelliSense builds to be opened on the appropriate aria available on the Map and are sticky on the Map. RichMarker and Info Windows have various events handlers, pre-built default styles, options, and features. k-means clustering is in progress and will be available soon. 

# Features
- Five default Markers and Three Info Windows styles.
- HTML Marker and HTML Info Windows.
- Animations support.
- Sticky Info Windows on the Map.
- IntelliSense builds for Info Windows.
- Info Windows with Sliders.
- Pure Javascript (no jQuery).
- Touch Support.
- Javascript options.
- Custom Callbacks and Event Handlers.
- Well documented.
- k-means clustering (in progress).

# Installation

**For Commonjs & ESModules:**

```js
// in commonjs & ESModules
import RichMap from "./RichMap.js";
// or
// in commonjs
const RichMap = require("./RichMap.js");
```

**In Plain Javascript:**

```html
<!-- in html file -->
<head>
  ...
  <script src="./RichMap.js"></script>
  ...
</head>
<body>
  ...
  <script type="text/javascript">
    // code
  </script>
</body>
```

# Use

```html
<!-- in html file -->
<head>
  ...
  <style>
    .google-maps {
      width: 100%;
      height: 100%;
    }
  </style>
</head>
<body>
  <div id="map" class="google-maps"></div>
  ...
  ...
  <script>
    // script function
    function getScriptTag(src) {
      const script = document.createElement('script');
      script.setAttribute("type", "module");
      script.src = src;
      return script;
    }
    // intialize the map
    function initMap() {
      const script = getScriptTag("./src/index.js");
      document.head.appendChild(script);
    };
    window.initMap = initMap;
  </script>

    <!-- Load the Google Maps Library Now. -->
    <script
      src="https://maps.googleapis.com/maps/api/js?key=(your-key)&callback=initMap&libraries=&v=weekly"
      defer="defer">
    </script>
</body>
```

**In (index.js) file:**

```js
// get the map div
const mapDiv = document.getElementById("map");

// initalize the map in the div
const initMap = () => {
  const myLatLng = { lat: 8.016, lng: 133.153 };
  const map = new google.maps.Map(mapDiv, {
    zoom: 3,
    center: myLatLng,
    disableDefaultUI: true,
  });
  window.map = map;
};

// call the initMap function
initMap();

// initalize the rich map plugin
const richMap = new RichMap({
  map
});

// add html marker
const richMarker = richMap.addMarker({
  domElement: richMap.getMarker("style-1"),
  LatLng: { lat: -25.363, lng: 131.044 },
  position: "bottomCenter"
});

// add html info window
const richInfoWindow = richMarker.addInfoWindow({
  domElement: richMap.getInfoWindow("style-1"),
  offset: "10px"
});

// Event Listener for the richMarker
richMarker.addEventListener("click", e => {
  //console.log(e);
});
richMarker.addEventListener("mouseenter", e => {
  //console.log(e);
});
richMarker.addEventListener("mouseleave", e => {
  //console.log(e);
});

// Event Listener for the richInfoWindow
richInfoWindow.addEventListener("click", e => {
  //console.log(e);
});
richInfoWindow.addEventListener("mouseenter", e => {
  //console.log(e);
});
richInfoWindow.addEventListener("mouseleave", e => {
  //console.log(e);
});
```



Rich Map library for google maps with HTML markers and info windows + k-means clustering



## [Click Here to See Live Demo](https://sllujaan.github.io/RichMarker/)🚀
