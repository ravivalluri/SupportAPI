## Scripts

# Clone Repo and Install Dependencies

\$ git clone https://github.com/codebyravi/supportAPI.git && cd appCalls && git install

# Starts API endpoints on port 4000, or user defined port. Navigate to localhost:4000/api

\$ npm start

# Runs testing suite

\$ npm test

# Starts API with nodemon

\$ npm watch

# Creates bundle for frontend

\$ npm build

# Lints relevant .js files. Defined in .eslintrc.js

\$ npm lint

# Fix lint errors

\$ npm lint-fix

# PrettierJS

\$ npm pretty

# This module creates tables in MySQL database.

# Can be used to migrate to remote or local database

\$ npm migrate

# Populates the previously created tables with necessary data

\$ npm seed

# Runs testQuery.js. For testing the connection to the db.

\$ npm testdb

## Endpoints

### Base

`/`
Redirects to `/api`, where you can fill all of this information again.

### Healthcheck

`/healthcheck`

## Scoped Routes

The following routes are scoped to the `/api` base path, i.e., in order to hit `/buildings`, in your request, the uri must include the base, `/api/buildings`

### All Buildings

`/buildings`
This path returns an Array of building names.

```json
["willis", "john_hancock", "aon", "thompson", "bcbs"]
```

