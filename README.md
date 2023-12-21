# BigChange OpenAPI Linting Rules
## Introduction
The repository provides [BigChange's OpenAPI linting rules](https://raw.githubusercontent.com/BigChangeApps/openapi-linting/main/rest/.spectral.yaml) and serves as a companion to our REST style guide (currently held internally). [Spectral](https://docs.stoplight.io/docs/spectral) is a command-line tool that is can lint [OpenAPI specifications](https://swagger.io/specification/), used to streamline adoption of our standards and provide a first-class integration experience for developers.
## Installation
Spectral requires Node version 14 or later:
```
yarn global add @stoplight/spectral-cli
```
## Usage

### Remote ruleset
You can apply these rules by providing the URL directly on the command line:
```
spectral lint -r https://raw.githubusercontent.com/BigChangeApps/openapi-linting/main/rest/.spectral.yaml petstore.yaml
```
### Local ruleset
For added flexibility and the ability to extend the ruleset we provide, we recommend that you create a local spectral ruleset (.spectral.yml) that remotely references this one:
```
extends: 
- https://raw.githubusercontent.com/BigChangeApps/openapi-linting/main/rest/.spectral.yaml 

rules:
 response-fail-support-problem-json: off
 schema-properties-documentation-missing: warn
```

