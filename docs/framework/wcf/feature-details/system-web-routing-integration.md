---
title: Интеграция с System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: a80b5c3b336b4fd18b347a25ceaf509baf6461b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184396"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="08489-102">Интеграция с System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="08489-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="08489-103">При хостинге службы Windows Communication Foundation (WCF) в Информационном сервисе Интернета (IIS) вы размещаете файл .svc в виртуальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="08489-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="08489-104">Этот SVC-файл указывает фабрику узла службы, которую необходимо использовать, а также класс, реализующий эту службу.</span><span class="sxs-lookup"><span data-stu-id="08489-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="08489-105">При запросах в службу вы указываете файл .svc `http://contoso.com/EmployeeServce.svc`в URI, например: .</span><span class="sxs-lookup"><span data-stu-id="08489-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="08489-106">Для разработчиков служб REST такой тип URI не является оптимальным.</span><span class="sxs-lookup"><span data-stu-id="08489-106">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="08489-107">URI для служб REST указывают определенный ресурс и обычно не имеют модулей.</span><span class="sxs-lookup"><span data-stu-id="08489-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="08489-108">Функция <xref:System.Web.Routing> интеграции позволяет разместить wCF REST службы, которая реагирует на URIs без расширения.</span><span class="sxs-lookup"><span data-stu-id="08489-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="08489-109">Для получения дополнительной информации о разгроме смотрите [ASP.NET.](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="08489-109">For more information about routing see [ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="08489-110">Использование интеграции System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="08489-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="08489-111">Для использования возможности интеграции <xref:System.Web.Routing> с помощью класса <xref:System.ServiceModel.Activation.ServiceRoute> создайте один или несколько маршрутов и добавьте их в <xref:System.Web.Routing.RouteTable> в файле Global.asax.</span><span class="sxs-lookup"><span data-stu-id="08489-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="08489-112">Это маршруты указывают относительные URI, по которым отвечает служба.</span><span class="sxs-lookup"><span data-stu-id="08489-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="08489-113">В приведенном ниже примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="08489-113">The following example shows how to do this.</span></span>  
  
```aspx-csharp  
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
  
 <span data-ttu-id="08489-114">Все запросы направляются по относительному URI, который начинается с Customers службы `Service`.</span><span class="sxs-lookup"><span data-stu-id="08489-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="08489-115">В файл Web.config необходимо добавить модуль `System.Web.Routing.UrlRoutingModule`, установить атрибут `runAllManagedModulesForAllRequests` в значение `true` и добавить обработчик `UrlRoutingHandler` в элемент`<system.webServer>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="08489-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="08489-116">Это позволит загрузить модуль и обработчик, которые необходимы для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="08489-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="08489-117">Дополнительные сведения см. в разделе [Маршрутизация](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="08489-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="08489-118">Необходимо также установить атрибут `aspNetCompatibilityEnabled` в значение `true` в элементе `<serviceHostingEnvironment>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="08489-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="08489-119">Класс, реализующий службу, должен соответствовать требованиям к совместимости ASP.NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="08489-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="08489-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="08489-120">See also</span></span>

- [<span data-ttu-id="08489-121">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="08489-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- <span data-ttu-id="08489-122">[Маршрутизация ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="08489-122">[ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
