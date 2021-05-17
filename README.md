--------------------------------------------------------------------------------
## backup_configs.py

### DESCRIPTION
This script iterates through a dashboard organization and backs up the configuration for the org, networks & templates, 
and devices, for the config settings that have API endpoint support.

### PREREQUISITES
Use with Meraki Python SDK @ github.com/meraki/dashboard-api-python/ & install required libraries with

  `pip install -r requirements.txt` 

> API key can, and is recommended to, be set as an environment variable named MERAKI_DASHBOARD_API_KEY. 

### USAGE
Run the command below.  Options are not required if enclosed in "[]".

  `./backup_configs.py [-o <org_id>] [-k <api_key>] [-t <tag>] [-y]`

If the optional [-t <tag>] is provided, then filter only for those networks with the tag, along with those networks' devices.
Optional flag [-y] to automatically continue to run without waiting for user confirmation.

--------------------------------------------------------------------------------
## restore_configs.py

### DESCRIPTION
This script creates new networks/templates and restores their configuration from a backup set of JSON files.
Settings that require a device to be present are not included, to safely not affect any running networks/devices.
See the input restore_operations.csv spreadsheet for full list of API endpoints that are requested.

### PREREQUISITES
Use with Meraki Python SDK @ github.com/meraki/dashboard-api-python/ & install required libraries with

  `pip install -r requirements.txt`

> API key can, and is recommended to, be set as an environment variable named MERAKI_DASHBOARD_API_KEY.

### USAGE
Run the command below.  Options are not required if enclosed in "[]".

  `./restore_configs.py [-o <org_id>] [-k <api_key>] -d <backup_directory>`
