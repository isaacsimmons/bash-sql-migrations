# Usage

## Basic overview

`./bash_migrate [--dir migration_dir] <command> [command opts]`

If specified, the `--dir` command line option defines the migrations directory.
Next, it will fall back to the `MIGRATION_DIR` environment variable.
Finally, if neither is specified, it will be assumed to be `./migrations` (relative to the current working directory).

## Commands

`./bash_migrate init <provider type>`: Initializes a new migration directory with a basic config file and migration template files.

`./bash_migrate create <migration name>`: Creates up and down files for a new migration.

`./bash_migrate list`: Prints the current status of all migrations.

`./bash_migrate run [<migration identifier>]` Apply or rollback migrations in order as needed to get the database into the specfied state.
An identifier can be any of the following:
* the timestamp of any migration
* the the name of any migration
* `0` refers to the state before the first migration
* an offset like `+2` or `-1` will be interpreted relative to the latest currently applied migration
* specifying no identifier will default to the latest state (apply all migrations)

# Configuration

Configuration is stored inside of a `

1) 
1) Include 

# Required values

MIGRATION_DIR=example

Absolute or relative path to the directory holding the migration scripts.

DB_TYPE=psql

Database type.
Must be a supported DB provider.

# Optional values

GROUP_BY=none|month|year (default: none)

If set to "month" or "year", the migrations that it creates will be sorted into sub-folders inside of the MIGRATION_DIR.

# Provider-specific values

## PostgreSQL

DB_NAME=dbname
USERNAME=psql
PGPASSWORD=secret
HOSTNAME=localhost
