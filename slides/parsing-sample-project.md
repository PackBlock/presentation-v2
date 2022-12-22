# Parsing Template

Our tool read sample projects and create templates by replacing all special symbols as template variables.

```sh {1-2|3|4|all}
create -i /Users/ac/src/api-http-service-sample \       # Input, sample project
       -o /Users/ac/src/api-httpservice \               # Output, generated template
       -m Crud Search \                                 # Model list
       -v CrudFolder SearchFolder                       # Variable list
```

This command will process and apply the following rules;

| **Name**     | **Sample Project** (Search) | **Template Source** (Replace) | **CLI Argument**                  |
|--------------|-----------------------------|-------------------------------|-----------------------------------|
| Project Name | PbProject                   | { {Pb.ProjectName} }          | ---n ToDoApp                      |
| Crud         | **PbModel**Crud             | { {Pb.ModelName} }            | ---type Crud                      |
| Search       | **PbModel**Search           | { {Pb.ModelName} }            | ---type Search                    |
| CrudFolder   | **PbVar**CrudFolder         | { {Pb.CrudFolder} }           | ---variables CrudFolder:[value]   |
| SearchFolder | **PbVar**SearchFolder       | { {Pb.SearchFolder} }         | ---variables SearchFolder:[value] |
