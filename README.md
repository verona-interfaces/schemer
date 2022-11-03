[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
# Verona Interfaces: Specification for Schemer

In order to understand Verona Interfaces, please go
to [Verona Interfaces Introduction](https://github.com/verona-interfaces/introduction)!

A Verona Schemer is a Html-file to be loaded into an iframe element of a web application. We call the web application "host". This specification describes the asynchronous communication between a host and the schemer.

Read the spec here:
* [Html-Document](https://verona-interfaces.github.io/schemer)
* [Markdown-Document](docs/asyncapi.md)
* [AsyncApi source yaml](api/schemerapi.yaml)

The schemer file must contain of one script tag for metadata as json-ld. The syntax and elements are described [here](https://github.com/verona-interfaces/metadata).

## release notes
### 1.1.0
* add `dependenciesToCode` to announce requirements for the coding process
* add `schemerConfig` again for `directDownloadUrl` to get additional code from the hosting server

### 1.0.0
* drop `vosGetSchemeRequest`: The schemer sends all data on every `vosSchemeChangedNotification`
* drop `schemerConfig` in `vosStartCommand`, because there is no need for `definitionReportPolicy` anymore 
* add `variables` to `vosSchemeChangedNotification` to send list of derived variables

### 0.1
* first draft

## For Contributors
The api is written as [async api](https://www.asyncapi.com) yaml file. After editing, we create markdown and html files for better reading.

To ease that post-processing, we use [node.js](https://nodejs.org). The repo contains a package.json. By running `npm install` you get the tool `@asyncapi/generator` and two templates. Run `npm run ag` to recreate html and markdown representations of the api.
