
<div class='left'>

# Example project

```cs {1-4|7|8-19|all}
using PbProject.PbVarCrudFolder.Models;
using PbProject.PbVarCrudFolder.Services.Contracts;

namespace PbProject.PbVarCrudFolder.Controllers;

[ApiController]
[Route("pbVarCrudFolder/[controller]")]
public class PbModelCrudController : ControllerBase
{
    private readonly IPbModelCrudHttpService _httpService;

    public PbModelCrudController(IPbModelCrudHttpService httpService)
    {
        _httpService = httpService;
    }

    [HttpPost]
    [ProducesResponseType(typeof(PbModelCrudViewModel), (int)HttpStatusCode.Created)]
    public Task<IActionResult> Post(PbModelCrudPostRequest request)
    {
        return _httpService.Post(request);
    }
```

</div>

::right::

<h1 class='right'>Generated Template</h1>

<div class='right'>

```cs {0|1-4|7|8-19|all}
using {{Pb.ProjectName}}.{{Pb.CrudFolder}}.Models;
using {{Pb.ProjectName}}.{{Pb.CrudFolder}}.Services.Contracts;

namespace {{Pb.ProjectName}}.{{Pb.CrudFolder}}.Controllers;

[ApiController]
[Route("{{Pb.crudFolder}}/[controller]")]
public class {{Pb.ModelName}}Controller : ControllerBase
{
    private readonly I{{Pb.ModelName}}HttpService _httpService;
    
    public {{Pb.ModelName}}Controller(I{{Pb.ModelName}}HttpService httpService)
    {
        _httpService = httpService;
    }
    
    [HttpPost]
    [ProducesResponseType(typeof({{Pb.ModelName}}ViewModel), (int)HttpStatusCode.Created)]
    public Task<IActionResult> Post({{Pb.ModelName}}PostRequest request)
    {
        return _httpService.Post(request);
    }
}
```

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

</style>