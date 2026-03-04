# ERIP - Emotion Recognition in Playstyle

A comprehensive system for collecting, processing, and analyzing gameplay data from Risk of Rain 2 to understand player behavior and emotional responses through gaming statistics.

## 📋 Project Overview

ERIP is a dual-component project that combines a **Risk of Rain 2 statistical collection plugin** with **Python-based data processing and analysis pipelines**. The project collects detailed gameplay telemetry and processes it using aggregation, joining, and preparation techniques to create datasets for machine learning analysis.

## 🏗️ Project Architecture

### Components

```
ERIP/
├─ RoR2/              # Risk of Rain 2 Plugin (C#)
│  └─ ScienceKit/     # BepInEx plugin for statistics collection
├─ Python/            # Data Processing Pipeline (Python)
│  ├─ Data Conversion & Preparation
│  ├─ Dataset Management
│  └─ DataAggregation/ # Multi-dimensional data aggregators
└─ DATASET.csv        # Output dataset
```

## 🎮 RoR2 Plugin - ScienceKit

A BepInEx plugin that collects comprehensive gameplay statistics from Risk of Rain 2.

### Features

- **Kill Statistics**: Tracks enemy eliminations and player deaths
- **Spawn Statistics**: Records enemy spawning events
- **Input Statistics**: Captures button presses and axis inputs
- **Item Statistics**: Monitors collected items and their effects
- **Player Health Statistics**: Logs health changes throughout gameplay
- **Player Stats Statistics**: Tracks character progression metrics
- **Persistent Storage**: Saves all statistics for later analysis

### Technical Details

- **Plugin Framework**: BepInEx
- **API**: R2API (Risk of Rain 2 API)
- **Target Framework**: .NET Standard 2.0
- **Language**: C#

## 🐍 Python Data Processing Pipeline

Handles data transformation, preparation, and aggregation for analysis.

### Key Scripts

| Script | Purpose |
|--------|---------|
| `erip_dataset.py` | PyTorch Dataset wrapper for image loading and processing |
| `data_conversion.py` | Converts raw game telemetry to standardized format |
| `data_joining.py` | Merges multiple data sources |
| `data_joining2.py` | Advanced data joining operations |
| `image_preparation.py` | Prepares game screenshots for ML processing |
| `image_emotion.py` | Analyzes emotional content in images |
| `heart_rate_preparation.py` | Processes heart rate sensor data |

### Data Aggregators (DataAggregation/)

Modular aggregators for multi-dimensional statistics processing:

- **AxisAggregator**: Aggregates analog stick/mouse movement data
- **ButtonsAggregator**: Compiles button input patterns
- **DataAggregator**: Core aggregation framework
- **EmotionAggregator**: Combines emotional indicators
- **EnemiesAggregator**: Aggregates enemy encounter data
- **HealthAggregator**: Compiles health statistics
- **ItemsAggregator**: Aggregates item collection patterns
- **StatsAggregator**: Compiles player progression statistics

### Technologies

- **PyTorch**: Dataset handling and tensor operations
- **scikit-image**: Image processing
- **torchvision**: Image transforms
- **Pandas**: Data manipulation (implied)

## 📊 Data Flow

```
RoR2 Gameplay
    ↓
ScienceKit Plugin (Collects Stats)
    ↓
Raw Statistics Files
    ↓
Python Data Processing
    ├─ Data Conversion
    ├─ Data Joining
    ├─ Multi-dimensional Aggregation
    └─ Image/Heart Rate Preparation
    ↓
DATASET.csv (Processed Dataset)
    ↓
ML Analysis
```

## 🚀 Getting Started

### Prerequisites

- **Risk of Rain 2** (Steam)
- **BepInEx** for RoR2 modding
- **Python 3.7+**
- **PyTorch**
- **scikit-image**

### Setup

1. **Install ScienceKit Plugin**
   - Copy the ScienceKit plugin to your BepInEx plugins directory
   - Run Risk of Rain 2 to generate gameplay statistics

2. **Set Up Python Environment**
   ```bash
   pip install torch torchvision scikit-image pandas
   ```

3. **Process Data**
   - Export statistics from RoR2
   - Run data conversion and aggregation scripts
   - Generated dataset will be saved to DATASET.csv

## 📝 Dataset Output

The final dataset contains:
- Player input metrics (buttons, axis inputs)
- Gameplay events (kills, spawns, item collection)
- Health and character progression data
- Emotional/physiological indicators (from images and heart rate)
- Aggregated statistics for ML analysis

## 🎯 Use Cases

- **Player Behavior Analysis**: Understand playstyle patterns
- **Emotion Recognition**: Correlate gameplay actions with emotional responses
- **Performance Metrics**: Track player skill progression
- **Biometric Integration**: Combine physiological data with gameplay
- **Machine Learning**: Train models on comprehensive player datasets

## 📦 Project Structure Details

### Statistics Collection (`RoR2/source/ScienceKit/Statistics/`)
- Base statistics interface (`IStatistics.cs`)
- Entry types for different data (`Entries/` folder)
- Specialized statistics collectors for each metric

### Data Processing (`Python/DataAggregation/`)
- Modular aggregator architecture
- Base `DataAggregator` class for inheritance
- Specific aggregators for each data dimension

## 🔧 Development

### Adding New Statistics

1. Create new `IStatistics` implementation in `Statistics/`
2. Define corresponding entry type in `Statistics/Entries/`
3. Register in `ScienceKitPlugin.cs`

### Adding New Data Aggregators

1. Create new class inheriting from `DataAggregator`
2. Implement aggregation logic
3. Integrate into pipeline

## 📄 License

[Add your license information here]

## 👥 Author

Created by DanteZ

---

**Note**: This project combines gaming telemetry collection with data science techniques to analyze player behavior and emotional responses during gameplay.
