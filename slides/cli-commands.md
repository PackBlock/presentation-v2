# CLI Commands 

## Install Suitable Templates

```bash
pb install [template-name-1] \
           [template-name-2] \
           ...
```

## Create Project

```bash
pb new -n [project-name] \
       -t [template-name-1 template-name-2, ...] \
       -v [variable-name-1:variable-value-1 variable-name-2:variable-value-2 ...]
```

## Add model - Generate Boilerplate Code

```bash
pb model -n [model-name] \
         -t [model-type] \
         -v [variable-name-1:variable-value-1 variable-name-2:variable-value-2 ...] \
         -p [property-1-name]:[property-1-type] \
            [property-2-name]:[property-2-type] \
            [parent-model-id]:[parent-model-id-type]:[parent-model-display-property] \
            ... 
```