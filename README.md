# dart_shp

A port to dart of some portions of the http://www.geotools.org shapefile plugin.

At the moment dbf read/write and shapefile reading works.

```dart
  // example
  File shpFile = File('assets/test.shp');
  final list = <Map<String, dynamic>>[];
  final reader = ShapefileFeatureReader(shpFile);
  reader.open().then((value) async {
    bool hasNext = await reader.hasNext();
    while (hasNext)
    {
      final feature = await reader.next();
      list.add(feature)
      hasNext = await reader.hasNext();
    }
    print('size===${list.length}');
  });
```
