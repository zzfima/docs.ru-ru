---
title: Интеграция с System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 5bd405d66dcad597bbe6f452703d25372fdb7682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="c1424-102">Интеграция с System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="c1424-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="c1424-103">При размещении службы Windows Communication Foundation (WCF) в Internet Information Service (IIS) можно разместить SVC-файла в виртуальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="c1424-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="c1424-104">Этот SVC-файл указывает фабрику узла службы, которую необходимо использовать, а также класс, реализующий эту службу.</span><span class="sxs-lookup"><span data-stu-id="c1424-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="c1424-105">При выполнении запросов к службе указывается SVC-файла в URI, например: http://contoso.com/EmployeeServce.svc.</span><span class="sxs-lookup"><span data-stu-id="c1424-105">When making requests to the service you specify the .svc file in the URI, for example: http://contoso.com/EmployeeServce.svc.</span></span> <span data-ttu-id="c1424-106">Для разработчиков служб REST такой тип URI не является оптимальным.</span><span class="sxs-lookup"><span data-stu-id="c1424-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="c1424-107">URI для служб REST указывают определенный ресурс и обычно не имеют модулей.</span><span class="sxs-lookup"><span data-stu-id="c1424-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="c1424-108"><xref:System.Web.Routing> Средство интеграции позволяет разместить службу WCF REST, соответствующую URI-адресам без расширения.</span><span class="sxs-lookup"><span data-stu-id="c1424-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="c1424-109">Дополнительные сведения о маршрутизации см. в разделе [маршрутизации ASP.NET](http://go.microsoft.com/fwlink/?LinkId=184660) и [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) образца.</span><span class="sxs-lookup"><span data-stu-id="c1424-109">For more information about routing see [ASP.NET Routing](http://go.microsoft.com/fwlink/?LinkId=184660) and the [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) sample.</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="c1424-110">Использование интеграции System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="c1424-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="c1424-111">Для использования функции интеграции <xref:System.Web.Routing> с помощью класса <xref:System.ServiceModel.Activation.ServiceRoute> создайте один или несколько маршрутов и добавьте их в <xref:System.Web.Routing.RouteTable> в файле Global.asax.</span><span class="sxs-lookup"><span data-stu-id="c1424-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="c1424-112">Это маршруты указывают относительные URI, по которым отвечает служба.</span><span class="sxs-lookup"><span data-stu-id="c1424-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="c1424-113">Следующий пример показывает, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="c1424-113">The following example shows how to do this.</span></span>  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
```  
  
 <span data-ttu-id="c1424-114">Все запросы направляются по относительному URI, который начинается с Customers службы `Service`.</span><span class="sxs-lookup"><span data-stu-id="c1424-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="c1424-115">В файл Web.config необходимо добавить модуль `System.Web.Routing.UrlRoutingModule`, установить атрибут `runAllManagedModulesForAllRequests` в значение `true` и добавить обработчик `UrlRoutingHandler` в элемент`<system.webServer>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c1424-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 <span data-ttu-id="c1424-116">Это позволит загрузить модуль и обработчик, которые необходимы для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c1424-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="c1424-117">Дополнительные сведения см. в разделе [Маршрутизация](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="c1424-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="c1424-118">Необходимо также установить атрибут `aspNetCompatibilityEnabled` в значение `true` в элементе `<serviceHostingEnvironment>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c1424-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="c1424-119">Класс, реализующий службу, должен соответствовать требованиям к совместимости ASP.NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c1424-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1424-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c1424-120">See Also</span></span>  
 [<span data-ttu-id="c1424-121">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="c1424-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="c1424-122">Маршрутизация ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c1424-122">ASP.NET Routing</span></span>](http://go.microsoft.com/fwlink/?LinkId=184660)
