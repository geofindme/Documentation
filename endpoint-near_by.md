## Explore Nearby Locations - /near_by

The `/near_by` endpoint of geofind.me allows you to discover nearby locations based on specific coordinates.

```
GET /near_by?resolution={resolution}&lat={latitude}&lon={longitude}&sort_by={sort_order}&accept_language={language}&normalize_address_names={true/false}&limit={limit}
```

- `resolution` (required): Resolution level for hierarchical listing (1-4, 1 being the highest resolution).
- `lat` (required): Latitude coordinate for the center of the search.
- `lon` (required): Longitude coordinate for the center of the search.
- `sort_by` (required): Sorting order for the results (1: distance, 2: importance).
- `accept_language` (optional): Preferred language for address names.
- `normalize_address_names` (optional): Normalize address names (true/false, default is false).
- `limit` (optional): Limit the number of results returned (default is 1000, also maximum).

### Example Request

```
GET /near_by?resolution=3&lat=37.751&lon=-97.822&sort_by=1&accept_language=en&normalize_address_names=true&limit=5
```

### Example Response

```json
{
  "type": "FeatureCollection",
  "features": [
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
        "distance": 88351.19361783225,
        "bearing": 311.3136636764616
      }
    },
    {
      "type": "Feature",
      "properties": {
        "id": "R161645",
        "category": "boundary",
        "type": "administrative",
        "place_type": "state",
        "name": "Oklahoma",
        "address_rank": 8,
        "admin_level": 4,
        "is_address": true,
        "distance": 314818.4017878988,
        "bearing": 170.77449436480606
      }
    },
    //... (other features)
  ],
  "licence": "https://www.geofind.me/licence"
}
```

### Response

The `/near_by` endpoint provides a response in the GeoJSON format, widely used for representing geographical data. GeoJSON is a standard that encapsulates geographical locations, properties, and other relevant information.

- `type`: Type of the response (FeatureCollection).
- `features`: List of nearby locations.
- `licence`: Link to the geofind.me licence.
