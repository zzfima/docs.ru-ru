---
title: Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 3ccfb34614707c17885da3ed37f545bbab808869
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978264"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
Windows Communication Foundation (WCF) позволяет создать службу, которая делает доступной конечную точку ASP.NET с поддержкой AJAX, которую можно вызывать из JavaScript на веб-сайте клиента. Чтобы создать такую конечную точку, можно использовать файл конфигурации, как и для всех остальных конечных точек Windows Communication Foundation (WCF), или использовать метод, который не требует каких-либо элементов конфигурации. В этом разделе показано выполнение этой задачи с помощью файла конфигурации.  
  
 Часть процедуры, включающая конечную точку службы, ASP.NET с поддержкой AJAX, состоит в настройке конечной точки для использования <xref:System.ServiceModel.WebHttpBinding> и добавлении [\<ного](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведения конечной точки >. После настройки конечной точки действия по внедрению и размещению службы похожи на те, которые используются любой службой WCF. Рабочий пример см. в разделе [Служба AJAX, использующая HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Дополнительные сведения о настройке конечной точки ASP.NET AJAX без использования конфигурации см. [в разделе инструкции. Добавление конечной точки ASP.NET AJAX без использования конфигурации](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
## <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1. Определите базовый контракт службы WCF с интерфейсом, помеченным атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
1. Создайте конфигурацию поведения и укажите [\<енаблевебскрипт >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведением для конечных точек службы ASP.NET с поддержкой AJAX.  
  
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
  
1. Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC. Измените этот файл, добавив соответствующие сведения об директиве [ServiceHost\@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) для службы. Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.  
  
    ```
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. Дополнительные сведения о размещении в службах IIS см. в разделе [как разместить службу WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="to-call-the-service"></a>Вызов службы  
  
1. Конечная точка настраивается по пустому адресу относительно SVC-файла, поэтому служба доступна и может быть вызвана при отправке запросов к службе. svc/\<операции > (например, Service. svc/Add для `Add` операции). Для этого укажите URL-адрес конечной точки в коллекции "Скрипты" в диспетчере скриптов ASP.NET AJAX. Пример см. в разделе [Служба AJAX, использующая HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>См. также

- [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
