# Creating DB providers

In order to support a new database type, Bash Schema Migrate needs a provider file.
The file must be a sourcable bash script named `provider_${DB_TYPE}` in the same directory as the main `bash-migrate` script.

The file must export the following environment variables:
 * MIGRATION_FILE_EXTENSION
 * DEFAULT_UP_TEMPLATE
 * DEFAULT_DOWN_TEMPLATE
 * DEFAULT_CONFIG_TEMPLATE

The file must export the following bash functions:
 * `check_env`: No arguments, invokes `die` function with error message if required environement vars are missing
 * `init_db`: No arguments, creates the bash-migrate data table
 * `get_status`: 
 * `run_migration`: 