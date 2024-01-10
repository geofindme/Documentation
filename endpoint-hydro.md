## Hydrographic Data Exploration - /hydro

The `/hydro` endpoint provides information about water bodies based on given coordinates. Explore and discover nearby seas, lakes, and more.

```
GET /hydro?lat={latitude}&lon={longitude}&accept_language={language}&normalize_address_names={true/false}
```

- `lat` (required): Latitude coordinate for the center of the search.
- `lon` (required): Longitude coordinate for the center of the search.
- `accept_language` (optional): Preferred language for address names.
- `normalize_address_names` (optional): Normalize address names (true/false, default is false).

### Example Request

```
GET /hydro?lat=40.8420&lon=28.9771&accept_language=en&normalize_address_names=true
```

### Example Response

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "id": "R5511568",
        "category": "place",
        "type": "sea",
        "name": "Sea of Marmara",
        "address_rank": 100,
        "admin_level": 15,
        "is_address": true,
        "distance": 0,
        "bearing": -1
      }
    }
  ],
  "licence": "https://www.geofind.me/licence"
}
```

### Response

The `/hydro` endpoint provides a response in the GeoJSON format, widely used for representing geographical data. GeoJSON is a standard that encapsulates geographical locations, properties, and other relevant information.

- `type`: Type of the response (FeatureCollection).
- `features`: List of found hydros.
- `licence`: Link to the geofind.me licence.
