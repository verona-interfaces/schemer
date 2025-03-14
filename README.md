[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

# Verona Interfaces: Specification for Schemer

In order to understand Verona Interfaces, please go
to [Verona Interfaces Introduction](https://verona-interfaces.github.io)!

A Verona Schemer is a Html-file to be loaded into an iframe element of a web application. We call the web application "host". This specification describes the asynchronous communication between a host and the schemer.

Read the spec here:
* [Html-Document](https://verona-interfaces.github.io/schemer)
* [AsyncApi source yaml](schemerapi.yaml)

The schemer file must contain of one script tag for metadata as json-ld. The syntax and elements are described [here](https://verona-interfaces.github.io/intro/metadata).

## release notes

### 3.1.0
* add `no-value`, `json` and `coded` to variable types (apply [variable-info](https://github.com/verona-interfaces/variable-info) v1.3)

### 3.0.0
* change data type and content of `variables` property in `vosStartCommand` to match the data structure coming from editor
* drop `variables` in `vosSchemeChangedNotification`
* use GitHub actions to build the html file as GitHub page

### 2.0.0
* change data type and content of `variables` property in `vosSchemeChangedNotification`: Now, all variables are listed (base and derived) and no info is given but `id`, `label` and `page`

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
This api is written as [async api](https://www.asyncapi.com/de) yaml file. After committing to main branch, a GitHub action is triggered to build the html page. Don't forget to update the version and the release notes in `README.md`. Then, create an release.

If you like to check the html page before committing to main branch, 

* have an npm/node.js-environment installed
* check out the repo
* run `npm install`
* run the `generate` script in package.json.

After that, you can check `docs/index.html` in a browser. This file will be ignored by git.