# MetaCrate DJ Automation System v2.1.0

## Overview
MetaCrate is a comprehensive 5-phase DJ library automation system designed for professional music collection management, analysis, and optimization. The system provides intelligent duplicate detection, metadata enrichment, TreeSize Pro integration, and automated workflow management.

## Features

### Phase 1: Collection Discovery & Baseline Analysis
- **Comprehensive File Scanning**: Deep scan of music directories with advanced file discovery
- **TreeSize Pro Integration**: Professional file size analysis with corrected CLI syntax (`-scan` parameters)
- **Duplicate Detection**: Hash-based duplicate identification across entire collection
- **Progressive Monitoring**: Real-time scanning progress with detailed metrics

### Phase 2: Intelligent Duplicate Resolution
- **Smart Keep Logic**: Intelligent file selection based on quality, format, and metadata completeness
- **Progressive TreeSize Scanning**: Enhanced monitoring after duplicate resolution
- **Quality Assessment**: Advanced duplicate ranking with format priority and bitrate analysis
- **Batch Processing**: Efficient handling of large duplicate sets

### Phase 3: Metadata Enhancement
- **Music-Metadata Integration**: Professional-grade metadata extraction and enrichment
- **Database Optimization**: SQLite integration with comprehensive track information
- **Progressive Scanning**: TreeSize monitoring after metadata processing
- **Validation Systems**: Metadata completeness verification and quality assurance

### Phase 4: Collection Organization
- **Intelligent File Organization**: Smart directory structuring based on metadata
- **Progressive TreeSize Integration**: Continuous monitoring throughout organization phase
- **Quality Control**: Comprehensive validation of organized collection structure
- **Backup Systems**: Automated backup creation during organization process

### Phase 5: Final Optimization & Reporting
- **Final TreeSize Analysis**: Complete collection analysis with detailed metrics
- **Comprehensive Reporting**: Detailed analytics and collection statistics
- **JOBINFO Integration**: Professional workflow tracking with TreeSize Pro
- **Quality Assurance**: Final validation and optimization verification

## System Requirements
- **Windows 10/11**: Full Windows compatibility with PowerShell support
- **TreeSize Pro**: Professional edition with command-line interface
- **Node.js**: Version 16+ for JavaScript automation components
- **SQLite**: Database engine for metadata management
- **Disk Space**: Minimum 20% free space of collection size for processing

## Installation & Setup

### Quick Start
1. Clone repository: `git clone https://github.com/djunohoo/metacrate-dj-automation.git`
2. Install dependencies: `cd scripts && npm install`
3. Configure environment: `.\init_env.ps1`
4. Install services: `.\install_services.ps1`
5. Start automation: `.\metacrate.ps1`

### Advanced Configuration
- **TreeSize Pro Setup**: Ensure TreeSize Pro CLI is accessible in system PATH
- **Database Configuration**: Configure SQLite databases in `system/database/`
- **Custom Paths**: Modify paths in `scripts/metacrate_pipeline.js`
- **Service Integration**: Use PowerShell scripts for Windows service installation

## Architecture

### Core Components
- **metacrate_pipeline.js**: Main automation engine with 5-phase processing
- **Database Layer**: SQLite integration for metadata and tracking
- **TreeSize Integration**: Professional file analysis with corrected CLI syntax
- **PowerShell Scripts**: Windows service management and environment setup

### Database Schema
- **tracks**: Main track metadata and file information
- **duplicates**: Duplicate detection and resolution tracking
- **processing_log**: Comprehensive audit trail of all operations
- **metadata_cache**: Performance optimization for repeated operations

### TreeSize Pro Integration
```javascript
// Enhanced TreeSize scanning with proper CLI syntax
runTreeSizeScan() {
    const command = `TreeSize.exe -scan "${path}" -export csv`;
    // Progressive monitoring with JOBINFO integration
}
```

## Usage Examples

### Basic Collection Processing
```powershell
# Initialize environment and start full 5-phase processing
.\scripts\init_env.ps1
node .\scripts\metacrate_pipeline.js
```

### Phase-Specific Execution
```javascript
// Run specific phases
const metacrate = require('./metacrate_pipeline.js');
metacrate.runPhase(1); // Discovery & Baseline
metacrate.runPhase(3); // Metadata Enhancement
```

### Database Operations
```javascript
// Access track information
const db = require('sqlite3').Database('./system/database/metacrate.db');
db.all('SELECT * FROM tracks WHERE duplicate_group IS NOT NULL');
```

## Version History

### v2.1.0 - Current Release
- **Enhanced TreeSize Pro Integration**: Corrected CLI syntax using `-scan` instead of `/SCAN`
- **Progressive Scanning Strategy**: TreeSize analysis after Phase 2, 4, and 5
- **Improved JOBINFO Integration**: Comprehensive workflow tracking with detailed metrics
- **Advanced Duplicate Detection**: Enhanced hash-based duplicate identification
- **Performance Optimizations**: Improved processing speed and memory efficiency

### Previous Versions
- **v2.0.x**: Core 5-phase automation system
- **v1.x**: Initial TreeSize integration and metadata processing

## Support & Documentation
- **GitHub Repository**: https://github.com/djunohoo/metacrate-dj-automation
- **Issues & Feature Requests**: Use GitHub Issues for support and feature requests
- **Documentation**: Comprehensive documentation in `/docs` directory
- **Community**: Active community support and contributions welcome

## License
Professional DJ automation system for music collection management. All rights reserved.

---

*MetaCrate v2.1.0 - Professional DJ Library Automation System*
*Enhanced TreeSize Pro Integration with Progressive Monitoring*