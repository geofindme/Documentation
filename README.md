Empower your applications with geofind.me's comprehensive location services. This API documentation provides developers with detailed information on various endpoints that cater to reverse geocoding, place identification, exploring nearby locations, address listing, hydrographic data exploration, and GeoIP analysis.

### Endpoints

- [GeoIP Analysis - /geoip](/endpoint-geoip)
- [Reverse Geocoding - /reverse](/endpoint-reverse)
- [Place Identification - /place](/endpoint-place)
- [Explore Nearby Locations - /near_by](/endpoint-near_by)
- [Address Listing - /list](/endpoint-list)
- [Hydrographic Data Exploration - /hydro](/endpoint-hydro)

### Authentication

To access the geofind.me API, authentication is required using the `X-API-Key` HTTP header. Follow the steps below to include your API key in the request:

#### Obtain an API Key

Before making requests, obtain your unique API key by [registering](https://www.geofind.me/signup) on the geofind.me.

#### Include API Key in Requests

Add the obtained API key to your HTTP requests using the `X-API-Key` header. For example:

```sh
curl -H "X-API-Key: YOUR_API_KEY" "https://api.geofind.me/geoip?ip=8.8.8.8"
```

### Common Types

#### Resolution: Enum

- 0: unspecified
- 1: country
- 2: region
- 3: admin
- 4: city
- 5: locality

#### SortBy: Enum

- 0: unspecified
- 1: by distance
- 2: by importance

#### Summary: Struct

Places returned from geocoding endpoints have `summary` field. This field stores feature indexes its related to.

- `country_code`
- `country`
- `admin`
- `city`
- `locality`

### GeoJSON

The majority of geofind.me API endpoints return responses in GeoJSON format. Therefore, understanding GeoJSON is crucial.

GeoJSON is a format for encoding geographical data structures, primarily used for representing geographic features with their non-spatial attributes. It is based on the JavaScript Object Notation (JSON) standard and is commonly used in web mapping applications. GeoJSON is widely used for exchanging and representing geographic data due to its simplicity, human-readable format, and broad compatibility with web technologies.

#### The GeoJSON Specification (RFC 7946)

In 2015, the Internet Engineering Task Force (IETF), in conjunction with the original specification authors, formed a GeoJSON WG to standardize GeoJSON. [RFC 7946](https://tools.ietf.org/html/rfc7946) was published in August 2016 and is the new standard specification of the GeoJSON format, replacing the 2008 GeoJSON specification.

#### Geometry Types:

- Point: Represents a single geographical point.
- LineString: Represents a sequence of connected points to create a line.
- Polygon: Represents an area defined by a closed loop of coordinates.
- MultiPoint, MultiLineString, MultiPolygon: Represent multiple points, lines, or polygons, respectively.

#### Feature Collection:

GeoJSON can contain a collection of features, each with its own set of properties and geometry.

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [28.9771, 40.8420]
      },
      "properties": {
        "name": "Golden Horn",
        "category": "Bay"
      }
	},
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [125.6, 10.1],
          [125.8, 10.2],
          [126.0, 10.3]
        ]
      },
      "properties": {
        "name": "Route 1",
        "category": "Path"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [125.6, 10.4],
            [125.7, 10.5],
            [125.8, 10.4],
            [125.6, 10.4]
          ]
        ]
      },
      "properties": {
        "name": "Area X",
        "category": "Zone"
      }
    }
  ]
}
```

#### Properties:

Features can have additional attributes, referred to as properties, providing non-spatial information about the feature.

#### CRS (Coordinate Reference System):

GeoJSON supports both "name" and "link" methods for specifying the coordinate reference system.
