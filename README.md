
# Purpose
To guide and make it easy to setup one's coding environment on a new machine (macOS in this case).

# Scope
This guide covers the basic installation only. Project specific installation will be covered in each project separately.

# Usage
This guide mainly contains self-serve scripts which you can run to get the system setup on your local.
This guide has not been tested thoroughly, so you may find some errors.
We recommend to only install things you require for your project.

# Tools

## Basic Setup
The basic tools we need for all projects:
- xCode (macOS dependency)
- Homebrew (packagae manager)

You can install this using this script:
```
scripts/setup.sh
```

## asdf 
We are using asdf as our runtime version manager for these languages:
- python
- nodejs

Refer [Setting Up asdf](./asdf.md)

## Nodejs
Nodejs installed using asdf.
Refer [Setting Up nodejs](./nodejs.md)


## Python
Python installed using asdf.
Refer [Setting Up python](./python.md)


## Java
Install using IntelliJ Community Edition.
https://www.jetbrains.com/idea/download/other.html 


## Postgres
To install and start postgres (assuming version 18)
```
brew install postgresql@18
brew services start postgresql@18
```

To add psql to PATH:
```
echo 'export PATH="/opt/homebrew/opt/postgresql@18/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

To install postGIS (may take some time - you've been warned!)
```
brew install postgis
```
Homebrew automatically builds PostGIS against your installed PostgreSQL version.

Testing PostGIS:
```
createdb geodb
psql geodb
```
Inside psql:
```
CREATE EXTENSION postgis;
SELECT PostGIS_Version();
```

For a GUI to access the database we recommend Postico: https://eggerapps.at/postico2/
