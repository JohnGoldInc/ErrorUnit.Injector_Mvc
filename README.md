# ErrorUnit.Injector_Mvc
Documentation on using ErrorUnit Mvc ActionFilter to instrument calls

To catch MVC Errors add to the `FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters)` method that is called by Global.asax.cs Application_Start method the code:
`filters.Add(new ErrorUnit.Attributes.ErrorUnitActionFilterAttribute());`
## Examples
So the full code for the FilterConfig class in you App_Start folder should look like:
```
using System.Web;
using System.Web.Mvc;

public class FilterConfig
{
   public static void RegisterGlobalFilters(GlobalFilterCollection filters)
   {
       filters.Add(new ErrorUnit.Attributes.ErrorUnitMvcActionFilterAttribute());
       //anything else ...
   }
}
```
