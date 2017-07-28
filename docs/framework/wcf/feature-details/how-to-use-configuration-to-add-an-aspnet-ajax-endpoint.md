---
title: "Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать службу, предоставляющую доступ к конечной точке с поддержкой ASP.NET AJAX, которую можно вызвать из кода JavaScript на клиентском веб\-сайте.Для создания этой конечной точки можно воспользоваться либо файлом конфигурации \(как и для всех остальных конечных точек [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\), либо методом, не требующим каких\-либо элементов конфигурации.В этом разделе показано выполнение этой задачи с помощью файла конфигурации.  
  
 Часть процедуры, обеспечивающей поддержку ASP.NET AJAX конечной точкой, заключается в том, чтобы указать в конфигурации этой конечной точки использование <xref:System.ServiceModel.WebHttpBinding> и добавить ей поведение [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md).После того как конечная точка сконфигурирована, действия по реализации и размещению службы аналогичны выполняемым для любой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Рабочий пример см. в разделе [Служба AJAX с использованием HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] настройке конечной точки с поддержкой ASP.NET AJAX без применения файла конфигурации см. в разделе [Как добавить конечную точку ASP.NET AJAX без использования конфигурации](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### Создание базовой службы WCF  
  
1.  Определите контракт базовой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
3.  Определите пространство имен для реализации классов `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### Создание конечной точки ASP.NET AJAX для службы  
  
1.  Создайте конфигурацию поведения и укажите поведение [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) для конечных точек службы, поддерживающих ASP.NET AJAX.  
  
    ```  
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
  
    ```  
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
  
### Размещение службы в IIS  
  
1.  Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC.Измените этот файл, добавив надлежащую информацию директивы [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) об этой службе.Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] размещении служб в IIS см. в разделе [Как разместить службу WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### Вызов службы  
  
1.  Конечная точка настраивается по пустому адресу, заданному относительно SVC\-файла, поэтому служба становится доступной и может быть вызвана отправкой запросов на service.svc\/\<operation\> \(например, service.svc\/Add для операции `Add`\).Для этого укажите URL\-адрес конечной точки в коллекции «Скрипты» в диспетчере скриптов ASP.NET AJAX.Пример см. в разделе [Служба AJAX с использованием HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## См. также  
 [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Практическое руководство. Миграция веб\-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)