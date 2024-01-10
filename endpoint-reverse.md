## /reverse

The `/reverse` endpoint of geofind.me provides reverse geocoding, allowing you to obtain address information based on geographical coordinates.

### Endpoint

```http
GET /reverse?lat={latitude}&lon={longitude}&accept_language={language}&normalize_address_names={true/false}&include_names={true/false}&include_extra_tags={true/false}&include_geometry={true/false}
```

- `lat` (required): Latitude coordinate.
- `lon` (required): Longitude coordinate.
- `accept_language` (optional): Preferred language for address names.
- `normalize_address_names` (optional): Normalize address names (true/false, default is false).
- `include_names` (optional): Include various names in the response (true/false, default is false).
- `include_extra_tags` (optional): Include extra tags in the response (true/false, default is false).
- `include_geometry` (optional): Include geometry information in the response (true/false, default is false).

#### Example Request

```http
GET /reverse?lat=37.751&lon=-97.822&accept_language=en&normalize_address_names=true&include_names=true&include_extra_tags=true&include_geometry=false
Host: api.geofind.me
```

#### Example Response

```json
{
  "type": "FeatureCollection",
  "lat": 37.930344,
  "lon": -98.1055753,
  "importance": 0.5129590654309935,
  "search_rank": 12,
  "names": {
    "_place_name": "Reno",
    "alt_name": "Reno",
    "name": "Reno County",
    "name:en": "Reno County",
    "ref": "RN"
  },
  "extra_tags": {
    "linked_place": "county",
    "wikidata": "Q379657",
    "wikipedia": "en:Reno County, Kansas"
  },
  "is_area": true,
  "address": 0,
  "features": [
    {
      "type": "Feature",
      "properties": {
        "id": "R1070327",
        "category": "boundary",
        "type": "administrative",
        "place_type": "county",
        "name": "Reno",
        "address_rank": 12,
        "admin_level": 6,
        "is_address": true,
        "distance": 31902.62035389154,
        "bearing": 308.77603766533156
      }
    },
    {
      "type": "Feature",
      "properties": {
        "id": "R161644",
        "category": "boundary",
        "type": "administrative",
        "place_type": "state",
        "name": "Kansas",
        "address_rank": 8,
        "admin_level": 4,
        "is_address": true,
        "distance": -1,
        "bearing": -1
      }
    },
    {
      "type": "Feature",
      "properties": {
        "id": "R148838",
        "category": "boundary",
        "type": "administrative",
        "place_type": "country",
        "name": "United States",
        "address_rank": 4,
        "admin_level": 2,
        "is_address": true,
        "distance": -1,
        "bearing": -1
      }
    },
    {
      "type": "Feature",
      "properties": {
        "id": "",
        "category": "place",
        "type": "country_code",
        "name": "us",
        "address_rank": 4,
        "admin_level": 0,
        "is_address": false,
        "distance": -1,
        "bearing": -1
      }
    }
  ],
  "linked_places": [
    {
      "type": "Feature",
      "properties": {
        "id": "N316955958",
        "category": "place",
        "type": "county",
        "name": "Reno",
        "address_rank": 12,
        "admin_level": 15,
        "is_address": false,
        "distance": 0,
        "bearing": -1
      }
    }
  ],
  "summary": {
    "country_code": 3,
    "country": 2,
    "admin": 1
  },
  "licence": "https://www.geofind.me/licence"
}
```

#### Response Fields

- `type`: Type of the response (FeatureCollection).
- `lat`: Latitude coordinate of the queried location.
- `lon`: Longitude coordinate of the queried location.
- `importance`: Importance of the location.
- `search_rank`: Search rank of the location.
- `names`: Various names associated with the location.
- `extra_tags`: Extra tags associated with the location.
- `is_area`: Indicates whether the location is an area (true/false).
- `address`: Address index on `features`.
- `features`: Array of features with detailed information about the location.
- `linked_places`: Linked places associated with the location.
- `summary`: Summary information about the location (country code, country, admin, etc..).
- `licence`: Link to the geofind.me licence.

### How to Use

1. Make a GET request to `/reverse` with the desired latitude and longitude.
2. Receive detailed reverse geocoding information including address details and linked places.

Use the `/reverse` endpoint to obtain address information based on geographical coordinates.
