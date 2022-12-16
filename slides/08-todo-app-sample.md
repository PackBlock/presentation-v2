# Todo App Sample

<div>
As a proof of concept, we have developed one backend and one frontend template for a sample Todo App. 

For these templates, developer only needed to execute these commands to accomplish a basic CRUD operations. Developer own the source code and may require to refactor the template defaults. 

</div>

```bash
pb install api-httpservice react-ant-pro              # install these two example templates
```

```bash
pb new -n ToDoApp -t api-httpservice react-ant-pro    # scaffold project with these templates
```

```bash
pb model -n Category \                                # Entity name       
         -t crud \                                    # Model type, could be many different model generation template
         -v CrudFolder:TaskManagement \               # Dynamic variables defined in the template, key:value
         -p Name:string                               # Model property list. [property name]:[type identifier]
```

```bash
pb model -n TaskItem                                  # Entity name
         -t crud                                      # Model type, could be many different model generation template
         -v CrudFolder:TaskManagement \               # Dynamic variables defined in the template, key:value
         -p Name:string \                             # Simple property
            CategoryId:int:Name                       # Foreign key property with a variable to display name propery
```