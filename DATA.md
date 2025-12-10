# Data Documentation

This document provides detailed information about the data sources, processing methods, and formats used in this project.

## Earthquake Data

### Source
- **Provider**: United States Geological Survey (USGS)
- **API**: USGS Earthquake Catalog
- **Query URL**: https://earthquake.usgs.gov/fdsnws/event/1/query.geojson

### Query Parameters
```
starttime: 2025-03-26 00:00:00
endtime: 2025-12-10 23:59:59
minlatitude: 9.5
maxlatitude: 28.5
minlongitude: 92.0
maxlongitude: 101.2
minmagnitude: 2.5
orderby: time
```

### Geographic Coverage
- **Latitude**: 9.5°N to 28.5°N
- **Longitude**: 92.0°E to 101.2°E
- **Region**: Myanmar and surrounding areas

### Data Statistics
- **Total Events**: 164 earthquakes
- **Magnitude Range**: M 2.5 - 7.7
- **Depth Range**: 4.5 km - 141.5 km
- **Time Span**: March 28, 2025 - December 10, 2025
- **Strong Earthquakes (M ≥ 5.0)**: 20+ events

### Data Fields

Each earthquake record includes:

| Field | Type | Description |
|-------|------|-------------|
| `mag` | Float | Earthquake magnitude |
| `place` | String | Location description |
| `time` | Timestamp | Unix timestamp (milliseconds) |
| `updated` | Timestamp | Last update time |
| `url` | String | Link to USGS event page |
| `felt` | Integer | Number of felt reports (if available) |
| `cdi` | Float | Community Decimal Intensity |
| `mmi` | Float | Modified Mercalli Intensity |
| `alert` | String | Alert level (null, green, yellow, orange, red) |
| `status` | String | Review status |
| `tsunami` | Integer | Tsunami flag (0 or 1) |
| `coordinates` | Array | [longitude, latitude, depth] |

### Major Events

#### 1. M 7.7 Mandalay Earthquake (Main Shock)
- **ID**: us7000pn9s
- **Date**: March 28, 2025
- **Time**: 19:54:12 UTC
- **Location**: 22.011°N, 95.936°E
- **Depth**: 10.0 km
- **Felt Reports**: 2,543
- **Alert Level**: Red
- **MMI**: 9.953 (Very destructive)

#### 2. M 6.7 Aftershock
- **ID**: us7000pn9z
- **Date**: March 28, 2025
- **Time**: 19:58:44 UTC
- **Location**: 21.698°N, 95.969°E
- **Depth**: 10.0 km
- **Felt Reports**: 115
- **Alert Level**: Red
- **MMI**: 8.978

## Tectonic Data

### Source
- **Repository**: [myanmar-earthquake-archive](https://github.com/drtinkooo/myanmar-earthquake-archive)
- **File**: Myanmar_Tectonic_Map_2011.geojson
- **Format**: GeoJSON LineString features
- **Reference**: Myanmar Tectonic Map 2011

### Content
The tectonic dataset includes:
- Major fault systems (Sagaing Fault, etc.)
- Tectonic lineaments
- Geological structures
- Strike-slip boundaries
- Active fault zones

### Properties
Each tectonic feature may include:
- Fault name
- Type (strike-slip, thrust, normal)
- Activity status
- Slip rate
- Other geological attributes

## Data Format

### GeoJSON Structure

```json
{
  "type": "FeatureCollection",
  "metadata": {
    "generated": 1765368828000,
    "title": "USGS Earthquakes",
    "count": 164
  },
  "features": [
    {
      "type": "Feature",
      "id": "us6000rtv3",
      "properties": {
        "mag": 4.7,
        "place": "32 km E of Shwebo, Burma (Myanmar)",
        "time": 1765359335634,
        ...
      },
      "geometry": {
        "type": "Point",
        "coordinates": [96.0144, 22.5428, 10.0]
      }
    }
  ]
}
```

## Data Processing

### Embedded in HTML
The earthquake data is embedded directly in the `index.html` file as a JavaScript variable:

```javascript
const earthquakeData = { ... };
```

This approach:
- ✅ Eliminates need for external data files
- ✅ Works offline after initial load
- ✅ Faster loading (no additional HTTP requests)
- ✅ Simpler deployment (single file)

### Magnitude Categorization

Earthquakes are styled based on magnitude:

| Magnitude | Color | Marker Size | Category |
|-----------|-------|-------------|----------|
| M ≥ 7.0 | Dark Red (#8B0000) | 12px | Major |
| M 6.0-6.9 | Crimson (#DC143C) | 9px | Strong |
| M 5.0-5.9 | Orange-red (#FF4500) | 7px | Moderate |
| M 4.0-4.9 | Tomato (#FF6347) | 5px | Light |
| M 2.5-3.9 | Light Salmon (#FFA07A) | 3.5px | Minor |

## Data Quality

### USGS Review Status
All earthquakes in this dataset have been reviewed by USGS seismologists:
- **Status**: "reviewed"
- **Quality**: High-quality, verified data
- **Updates**: Data may be updated retroactively as more information becomes available

### Completeness
- ✅ Complete for M ≥ 2.5 in the specified region
- ✅ All major events included
- ✅ Comprehensive aftershock sequence
- ⚠️ Some smaller events (M < 2.5) may be missing

### Temporal Coverage
- **Start**: March 26, 2025 (2 days before main shock)
- **End**: December 10, 2025
- **Duration**: ~8.5 months
- **Coverage**: Complete sequence from main shock through aftershocks

## Data Updates

### How to Update

1. **Query USGS API**
   ```bash
   curl "https://earthquake.usgs.gov/fdsnws/event/1/query.geojson?starttime=2025-03-26&endtime=2025-12-31&minlatitude=9.5&maxlatitude=28.5&minlongitude=92&maxlongitude=101.2&minmagnitude=2.5" > new_data.json
   ```

2. **Replace embedded data in index.html**
   - Open `index.html`
   - Locate the `earthquakeData` variable
   - Replace with new GeoJSON content

3. **Test locally**
   - Open in browser
   - Verify all features work
   - Check statistics are correct

4. **Commit and push**
   ```bash
   git add index.html
   git commit -m "Update earthquake data to [date]"
   git push
   ```

## Data Citation

When using this data, please cite:

```
U.S. Geological Survey (2025). Earthquake Catalog. 
Retrieved from https://earthquake.usgs.gov/earthquakes/

Tin Ko Oo (2025). Sagaing Fault Seismicity Interactive Map.
GitHub: https://github.com/drtinkooo/sagaing-fault-seismicity
```

## Data Limitations

- Data represents point locations (epicenters), not fault rupture extents
- Depth accuracy varies (typically ±5-10 km)
- Magnitude types vary (mb, mww, etc.)
- Felt reports are voluntary and may be incomplete
- Small earthquakes may be missed in areas with limited monitoring

## Related Datasets

For additional context, consider:
- **Historical Myanmar seismicity**: [myanmar-earthquake-archive](https://github.com/drtinkooo/myanmar-earthquake-archive)
- **Global seismicity**: [USGS ComCat](https://earthquake.usgs.gov/data/comcat/)
- **Regional tectonic data**: Various geological surveys

## Contact

For questions about data processing or updates:
- Open an issue on GitHub
- Check USGS documentation: https://earthquake.usgs.gov/data/comcat/
