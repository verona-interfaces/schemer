Since version 3.2, every new release is published with a tag. This tag carries release notes, so there is no need to add release notes to the README.md anymore. The list below is the copy of old release notes.

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
