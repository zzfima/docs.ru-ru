---
title: Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 3a3474dc04ce2cda63157e68597d1184e9b2bf15
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878887"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
Windows Communication Foundation (WCF) позволяет создавать службу, использующую с поддержкой ASP.NET AJAX конечной точки доступны, который может вызываться из JavaScript на веб-сайта клиента. Чтобы создать такой конечной точки, можно использовать файл конфигурации, как и для всех остальных конечных точек службы Windows Communication Foundation (WCF), или использовать метод, который не требует никаких элементов конфигурации. В этом разделе показано выполнение этой задачи с помощью файла конфигурации.  
  
 Часть процедуры, которая позволяет конечной точке службы становятся с поддержкой ASP.NET AJAX заключается в настройке конечная точка, используемая <xref:System.ServiceModel.WebHttpBinding> и добавить [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение конечной точки. После настройки конечной точки, действия по реализации и размещению службы аналогичны используется службой WCF. Рабочий пример см. в разделе [служба AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Дополнительные сведения о том, как настроить конечную точку ASP.NET AJAX без использования конфигурации см. в разделе [как: Добавление ASP.NET AJAX конфигурации конечной точки без с помощью](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1.  Определение основных контракта службы WCF с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute> атрибута. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
1.  Создать конфигурацию поведения и указать [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение с поддержкой ASP.NET AJAX конечные точки службы.  
  
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
  
1.  Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC. Измените этот файл, добавив соответствующие [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) информацию директивы для службы. Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  Дополнительные сведения о размещении в IIS, см. в разделе [как: размещение службы WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Вызов службы  
  
1.  Конечная точка настраивается с пустым адресом относительно SVC-файла, поэтому служба становится доступной и может быть вызвана отправкой запросов на service.svc/\<операции >, например, service.svc/Add для `Add` операции. Для этого укажите URL-адрес конечной точки в коллекции "Скрипты" в диспетчере скриптов ASP.NET AJAX. Например, см. в разделе [служба AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>См. также  
 [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
