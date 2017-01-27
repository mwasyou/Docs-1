# Database configuration

By default, the database configuration file is located inside server directory `Databases\[DatabaseName]\[DatabaseName].db.config`

## Configuration options

Here are the most important database configuration options with their default values: 

1. Should edition libraries be loaded in databases:
`LoadEditionLibraries: true`

2. Should Json responses be wrapped in application name:
`WrapJsonInNamespaces: true`

3. Should applications be forced to register handlers starting with application name prefix:
`EnforceURINamespaces: false`

4. Should Json responses from multiple applications be merged:
`MergeJsonSiblings: true`

5. Should URI mapping (UriMapping.Map) be enabled:
`UriMappingEnabled: true`

6. Should URI ontology mapping (UriMapping.OntologyMap) be enabled:
`OntologyMappingEnabled: true`

7. Should the request filters be enabled (previously middleware filters):
`RequestFiltersEnabled: true`

8. Should static files HTTP responses have a special header `X-File-Path` that contains a full path to the actual file on the server (default value is `False`). This HTTP header is often useful for debugging purposes, but should be disabled in production:
`XFilePathHeader: true`

## Runtime changes

When codehost is running one can manipulate the above flags at runtime using a REST API. All should be called on system port (`8181` by default).

Getter for flags: `GET /sc/[DatabaseName]/GetFlag/[FlagName]`. For example:

```
http://localhost:8181/sc/default/GetFlag/WrapJsonInNamespaces
```

Setter for flags: `GET /sc/[DatabaseName]/SetFlag/[FlagName]/[BooleanValue]`. For example:

```
http://localhost:8181/sc/default/SetFlag/WrapJsonInNamespaces/True
```