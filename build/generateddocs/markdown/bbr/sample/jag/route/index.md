
# Route (Schema)

`iso.bbr.sample.jag.route` *v0.1*

A route: a road or path, described as a feature with a length in metres and a line geometry.

[*Status*](http://www.opengis.net/def/status): Under development

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Route
description: A route is a GeoJSON feature with a MultiLineString geometry and a length
  in metres.
type: object
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
- properties:
    geometry:
      properties:
        type:
          const: MultiLineString
    properties:
      type: object
      required:
      - length
      properties:
        length:
          type: number
          exclusiveMinimum: 0
          description: Length of the route, in metres.
        name:
          type: string
          description: Human-readable name of the route.
  required:
  - geometry
  - properties
x-bblocks-metadata:
  itemIdentifier: iso.bbr.sample.jag.route
  register: https://avillar.github.io/bblocks-nov10-jag/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-10-29'

```

Links to the schema:

* YAML version: [schema.yaml](https://avillar.github.io/bblocks-nov10-jag/build/annotated/bbr/sample/jag/route/schema.json)
* JSON version: [schema.json](https://avillar.github.io/bblocks-nov10-jag/build/annotated/bbr/sample/jag/route/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:geometry"
    },
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://avillar.github.io/bblocks-nov10-jag/build/annotated/bbr/sample/jag/route/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/avillar/bblocks-nov10-jag](https://github.com/avillar/bblocks-nov10-jag)
* Path: `_sources/route`

