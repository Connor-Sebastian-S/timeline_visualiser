# Interactive Timeline Visualiser

A web-based tool that enables users to create visually appealing, interactive timelines from structured CSV data with optional image support.

https://connor-sebastian-s.github.io/timeline_visualiser/

## Overview

The Interactive Timeline Visualiser transforms chronological data into a visual experience. Users can upload CSV data containing event information along with accompanying images to generate an interactive timeline that displays events along a flowing path. Each event is represented by a clickable bubble that reveals detailed information and associated images when selected.

## Features

- **Data Input**: Upload timeline data via a simple CSV format with drag-and-drop functionality
- **Image Support**: Include images for each event by uploading a ZIP file with organised folders
- **Interactive Visualisation**: Navigate through events displayed on a dynamic, flowing timeline
- **Detailed Event View**: Click on events to view comprehensive information including dates, descriptions, and associated images
- **Responsive Design**: Automatically adjusts to different screen sizes for optimal viewing experience
- **Type-Based Colour Coding**: Events are colour-coded based on their type for enhanced visual categorisation
- **Image Gallery**: View event-related images with lightbox functionality for detailed examination

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- No server-side dependencies required (functions entirely in the browser)
- CSV file with event data and optional ZIP file with images

## Installation

No installation is required. Simply download the HTML file and open it in a web browser to use the application.

## Usage Instructions

### Preparing Your Data

1. **Create a CSV File** with the following required columns:
   - `ID`: Unique identifier for each event
   - `START_DATE`: Event start date in DD-MM-YYYY format
   - `END_DATE`: Event end date in DD-MM-YYYY format
   - `EVENT`: Short title or name of the event
   - `DESCRIPTION`: Detailed description of the event
   - `TYPE` (optional): Category of the event for colour coding

   Example CSV format:
   ```
   ID,START_DATE,END_DATE,EVENT,DESCRIPTION,TYPE
   1,01-01-2020,15-01-2020,Project Launch,"Initial project kickoff meeting with stakeholders.",work
   2,20-01-2020,25-02-2020,Research Phase,"Conducted market research and competitor analysis.",research
   ```

2. **Prepare Images** (Optional):
   - Create a folder for each event, named with the event's ID
   - Place relevant images inside the corresponding folders
   - Compress all folders into a single ZIP file
   
   Example structure:
   ```
   images.zip
   ├── 1/
   │   ├── kickoff.jpg
   │   └── team.jpg
   ├── 2/
   │   ├── research.jpg
   │   └── analysis.png
   └── 3/
       └── implementation.jpg
   ```

### Using the Visualiser

1. Open the Interactive Timeline Visualiser in your web browser
2. Upload your CSV file by dragging it to the designated area or clicking "Select CSV File"
3. If you have images, upload the ZIP file by dragging it to the images upload area or clicking "Select ZIP File"
4. Click "Process Data" to generate the timeline
5. Interact with the timeline by clicking on event bubbles to view detailed information
6. View images in full-screen mode by clicking on them in the event detail view
7. The website has default files it loads automatically if they are present; input.csv and images.zip.

## Customisation

The visualiser can be customised by modifying the CSS variables at the top of the stylesheet:

```css
:root {
    --primary-color: #4a6fa5;
    --secondary-color: #334e68;
    --background-color: #f5f7fa;
    --text-color: #333;
    --light-gray: #e1e5eb;
}
```

Additional event types and colours can be added to the `colorMap` object in the JavaScript code.

## Browser Compatibility

The visualiser has been tested and confirmed to work on:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Troubleshooting

**Issue: CSV file not loading**
- Ensure the CSV file follows the exact format specified above
- Check that date fields use the DD-MM-YYYY format
- Verify that the file has the .csv extension

**Issue: Images not appearing**
- Confirm that the ZIP file structure matches the requirement (folders named by event ID)
- Ensure images are in a supported format (jpg, jpeg, png, gif, bmp, webp, svg)
- Verify that the folder names in the ZIP exactly match the ID values in the CSV

**Issue: Timeline not rendering properly**
- Try resizing the browser window
- Ensure the CSV contains at least one valid event
- Check browser console for any JavaScript errors

## Licence

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

- Uses [JSZip](https://stuk.github.io/jszip/) library for handling ZIP files
