[![Build Status](https://jenkins.flowingcode.com/job/GoogleMaps-14-addon/badge/icon)](https://jenkins.flowingcode.com/job/GoogleMaps-14-addon)

# Google Maps Add-on

Vaadin 14+ addon for Google Maps Web Component

## Features

* Programmatic server-side panning and zooming
* Adding/removing markers
* Adding/removing polygons  

## Online demo

[Online demo here](http://addonsv14.flowingcode.com/googlemaps)

## Download release

[Available in Vaadin Directory](https://vaadin.com/directory/component/google-maps-addon)

## Building and running demo

- git clone repository
- mvn clean install jetty:run

To see the demo, navigate to http://localhost:8080/

## Release notes

See [here](https://github.com/FlowingCode/GoogleMapsAddon/releases)

## Issue tracking

The issues for this add-on are tracked on its github.com page. All bug reports and feature requests are appreciated. 

## Contributions

Contributions are welcome, but there are no guarantees that they are accepted as such. Process for contributing is the following:

- Fork this project
- Create an issue to this project about the contribution (bug or feature) if there is no such issue about it already. Try to keep the scope minimal.
- Develop and test the fix or functionality carefully. Only include minimum amount of code needed to fix the issue.
- Refer to the fixed issue in commit
- Send a pull request for the original project
- Comment on the original issue that you have implemented a fix for it

## License & Author

Add-on is distributed under Apache License 2.0. For license terms, see LICENSE.txt.

GoogleMapsAddon is written by Flowing Code S.A.

# Developer Guide

## Getting started

Create an instance of GoogleMap, configure it, add markers, polygons, etc:
```
            GoogleMap gmaps = new GoogleMap(apiKey,null,null);
            gmaps.setMapType(MapType.SATELLITE);
            gmaps.setSizeFull();
            gmaps.setCenter(new LatLon(0,0));
            gmaps.addMarker("Center", new LatLon(0,0), true, "");
            GoogleMapPolygon gmp = gmaps.addPolygon(Arrays.asList(new GoogleMapPoint(gmaps.getCenter()),
            new GoogleMapPoint(gmaps.getCenter().getLat(),gmaps.getCenter().getLon()+1),
            new GoogleMapPoint(gmaps.getCenter().getLat()+1,gmaps.getCenter().getLon())));
            gmp.addClickListener(ev->Notification.show("polygon clicked"));
```