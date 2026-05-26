# BlinkStep

A JavaFX-based desktop application for interactive map visualization and navigation.

## About

BlinkStep is a Java-based desktop application built with JavaFX that provides map visualization capabilities using the GMapsFX library. The application allows users to interact with maps and perform navigation tasks through a modern graphical user interface.

## Tech Stack

- **Language**: Java (JDK 21.0.1)
- **UI Framework**: JavaFX with e(fx)clipse plugin
- **Map Integration**: GMapsFX
- **Data Format**: JSON (javax.json)
- **Build Tool**: Eclipse with JavaFX support
- **IDE**: Eclipse

## Features

- Interactive map visualization
- Map navigation and interaction
- JavaFX-based modern GUI
- Cross-platform support

## Prerequisites

Before setting up BlinkStep, ensure you have the following installed:

- **JDK 21.0.1** or higher
- **Eclipse IDE** with e(fx)clipse plugin
- **JavaFX SDK** (platform-specific)

## Installation & Setup

### 1. Install JDK 21.0.1

Download and install JDK 21.0.1 from the official source.

### 2. Clone the Repository

```bash
git clone https://github.com/nikitha0612/BlinkStep.git
cd BlinkStep
```

### 3. Install e(fx)clipse Plugin

1. Open Eclipse
2. Go to **Help** → **Eclipse Marketplace**
3. Search for "fx" and locate "e(fx)clipse"
4. Click **Install** and follow the prompts
5. Restart Eclipse

### 4. Download and Configure JavaFX SDK

1. Download JavaFX SDK from [GluonHQ](https://gluonhq.com/products/javafx/)
2. Select the appropriate version for your operating system
3. Extract the downloaded folder
4. Create a local directory (e.g., `/JavaFX-SDK`) and place the extracted folder there

### 5. Create JavaFX User Library in Eclipse

1. Go to **Eclipse** → **Preferences** → **Java** → **Build Path** → **User Libraries**
2. Click **New** to create a new user library
3. Name it "JavaFX"
4. Click **Add External JARs**
5. Navigate to `JavaFX-SDK/lib` and select all `.jar` files
6. Click **Apply and Close**

### 6. Configure BlinkStep Project

1. Right-click on the **BlinkStep** project
2. Select **Properties** → **Java Build Path**
3. In the **Libraries** tab:
   - Select **Classpath**
   - Click **Add Library...**
   - Choose **User Library**
   - Select **JavaFX**
   - Click **Finish** → **Apply and Close**

### 7. Add External Libraries

1. Go to **Java Build Path** → **Libraries** → **Classpath**
2. Click **Add External JARs**
3. Navigate to the `libs/` folder in the BlinkStep project
4. Select all `.jar` files (includes javax.json, gmapsfx, etc.)
5. Click **Apply and Close**

### 8. Configure Run Configuration

1. Right-click on the project
2. Select **Run As** → **Run Configurations**
3. Click **+** to create a new configuration
4. Name it "main"
5. Go to the **Arguments** tab and paste the following in **VM Arguments**:

```
--module-path /path/to/JavaFX-SDK/lib
--add-modules=javafx.swing,javafx.graphics,javafx.fxml,javafx.media,javafx.web
--add-reads javafx.graphics=ALL-UNNAMED
--add-opens javafx.controls/com.sun.javafx.charts=ALL-UNNAMED
--add-opens javafx.graphics/com.sun.javafx.iio=ALL-UNNAMED
--add-opens javafx.graphics/com.sun.javafx.iio.common=ALL-UNNAMED
--add-opens javafx.graphics/com.sun.javafx.css=ALL-UNNAMED
--add-opens javafx.base/com.sun.javafx.runtime=ALL-UNNAMED
```

Replace `/path/to/JavaFX-SDK/lib` with your actual JavaFX SDK lib directory path.

6. Uncheck all checkboxes under VM Arguments
7. Click **Apply and Close**

## Running the Application

1. Navigate to `src/MapApp.java`
2. Right-click and select **Run As** → **Java Application**
3. The application will launch with the map interface

## Project Structure

```
BlinkStep/
├── src/                  # Source code
├── libs/                 # External libraries (javax.json, gmapsfx, etc.)
├── data/                 # Data files
├── .project             # Eclipse project configuration
├── build.fxbuild        # JavaFX build configuration
├── .gitignore           # Git ignore rules
└── README.md            # This file
```

## Repository Info

- **Repository**: [nikitha0612/BlinkStep](https://github.com/nikitha0612/BlinkStep)
- **Forked from**: [Shiva-017/BlinkStep](https://github.com/Shiva-017/BlinkStep)
- **Language**: Java (98.7%)
- **Created**: July 2, 2025

## Troubleshooting

- **Module-related errors**: Ensure the `--module-path` in VM Arguments points to the correct JavaFX SDK lib directory
- **Missing JavaFX library**: Verify that the JavaFX user library is properly configured and all JARs are added
- **Compilation errors**: Confirm JDK 21.0.1 is installed and set as the project's JRE
- **GMapsFX not found**: Ensure all JARs from the `libs/` folder are added to the classpath

## License

Please refer to the repository for licensing information.

## Contributing

This is a fork of the original BlinkStep project. For contributions, consider submitting to the upstream repository.