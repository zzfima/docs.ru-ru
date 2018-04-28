---
title: Интеграция с System.Web.Routing
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c3a5b9965f63a9fc501025493b3a323013ea2a4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="systemwebrouting-integration"></a>Интеграция с System.Web.Routing
При размещении службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в службах IIS SVC-файл размещается в виртуальном каталоге. Этот SVC-файл указывает фабрику узла службы, которую необходимо использовать, а также класс, реализующий эту службу. При выполнении запросов к службе указывается SVC-файла в URI, например: http://contoso.com/EmployeeServce.svc. Для разработчиков служб REST такой тип URI не является оптимальным. URI для служб REST указывают определенный ресурс и обычно не имеют модулей. Функция интеграции <xref:System.Web.Routing> позволяет размещать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST, соответствующую URI-адресам без расширения. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] маршрутизации см. в разделе [маршрутизации ASP.NET](http://go.microsoft.com/fwlink/?LinkId=184660) и [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) образца.  
  
## <a name="using-systemwebrouting-integration"></a>Использование интеграции System.Web.Routing  
 Для использования функции интеграции <xref:System.Web.Routing> с помощью класса <xref:System.ServiceModel.Activation.ServiceRoute> создайте один или несколько маршрутов и добавьте их в <xref:System.Web.Routing.RouteTable> в файле Global.asax. Это маршруты указывают относительные URI, по которым отвечает служба. Следующий пример показывает, как это сделать.  
  
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
  
 Все запросы направляются по относительному URI, который начинается с Customers службы `Service`.  
  
 В файл Web.config необходимо добавить модуль `System.Web.Routing.UrlRoutingModule`, установить атрибут `runAllManagedModulesForAllRequests` в значение `true` и добавить обработчик `UrlRoutingHandler` в элемент`<system.webServer>`, как показано в следующем примере.  
  
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
  
 Это позволит загрузить модуль и обработчик, которые необходимы для маршрутизации. Дополнительные сведения см. в разделе [Маршрутизация](../../../../docs/framework/wcf/feature-details/routing.md). Необходимо также установить атрибут `aspNetCompatibilityEnabled` в значение `true` в элементе `<serviceHostingEnvironment>`, как показано в следующем примере.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 Класс, реализующий службу, должен соответствовать требованиям к совместимости ASP.NET, как показано в следующем примере.  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>См. также  
 [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Маршрутизация ASP.NET](http://go.microsoft.com/fwlink/?LinkId=184660)
