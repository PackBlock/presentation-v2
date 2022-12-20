# Parsing Template

Our tool read sample projects and create templates by replacing all special symbols as template variables.

```sh
create -i /Users/ac/src/api-http-service-sample \       # Input, sample project
       -o /Users/ac/src/api-httpservice \               # Output, generated template
       -m Crud Search \                                 # Model list
       -v CrudFolder SearchFolder                       # Variable list
```

This command will process and apply the following rules;

| **Name**     | **Search**        | **Replace**           | **CLI Argument**                  |
|--------------|-------------------|-----------------------|-----------------------------------|
| Project Name | PbProject         | { {Pb.ProjectName} }  | ---n ToDoApp                      |
| Crud         | PbModelCrud       | { {Pb.ModelName} }    | ---type Crud                      |
| Search       | PbModelSearch     | { {Pb.ModelName} }    | ---type Search                    |
| CrudFolder   | PbVarCrudFolder   | { {Pb.CrudFolder} }   | ---variables CrudFolder:[value]   |
| SearchFolder | PbVarSearchFolder | { {Pb.SearchFolder} } | ---variables SearchFolder:[value] |
