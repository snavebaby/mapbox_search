# mapbox_search

[![Pub](https://img.shields.io/pub/v/mapbox_search)](https://pub.dartlang.org/packages/mapbox_search)

# MapBox Search and Static Image pure Dart Implementation

#### A Flutter package for place search using MapBox Api and for Static map image

### I made this package because google place search was not working that much efficently(daily quota limit) and MapBox offers plenty of free search rerquests.

### Way more useful than google if you want staitic map images

## Installing

Add the following to your `pubspec.yaml` file:

    dependencies:
      mapbox_search: any

# Example

## Static Image

    MapBoxStaticImage staticImage = MapBoxStaticImage(
        apiKey:
            "API Key");

### Image With Polyline

    String getStaticImageWithPolyline() => staticImage.getStaticUrlWithPolyline(
      point1: Location(lat: 37.77343, lng: -122.46589),
      point2: Location(lat: 37.75965, lng: -122.42816),
      marker1: MapBoxMarker( markerColor: Colors.black, markerLetter: 'p', markerSize: MarkerSize.LARGE),
      msrker2: MapBoxMarker(
          markerColor: Colors.redAccent,
          markerLetter: 'q',
          markerSize: MarkerSize.SMALL),
      height: 300,
      width: 600,
      zoomLevel: 16,
      style: MapBoxStyle.Mapbox_Dark,
      path: MapBoxPath(pathColor: Colors.red, pathOpacity: 0.5,     pathWidth: 5),
      render2x: true);
    

### Image with Marker

    String getStaticImageWithMarker() => staticImage.getStaticUrlWithMarker(
      center: Location(lat: 37.77343, lng: -122.46589),
      marker: MapBoxMarker(
          markerColor: Colors.black, markerLetter: 'p', markerSize: MarkerSize.LARGE),
      height: 300,
      width: 600,
      zoomLevel: 16,
      style: MapBoxStyle.Mapbox_Streets,
      render2x: true,
    );
  

### Image without Marker

    String getStaticImageWithoutMarker() => staticImage.getStaticUrlWithoutMarker(
        center: Location(lat: 37.75965, lng: -122.42816),
        height: 300,
        width: 600,
        zoomLevel: 16,
        style: MapBoxStyle.Mapbox_Outdoors,
        render2x: true,
      );


## Search Widget

    MapBoxPlaceSearchWidget(
          popOnSelect: true,
          apiKey:
              "API KEY",
          limit: 10,
          onSelected: (place) {},
          context: context,
    )