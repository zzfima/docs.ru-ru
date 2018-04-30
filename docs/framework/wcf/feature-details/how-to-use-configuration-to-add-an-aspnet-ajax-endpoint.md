---
title: Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28051dbed626dc0073a38e72f2cdc21ea108a32e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать службу, предоставляющую доступ к конечной точке с поддержкой ASP.NET AJAX, которую можно вызвать из кода JavaScript на клиентском веб-сайте. Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]), либо методом, не требующим каких-либо элементов конфигурации. В этом разделе показано выполнение этой задачи с помощью файла конфигурации.  
  
 Часть процедуры, которая позволяет конечной точке службы становятся поддержкой ASP.NET AJAX состоит в настройке конечной точки, чтобы использовать <xref:System.ServiceModel.WebHttpBinding> и добавление [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведения конечной точки. После того как конечная точка сконфигурирована, действия по реализации и размещению службы аналогичны выполняемым для любой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Рабочий пример см. в разделе [AJAX службы с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Дополнительные сведения о том, как настроить конечную точку ASP.NET AJAX без использования конфигурации см. в разделе [как: Добавление ASP.NET AJAX конфигурации конечной точки без с помощью](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1.  Определите контракт базовой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью интерфейса, помеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>Создание конечной точки ASP.NET AJAX для службы  
  
1.  Создать конфигурацию поведения и указать [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение для конечные точки службы с поддержкой ASP.NET AJAX.  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2.  Создайте конечную точку для службы, использующую <xref:System.ServiceModel.WebHttpBinding> и поведение ASP.NET AJAX, определенное на предыдущем шаге.  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
### <a name="to-host-the-service-in-iis"></a>Размещение службы в IIS  
  
1.  Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC. Измените этот файл, добавив соответствующие [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив сведения о службе. Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  Дополнительные сведения о размещении в IIS см. в разделе [как: размещение службы WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Вызов службы  
  
1.  Конечная точка настраивается с пустым адресом относительно SVC-файла, поэтому служба становится доступной и может быть вызвана отправкой запросов на service.svc/\<операции > — Например, service.svc/Add для `Add` операции. Для этого укажите URL-адрес конечной точки в коллекции "Скрипты" в диспетчере скриптов ASP.NET AJAX. Пример см. в разделе [AJAX службы с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>См. также  
 [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
