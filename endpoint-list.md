# Address Listing - /list

The `/list` endpoint of geofind.me allows you to retrieve hierarchical address information based on resolution and optional parameters.

```
GET /list?resolution={resolution}&accept_language={language}&normalize_address_names={true/false}&country_code={country_code}&region_id={region_id}&admin_id={admin_id}
```

- `resolution` (required): Resolution level for hierarchical listing (1-4, 1 being the highest resolution).
- `accept_language` (optional): Preferred language for address names.
- `normalize_address_names` (optional): Normalize address names (true/false, default is false).
- `country_code` (optional): Country code for filtering results.
- `region_id` (optional): Region ID for filtering results.
- `admin_id` (optional): Admin ID for filtering results.

### Example Request

```
GET /list?resolution=3&accept_language=en&normalize_address_names=true&country_code=nl
```

### Example Response

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "id": "R47540",
        "category": "boundary",
        "type": "administrative",
        "place_type": "state",
        "name": "Drenthe",
        "address_rank": 8,
        "admin_level": 4,
        "is_address": true,
        "distance": 0,
        "bearing": -1
      }
    },
    {
      "type": "Feature",
      "properties": {
        "id": "R47407",
        "category": "boundary",
        "type": "administrative",
        "place_type": "state",
        "name": "Flevoland",
        "address_rank": 8,
        "admin_level": 4,
        "is_address": true,
        "distance": 0,
        "bearing": -1
      }
    },
    //... (other features)
  ],
  "licence": "https://www.geofind.me/licence"
}
```

### Response

The `/list` endpoint provides a response in the GeoJSON format, widely used for representing geographical data. GeoJSON is a standard that encapsulates geographical locations, properties, and other relevant information.

- `type`: Type of the response (FeatureCollection).
- `features`: List of addresses.
- `licence`: Link to the geofind.me licence.
