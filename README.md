# StressMeter 📊

A mobile Android application for tracking and visualizing daily stress levels through an intuitive image-based interface.

📥 Download APK: [*StressMeter.apk*](https://drive.google.com/file/d/1fS8t7M6G3Uvw-3-LLUAcYCx7qCh_K-x4/view?usp=sharing)

## Overview

StressMeter is a psychology-inspired mobile app that helps users monitor their stress levels over time. Instead of traditional surveys, it uses a visual approach where users select images that represent their current stress state. The app records these selections with timestamps and provides data visualization to help users reflect on their stress patterns.

## Features

- **Visual Stress Assessment**: Select from 16 unique images across 3 pages that correlate with different stress levels
- **Data Persistence**: Automatic saving of stress scores and timestamps to CSV file
- **Interactive Visualization**: View your stress history through graphs and tables
- **Modern UI**: Navigation drawer with smooth transitions
- **Audio/Haptic Feedback**: Sound and vibration on app launch
- **Responsive Design**: Supports multiple screen orientations

## How It Works

1. **Select Stress Level**: Browse through a grid of images and select one that represents your current stress state
2. **Confirm Selection**: View the enlarged image and confirm or cancel your selection
3. **Data Storage**: Your stress score and timestamp are automatically saved to `stress_timestamp.csv`
4. **View Results**: Switch to the Results view to see graphs and tables of your stress patterns over time

## Architecture

The app follows the **MVVM (Model-View-ViewModel)** architecture pattern with LiveData for reactive UI updates.

### Project Structure

```
StressMeter/
├── ImageRequest/
│   ├── ImageAdapter (Custom grid view adapter)
│   ├── ImageRequestFragment (UI components for image grid display)
│   └── ImageRequestViewModel (UI state management)
├── ImageResponse/
│   ├── ImageResponseActivity (UI components for enlarged image)
│   └── ImageResponseViewModel (UI state management)
├── Visualization/
│   ├── VisualizationFragment (UI components for graphs, table etc.)
│   └── VisualizationViewModel (UI state management)
├── Util/
│   └── Utils (Permission verification)
└── MainActivity.kt
```

### Key Components

#### Image Request Module
- **ImageRequestFragment**: Displays the GridView of stress level images
- **ImageRequestViewModel**: Manages image data and user selection state
- **ImageAdapter**: Custom adapter for rendering images in the GridView

#### Image Response Module
- **ImageResponseActivity**: Shows enlarged image and handles confirmation/cancellation
- **ImageResponseViewModel**: Manages selected image data and score calculation

#### Visualization Module
- **VisualizationFragment**: Displays stress data as graphs and tables
- **VisualizationViewModel**: Handles CSV file reading and data processing for visualization

#### Utilities
- **Utils**: Manages runtime permissions for storage and other features

#### Main
- **MainActivity**: Hosts fragments and manages NavigationView drawer

### UI Components

- **GridView**: Displays stress level images in a responsive grid layout
- **NavigationView**: Material Design sliding drawer for view navigation
- **Graphing Library ( [AnyChart](https://github.com/AnyChart/AnyChart) )**: Third-party visualization library for plotting stress data

## Setup & Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/AyushArora10hg/StressMeter.git
   ```

2. Open the project in Android Studio

3. Sync Gradle files

4. Run the app on an emulator or physical device

## Data Storage

Stress data is stored in `stress_timestamp.csv` with the following format:
```
score,timestamp
5,2024-01-15 14:30:00
8,2024-01-15 18:45:00
```

## Acknowledgments

- Image assets provided as part of the original lab assignment
- Inspired by research on visual stress assessment methods
- Built as part of mobile computing coursework
