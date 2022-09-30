## Meson Build for nlohmann_json_schema_validator
# Based on nlohmann json meson.build from v3.11.2
## @note If using this project as a meson subproject, it is expected that you 
# also have nlohmann jso in your project's subprojects directory

project('nlohmann_json_schema_validator', 'cpp')

srcs = files([
    'src/json-patch.cpp',
    'src/json-schema-draft7.json.cpp',
    'src/json-uri.cpp',
    'src/json-validator.cpp',
    'src/string-format-check.cpp',
])

incs = include_directories('src', 'src/nlohmann')
nlohmann_json_dep = subproject('json').get_variable('nlohmann_json_dep')
nlohmann_json_schema_validator_lib = library(
    'nlohmann_json_schema_validator',
    srcs,
    include_directories: incs,
    dependencies: nlohmann_json_dep,
)

nlohmann_json_schema_validator_dep = declare_dependency(
    include_directories: incs,
    link_with: nlohmann_json_schema_validator_lib
)