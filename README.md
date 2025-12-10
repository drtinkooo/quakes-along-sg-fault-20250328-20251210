# Sagaing Fault Seismicity (March 28 - December 10, 2025)

Interactive web map visualizing 164 earthquakes along the Sagaing Fault in Myanmar following the catastrophic M 7.7 Mandalay earthquake on March 28, 2025.

## 🌐 Live Demo

**[View Interactive Map](https://drtinkooo.github.io/sagaing-fault-seismicity/)**

## 📋 Overview

This project provides an interactive visualization of seismic activity along Myanmar's Sagaing Fault zone during the period from March 28 to December 10, 2025. The map displays all recorded earthquakes (M ≥ 2.5) following the devastating M 7.7 Mandalay earthquake, overlaid on tectonic lineaments to provide geological context.

## ✨ Features

### Interactive Map
- **164 earthquake epicenters** color-coded and sized by magnitude
- **Tectonic lineaments** of Myanmar showing fault structures
- **Multiple base layers**: Street Map, Satellite, and Terrain views
- **Layer control** to toggle earthquakes and tectonic features
- **Responsive design** works on desktop and mobile devices

### Data Visualization
- **Magnitude-based styling**:
  - M ≥ 7.0: Dark red (large markers)
  - M 6.0-6.9: Crimson
  - M 5.0-5.9: Orange-red
  - M 4.0-4.9: Tomato red
  - M 2.5-3.9: Light salmon (small markers)

### Interactive Features
- **Click on earthquakes** for detailed information (magnitude, location, time, depth, felt reports)
- **Magnitude filter slider** to adjust minimum magnitude (2.5 - 7.7)
- **Statistics panel** showing:
  - Total events count
  - Magnitude range
  - Count of M ≥ 5.0 earthquakes
  - Latest event information
- **Major events list** (M ≥ 5.0) sorted by magnitude
- **Mouse coordinate display** showing latitude/longitude
- **Scale bar** for distance reference
- **Direct links to USGS** earthquake pages for more details

## 📊 Data

### Earthquake Data
- **Source**: [USGS Earthquake Catalog](https://earthquake.usgs.gov/)
- **Time Period**: March 28, 2025 - December 10, 2025
- **Region**: Myanmar (9.5°N - 28.5°N, 92°E - 101.2°E)
- **Magnitude Range**: M 2.5 - 7.7
- **Total Events**: 164 earthquakes
- **Format**: GeoJSON embedded in HTML

### Tectonic Data
- **Source**: Myanmar Tectonic Map 2011
- **Repository**: [myanmar-earthquake-archive](https://github.com/drtinkooo/myanmar-earthquake-archive)
- **Format**: GeoJSON (loaded from GitHub)

### Major Events Included
1. **M 7.7** - 2025 Mandalay Earthquake (March 28, 2025) - Main shock
2. **M 6.7** - Burma (March 28, 2025) - Major aftershock
3. **M 5.2** - Near Shwebo (multiple events)
4. **Numerous aftershocks** M 4.0-4.9

## 🛠️ Technology Stack

- **HTML5/CSS3** - Structure and styling
- **JavaScript** - Interactive functionality
- **Leaflet.js 1.9.4** - Interactive mapping library
- **OpenStreetMap** - Base map tiles
- **ESRI World Imagery** - Satellite imagery
- **OpenTopoMap** - Terrain visualization

## 🚀 Usage

### Online Access
Simply visit the [live demo]([https://drtinkooo.github.io/quakes-along-sg-fault-20250328-20251210

/) to view the interactive map.

### Local Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/drtinkooo/quakes-along-sg-fault-20250328-20251210.git
   ```
2. Open `index.html` in any modern web browser
3. No server or installation required - it's a standalone HTML file

### Embedding
You can embed this map in your website using an iframe:
```html
<iframe src="https://drtinkooo.github.io/quakes-along-sg-fault-20250328-20251210/" 
        width="100%" height="600" frameborder="0"></iframe>
```

## 📁 Repository Structure

```
quakes-along-sg-fault-20250328-20251210/
├── index.html          # Main interactive map (standalone, embedded data)
├── README.md           # This documentation
├── LICENSE             # MIT License
└── screenshots/        # Preview images (optional)
```

## 🔍 Key Findings

### Seismic Sequence Analysis
- The M 7.7 Mandalay earthquake triggered an extensive aftershock sequence
- Activity is concentrated along the Sagaing Fault zone
- Aftershocks range from M 2.5 to M 6.7
- Significant events (M ≥ 5.0): 20+ earthquakes
- Spatial distribution shows clear alignment with tectonic structures

### Temporal Pattern
- Highest activity immediately following the main shock (March 28)
- Continued seismicity through December 2025
- Multiple M 4+ earthquakes near Shwebo, Mandalay, and Sagaing regions

## 📖 Scientific Context

The **Sagaing Fault** is a major right-lateral strike-slip fault system that runs through central Myanmar. It forms part of the boundary between the Indian and Eurasian plates and is one of the most seismically active fault zones in Southeast Asia.

The March 28, 2025 M 7.7 Mandalay earthquake represents one of the largest seismic events recorded along this fault system in recent history. The extensive aftershock sequence provides valuable data for understanding:
- Fault mechanics and stress transfer
- Seismic hazard assessment
- Regional tectonic processes
- Earthquake prediction and early warning systems

## 🎓 Applications

This visualization is useful for:
- **Researchers**: Studying aftershock patterns and fault behavior
- **Emergency managers**: Understanding seismic risk distribution
- **Educators**: Teaching about earthquakes and plate tectonics
- **General public**: Accessing earthquake information for affected regions
- **Media**: Communicating seismic events to the public

## 🤝 Contributing

Contributions are welcome! If you'd like to improve this project:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

### Potential Improvements
- Add temporal animation showing earthquake progression
- Include historical seismicity for comparison
- Add earthquake magnitude-frequency analysis
- Create downloadable data exports
- Add multi-language support (Myanmar, English)

## 📝 Citation

If you use this visualization in your research or publication, please cite:

```
Tin Ko Oo (2025). Sagaing Fault Seismicity: Interactive Map of the 2025 Mandalay 
Earthquake Sequence. GitHub repository: https://github.com/drtinkooo/quakes-along-sg-fault-20250328-20251210
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **USGS** for providing comprehensive earthquake data
- **OpenStreetMap contributors** for base map data
- **Leaflet.js** for the excellent mapping library
- **Myanmar Earthquake Archive** for tectonic lineament data

## 📧 Contact

**Tin Ko Oo**
- Mahidol University, Thailand
- Email: tin.koo@mahidol.ac.th

For questions or collaboration opportunities, please open an issue in this repository.

## ⚠️ Disclaimer

This visualization is for educational and research purposes. For official earthquake information and safety guidance, please refer to:
- [USGS Earthquake Hazards Program](https://earthquake.usgs.gov/)
- Myanmar Department of Meteorology and Hydrology
- Local emergency management authorities

## 🔄 Updates

- **December 10, 2025**: Initial release with data through December 10, 2025
- Future updates will include additional seismicity data as it becomes available

---

**⭐ If you find this project useful, please consider giving it a star!**
