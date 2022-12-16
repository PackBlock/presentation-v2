
<div class='left'>

<h3>Inline Templating - Existing Code</h3>

```cs {4-5|10-11|12-14|all}
using Microsoft.AspNetCore.Mvc;
using PbProject;
using PbProject.PackBlock.Swagger;
/* Pb-Using Begin */
/* Pb-Using End */
var appBuilder = WebApplication.CreateBuilder(args);
var services = appBuilder.Services;
services.AddControllers();
services.AddEndpointsApiExplorer();
/* Pb-Registration Begin */
/* Pb-Registration End */
#region Pb-Exclude
// codes in this region would not be in template
#endregion
services.AddHttpContextAccessor();
```

<h3>Inline Template</h3>

```cs {0|2-3|5|all}
//Pb-Using%insert-if-not-exist
using {{Pb.ProjectName}}.{{Pb.CrudFolder}}.Services.Contracts;
using {{Pb.ProjectName}}.{{Pb.CrudFolder}}.Services.Implementations;
//Pb-Registration
services.AddScoped<I{{Pb.ModelName}}HttpService, {{Pb.ModelName}}HttpService>();
```

</div>

::right::

<h3 class='right'>Output</h3>

<div class='right'>

```cs {0|4-7|12-14|all}
using Microsoft.AspNetCore.Mvc;
using ToDoApp;
using ToDoApp.PackBlock.Swagger;
/* Pb-Using Begin */
using ToDoApp.TaskFeature.Services.Contracts;
using ToDoApp.TaskFeature.Services.Implementations;
/* Pb-Using End */
var appBuilder = WebApplication.CreateBuilder(args);
var services = appBuilder.Services;
services.AddControllers();
services.AddEndpointsApiExplorer();
/* Pb-Registration Begin */
services.AddScoped<ICategoryHttpService, CategoryHttpService>();
/* Pb-Registration End */
services.AddHttpContextAccessor();
```
<div class='description'>

Special comment blocks is placeholders for future code generations, should preserved in application code.

</div>

</div>

<style>

.left {
    @apply
    pr-5
}

.right {
    @apply
    pl-5
}

.description {
    @apply
    place-items-center
}

</style>