## /geoip

The `/geoip` endpoint of geofind.me provides GeoIP analysis, allowing you to obtain geographical coordinates and ASN (Autonomous System Number) information based on IP addresses.

### Endpoint

```http
GET /geoip?ip={ip_address}
```

- `ip` (required): The IP address for which you want to perform GeoIP analysis.

#### Example Request

```http
GET /geoip?ip=8.8.8.8
Host: api.geofind.me
```

#### Example Response

```json
{
  "autonomous_system_number": 15169,
  "autonomous_system_organization": "GOOGLE",
  "lat": 37.751,
  "lon": -97.822,
  "radius": 1000000,
  "is_proxy": false,
  "is_satellite": false
}
```

#### Response Fields

- `autonomous_system_number`: ASN (Autonomous System Number) associated with the IP.
- `autonomous_system_organization`: Organization associated with the ASN.
- `lat`: Latitude coordinate.
- `lon`: Longitude coordinate.
- `radius`: Estimated radius of the location (in meters).
- `is_proxy`: Indicates whether the IP is a proxy (true/false).
- `is_satellite`: Indicates whether the IP is associated with a satellite connection (true/false).

### How to Use

1. Make a GET request to `/geoip` with the desired IP address.
2. Receive detailed GeoIP analysis including geographical coordinates and ASN information.

Use the `/geoip` endpoint to gather insights into the geographical location and network details of a given IP address.
