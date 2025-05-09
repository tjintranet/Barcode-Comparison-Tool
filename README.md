# Barcode Comparison Tool

A web-based application for comparing barcodes used in book manufacturing quality control. This tool allows operators to scan and compare Code 39 and DataMatrix barcodes to ensure matching components during the binding process.

![Barcode Comparison Tool Screenshot](screenshot.png)

## Overview

The Barcode Comparison Tool is designed for production environments where operators need to verify that the cover and book block components match before binding. The tool:

- Accepts input from physical barcode scanners
- Compares the first 13 digits of both barcodes
- Provides immediate visual and audio feedback about the match status
- Prevents data carryover between scans
- Works with standard web browsers without additional software

## Features

- **Simple, Focused Interface**: Clean design with clear visual indicators and instructions
- **Barcode Scanner Compatibility**: Works with most USB barcode scanners that emulate keyboard input
- **Multiple Feedback Methods**:
  - Color-coded input highlighting (green for match, red for no match)
  - Alert message with match status
  - Audio feedback (high tone for match, low tone for no match)
- **Data Validation**: Ensures Code 39 barcode contains exactly 13 digits and DataMatrix contains at least 13 digits
- **Error Prevention**: Automatically clears fields when appropriate and prevents data carryover between scans
- **Responsive Design**: Works on desktop workstations, tablets, and mobile devices

## Usage Instructions

### Basic Operation

1. Open the application in a web browser
2. Focus is automatically set to the Code 39 input field
3. Scan the Code 39 barcode from the book cover
4. Focus automatically moves to the DataMatrix input field
5. Scan the DataMatrix barcode from the book block
6. The comparison happens automatically and displays the result
7. To start a new comparison, either:
   - Click the Reset button
   - Click in the Code 39 field
   - Use the "Focus Code 39" button

### Detailed Workflow

#### First-Time Setup

1. Connect your barcode scanner to the computer
2. Open the Barcode Comparison Tool in a web browser
3. Ensure the scanner is configured to add a carriage return after each scan (most scanners do this by default)

#### Daily Usage

1. **Scan Cover**: Position the scanner over the Code 39 barcode on the book cover and scan
   - The first field will populate with the 13-digit code
   - Focus will automatically move to the second field

2. **Scan Book Block**: Position the scanner over the DataMatrix barcode on the book block and scan
   - The system extracts the first 13 digits from the DataMatrix code
   - Comparison happens automatically

3. **Read Result**:
   - **Green with checkmark**: Components match, proceed with binding
   - **Red with X**: Components do not match, do not bind these components together

4. **Reset for Next Check**: Click the Reset button or click into the Code 39 field

## Technical Details

### Input Requirements

- **Code 39 Input**: Must be exactly 13 digits
- **DataMatrix Input**: Must contain at least 13 digits (only the first 13 are compared)

### Browser Compatibility

- Chrome (recommended)
- Firefox
- Edge
- Safari

### Implementation Notes

The application is built using:
- HTML5
- CSS3 with Bootstrap 5.3
- Vanilla JavaScript

Key technical features include:
- Special handling of barcode scanner input behavior
- Prevention of data carryover between input fields
- Web Audio API for generating feedback tones
- Bootstrap for responsive layout and styling

## Installation

The Barcode Comparison Tool is a standalone web application that requires no server-side components or installation.

### Local Deployment

1. Download all files to a local directory
2. Open `index.html` in a web browser

### Network Deployment

1. Upload all files to a web server or shared network location
2. Access the tool via browser using the appropriate URL
3. For offline environments, deploy to a local web server on the network

## Troubleshooting

### Common Issues

| Problem | Possible Solution |
|---------|-----------------|
| Barcode scan not registering | Ensure scanner is configured to send Enter key after scan |
| DataMatrix not being recognized | Verify scanner supports DataMatrix format |
| Data carrying over between fields | Try increasing scan delay in scanner configuration |
| No sound feedback | Ensure browser sound is not muted |

### Browser Settings

- Allow JavaScript execution
- Allow Web Audio API (for sound feedback)
- For best results, use full-screen mode (F11 in most browsers)

## Custom Modifications

The tool can be customized by editing the HTML, CSS, and JavaScript:

- Change the header labels in the HTML
- Modify the color scheme in the CSS
- Adjust validation rules or comparison logic in the JavaScript

## Support and Feedback

For support or to provide feedback, please contact the IT department or the development team.

---

*Version 1.0 - May 2025*