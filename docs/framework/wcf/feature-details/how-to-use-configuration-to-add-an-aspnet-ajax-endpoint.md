---
title: Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 5314bb000371ee2d3eef2576e1edfa455aa65b90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184833"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
Фонд связи Windows (WCF) позволяет создать сервис, который делает доступ к ASP.NET токс-с поддержкой AJAX, которая может быть вызвана из JavaScript на веб-сайте клиента. Для создания такой конечной точки можно либо использовать файл конфигурации, как и все другие конечные точки Windows Communication Foundation (WCF), либо использовать метод, который не требует элементов конфигурации. В этом разделе показано выполнение этой задачи с помощью файла конфигурации.  
  
 Часть процедуры, которая позволяет конечной точке службы стать ASP.NET с поддержкой <xref:System.ServiceModel.WebHttpBinding> AJAX, состоит в настройке конечной точки для использования и добавлении [ \<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение конечной точки. После настройки конечной точки шаги по реализации и размещению службы аналогичны тем, которые используются любой службой WCF. В рабочем примере см. [службу AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Для получения дополнительной информации о том, как настроить конечную точку ASP.NET AJAX без использования конфигурации, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
  
## <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1. Определите базовый контракт службы WCF <xref:System.ServiceModel.ServiceContractAttribute> с интерфейсом, отмеченным атрибутом. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>Создание конечной точки ASP.NET AJAX для службы  
  
1. Создайте конфигурацию поведения и укажите [ \<поведение enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) для ASP.NET конечных точек службы с поддержкой AJAX.  
  
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
  
2. Создайте конечную точку для службы, использующую <xref:System.ServiceModel.WebHttpBinding> и поведение ASP.NET AJAX, определенное на предыдущем шаге.  
  
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
  
## <a name="to-host-the-service-in-iis"></a>Размещение службы в IIS  
  
1. Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC. Отобразите этот файл, добавив соответствующую [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивную информацию ServiceHost для службы. Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.  
  
    ```
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. Для получения дополнительной информации о хостинге в IIS, [см.](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
  
## <a name="to-call-the-service"></a>Вызов службы  
  
1. Конечная точка настроена по пустому адресу по отношению к файлу .svc, поэтому служба теперь доступна\<и может быть вызвана, отправив `Add` запросы на service.svc/> операции - например, service.svc/Add для операции. Для этого укажите URL-адрес конечной точки в коллекции "Скрипты" в диспетчере скриптов ASP.NET AJAX. Например, см. [службу AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>См. также раздел

- [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
