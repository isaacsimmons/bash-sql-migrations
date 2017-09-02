# Creating DB providers

Instructions for adding support for new types of databases to bash-migrate.
Intended for bash-migrate developers or advanced users only.

In order to support a new database type, bash-migrate needs a provider file.
The file must be a sourcable bash script named `provider-${DB_TYPE}` in the same directory as the main `bash-migrate` script.

The file must export the following environment variables:
 * MIGRATION_FILE_EXTENSION
 * DEFAULT_UP_TEMPLATE
 * DEFAULT_DOWN_TEMPLATE
 * DEFAULT_CONFIG_TEMPLATE

The file must export the following bash functions:
 * `check_env`: No arguments, invokes `die` function with error message if required environement vars are missing
 * `init_db`: No arguments, creates the bash-migrate data table
 * `get_status`: No arguments, prints to standard out all of the names of all migrations and their current status (new/up/down).
 * `run_migration`: Single argument of the path to the (up or down) migration file to apply.