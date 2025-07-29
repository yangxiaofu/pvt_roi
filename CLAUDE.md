# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file web application called "PVT ROI - Surge Protection Solution" that analyzes the Return on Investment (ROI) of using superior ERICO surge protection devices in mission-critical microgrid applications. The app is designed for:

- Client presentations  
- Trade show demonstrations
- iPad-based sales tools
- Offline use in any environment

## Architecture

The application is built as a **single HTML file** (`erico-protection-analyzer.html`) containing:
- Pure HTML structure with embedded CSS and JavaScript
- No external dependencies or frameworks
- Self-contained offline-capable design
- Touch-optimized interface for tablets

### Key Components

- **Multi-step wizard interface** with 4 main screens:
  1. Project Configuration (system size, inverter type/quantity)
  2. Fault Current Analysis (operating scenarios)
  3. Competitor Comparison (product ratings vs fault current)
  4. Financial Impact & ROI Calculator

- **Application State Management** via JavaScript object `appState` containing:
  - System configuration (size, inverter type/quantity)
  - Fault current scenario selection
  - Financial parameters (inverter cost, downtime cost)

- **Real-time Calculations** for:
  - Inverter quantity recommendations based on industry standards
  - Safety margins for surge protection devices
  - Financial impact of equipment failure and downtime
  - ROI comparisons between protection options

### Styling Architecture

- CSS custom properties for nVent brand colors
- Responsive design optimized for iPad (1024px breakpoint)
- Touch-friendly UI elements with hover effects
- Progress bar and animated transitions
- Card-based layout with professional styling

## Development Guidelines

### File Structure
- Main application: `erico-protection-analyzer.html` (single file containing everything)
- Assets: `asset/` and `assets/` directories for images
- Documentation: `README.md` and this `CLAUDE.md`

### Brand Guidelines
- Use nVent brand colors defined in CSS custom properties
- Maintain professional appearance suitable for trade shows
- Red (#c4262e) as primary brand color
- Orange (#ff6319) for accents and highlights

### Key Business Logic
- **Inverter sizing formulas** in `calculateInverterQuantity()` function
- **Competitor comparison** uses 65 kA as ERICO baseline rating
- **Financial calculations** include equipment replacement + 48-hour downtime costs
- **ROI analysis** assumes 99% protection effectiveness for ERICO products

### Testing
- Test primarily in modern web browsers (Chrome, Safari, Firefox)
- Verify touch interactions work on iPad devices
- Ensure offline functionality (no network dependencies)
- Validate calculations match business requirements

## Important Notes

- This is a **sales/marketing tool**, not a technical engineering calculator
- All calculations use simplified industry rules-of-thumb
- The app generates a summary report via JavaScript alert (not a PDF)
- Competitor product data is hardcoded in the `competitorProducts` array
- Financial parameters can be adjusted via sliders in the UI

## Live Demo

The application is deployed at: https://yangxiaofu.github.io/pvt_roi/erico-protection-analyzer.html