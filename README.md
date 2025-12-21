# DB-IP City Lite - Free IP Geolocation Database

[![npm version](https://img.shields.io/npm/v/dbip-city-lite.svg)](https://www.npmjs.com/package/dbip-city-lite)
[![npm downloads](https://img.shields.io/npm/dm/dbip-city-lite.svg)](https://www.npmjs.com/package/dbip-city-lite)
[![License](https://img.shields.io/badge/license-CC%20BY%204.0-green)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Stars](https://img.shields.io/github/stars/wp-statistics/DbIP-City-lite?style=social)](https://github.com/wp-statistics/DbIP-City-lite)

Free DB-IP City Lite database for IP geolocation. A lightweight alternative to MaxMind with city-level accuracy. Automatically updated and served via jsDelivr CDN.

**Website:** [geo.wp-statistics.com](https://geo.wp-statistics.com)

---

## Features

- **City-Level Accuracy** - Get country, city, coordinates, and more
- **Lightweight** - Smaller file size (~19 MB) compared to alternatives
- **Auto-Updated** - Database updated automatically on 1st of each month
- **Fast CDN** - Served via jsDelivr with global edge locations
- **No Authentication** - Direct download, no API keys required
- **Free Forever** - Open source under CC BY 4.0 license

---

## Quick Start

### Direct Download

```
https://cdn.jsdelivr.net/npm/dbip-city-lite/dbip-city-lite.mmdb.gz
```

### PHP

```php
use GeoIp2\Database\Reader;

$reader = new Reader('/path/to/dbip-city-lite.mmdb');
$record = $reader->city('128.101.101.101');

echo $record->country->name;  // 'United States'
echo $record->city->name;     // 'Minneapolis'
```

### Node.js

```javascript
const { Reader } = require('@maxmind/geoip2-node');

const reader = await Reader.open('./dbip-city-lite.mmdb');
const response = reader.city('128.101.101.101');

console.log(response.country.names.en);  // 'United States'
console.log(response.city.names.en);     // 'Minneapolis'
```

### Python

```python
import geoip2.database

reader = geoip2.database.Reader('./dbip-city-lite.mmdb')
response = reader.city('128.101.101.101')

print(response.country.name)  # 'United States'
print(response.city.name)     # 'Minneapolis'
```

### WordPress (WP Statistics)

```php
use WP_Statistics\Service\Geolocation\GeolocationFactory;

$location = GeolocationFactory::getLocation('128.101.101.101');
echo $location['city'];  // 'Minneapolis'
```

---

## Database Info

| Property | Value |
|----------|-------|
| **CDN URL** | `https://cdn.jsdelivr.net/npm/dbip-city-lite/dbip-city-lite.mmdb.gz` |
| **npm** | `npm install dbip-city-lite` |
| **Update Schedule** | Monthly (1st of each month) |
| **Size** | ~19 MB (compressed) |
| **Format** | MaxMind DB (MMDB) |
| **License** | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

---

## Update Schedule

This database is **automatically updated** via GitHub Actions:

- **Schedule:** 1st of each month at 06:00 UTC
- **Source:** [DB-IP Lite](https://db-ip.com/db/lite.php)
- **Distribution:** Published to npm, served via jsDelivr CDN

#### Last updated: 2025-12-21

---

## DB-IP vs MaxMind

| Feature | DB-IP City Lite | MaxMind GeoLite2-City |
|---------|-----------------|----------------------|
| **File Size** | ~19 MB | ~68 MB |
| **Update Frequency** | Monthly | Twice weekly |
| **License** | CC BY 4.0 | CC BY-SA 4.0 |
| **Best For** | Smaller deployments | Higher accuracy needs |

---

## Related Resources

- **Documentation:** [geo.wp-statistics.com](https://geo.wp-statistics.com)
- **MaxMind Alternative:** [GeoLite2-City](https://github.com/wp-statistics/GeoLite2-City)
- **Country Database:** [GeoLite2-Country](https://github.com/wp-statistics/GeoLite2-Country)
- **WP Statistics:** [wordpress.org/plugins/wp-statistics](https://wordpress.org/plugins/wp-statistics/)

---

## Attribution

This database is provided by [DB-IP](https://db-ip.com/). When using this database, you must include a link back to DB-IP.com on pages that display results from the database, as required by the [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/).

---

## License

DB-IP City Lite is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Maintained by [VeronaLabs](https://veronalabs.com) and the [WP Statistics](https://wp-statistics.com) team.
