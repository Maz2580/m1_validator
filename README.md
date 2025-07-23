# M1 Validator - GIS Automation System

## Project Structure

```
m1_validator/
├── README.md
├── requirements.txt
├── setup.py
├── .env.example
├── .gitignore
├── config/
│   ├── __init__.py
│   └── config.py
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── email_monitor.py
│   ├── file_processor.py
│   ├── workflow_runner.py
│   ├── data_analyzer.py
│   └── utils/
│       ├── __init__.py
│       ├── logger.py
│       ├── database.py
│       └── notifications.py
├── logs/
│   └── .gitkeep
├── tests/
│   ├── __init__.py
│   ├── test_email_monitor.py
│   ├── test_file_processor.py
│   ├── test_workflow_runner.py
│   └── test_data_analyzer.py
├── docs/
│   ├── installation.md
│   ├── configuration.md
│   ├── usage.md
│   └── troubleshooting.md
└── scripts/
    ├── install_service.py
    └── run_manual.py
```

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/Maz2580/m1_validator.git
   cd m1_validator
   ```

2. **Set up Python environment**
   ```bash
   python -m venv venv
   venv\Scripts\activate  # Windows
   pip install -r requirements.txt
   ```

3. **Configure environment**
   ```bash
   copy .env.example .env
   # Edit .env with your settings
   ```

4. **Run the application**
   ```bash
   python src/main.py
   ```

## Features

- **Automated Email Monitoring**: Monitors incoming orders from datashare.vic.gov.au
- **File Processing**: Downloads and extracts VICMAP data automatically
- **Workflow Execution**: Runs FME workflows and POZI Connect processes
- **Data Analysis**: Compares rates database with geocortex systems
- **Reporting**: Generates comprehensive discrepancy reports
- **Logging**: Detailed logging with rotation and archival
- **Error Handling**: Robust error handling with notifications

## System Requirements

- Windows 10/11 or Windows Server 2016+
- Python 3.8 or higher
- Microsoft Office (for Excel report generation)
- FME Desktop (for spatial data processing)
- POZI Connect (for M1 form generation)
- SQL Server access for rates database
- SDE connection for geocortex data

## Environment Variables

Create a `.env` file based on `.env.example` and configure:

```env
# Email Configuration
EMAIL_SERVER=outlook.office365.com
EMAIL_PORT=993
EMAIL_USER=maz.ghasemi@shepparton.vic.gov.au
EMAIL_PASSWORD=your_app_password

# Database Configuration
PATHWAY_DB_SERVER=your_sql_server
PATHWAY_DB_DATABASE=InfoProd
PATHWAY_DB_USER=your_username
PATHWAY_DB_PASSWORD=your_password

# File Paths
UPDATES_BASE_PATH=E:\Administration\Data\Updates\Updated Zip Files
FME_WORKFLOW_PATH=E:\Administration\FME Jobs\VicMap Updates
POZI_CONNECT_PATH=E:\Programs\Pozi Connect\PoziConnect.exe
M1_OUTPUT_PATH=E:\Programs\Pozi Connect\output\M1
M1_ARCHIVE_PATH=E:\Administration\Data\Rates\M1s
SDE_CONNECTION_PATH=F:\Connections\sdereader@vm59.sde

# Notification Settings
NOTIFICATION_EMAIL=admin@shepparton.vic.gov.au
SMTP_SERVER=smtp.office365.com
SMTP_PORT=587
```

## Installation

See [docs/installation.md](docs/installation.md) for detailed installation instructions.

## Configuration

See [docs/configuration.md](docs/configuration.md) for detailed configuration options.

## Usage

See [docs/usage.md](docs/usage.md) for usage instructions and examples.

## Support

For issues and support, please check [docs/troubleshooting.md](docs/troubleshooting.md) or create an issue on GitHub.
