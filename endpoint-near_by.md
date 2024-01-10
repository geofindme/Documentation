## Endpoint /near_by

The `/near_by` endpoint of geofind.me allows you to discover nearby locations based on specific coordinates.

```http
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

```http
GET /near_by?resolution=3&lat=37.751&lon=-97.822&sort_by=1&accept_language=en&normalize_address_names=true&limit=5
Host: api.geofind.me
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

### Response Fields

- `type`: Type of the response (FeatureCollection).
- `features`: Array of features with detailed information about nearby locations.
- `licence`: Link to the geofind.me licence.

### How to Use

1. Make a GET request to `/near_by` with the desired resolution, coordinates, and sortby.
2. Receive a list of nearby locations based on the specified coordinates.

Use the `/near_by` endpoint to discover nearby locations based on specific coordinates.
