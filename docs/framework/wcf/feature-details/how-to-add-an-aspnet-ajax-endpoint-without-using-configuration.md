---
title: "Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать службу, предоставляющую конечную точку с поддержкой ASP.NET AJAX, которую можно вызвать из кода JavaScript на веб-сайте клиента. Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации. В этом разделе показано решение этой задачи вторым методом.  
  
 Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS. Чтобы активировать конечную точку ASP.NET AJAX с помощью такого подхода, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> фабрики в качестве параметра [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивы в файле .svc. Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.  
  
 Рабочий пример см. в разделе [службы AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Общие сведения о настройке конечной точки ASP.NET AJAX с помощью элементов конфигурации в разделе [Практическое руководство: использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1.  Определение базового [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] контракт службы с помощью интерфейса, отмеченные <xref:System.ServiceModel.ServiceContractAttribute> атрибута. Пометьте каждую операцию с <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> свойство.  
  
    ```  
    [ServiceContract(Namespace = "MyService")]]  
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
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Размещение службы в службах IIS без конфигурации  
  
1.  Создайте в приложении новый файл с именем "service" и расширением .svc. Изменить этот файл, добавив соответствующие [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) информацию директивы для службы. Указывает, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> будет использоваться в [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директива для автоматической настройки конечной точки ASP.NET AJAX.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  Создайте службу и вызовите ее из клиента. Internet Information Services (IIS) активирует данную службу при вызове. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Размещение в службах IIS, в разделе [как: размещение службы WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Вызов службы  
  
1.  Конечная точка настраивается с пустым адресом относительно SVC-файла, поэтому служба доступна и может быть вызвана отправкой запросов на service.svc/<> \</> \> — например, service.svc/Add для `Add` операции. Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX. Например, в разделе [службы AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Пример  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса. Этот метод также допускает добавление и использование файла конфигурации. Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.  
  
 Например, service.svc использует <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> и в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу «soap». В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).  
  
 Если файл конфигурации определяет конечную точку по пустому адресу, относительный и <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> — используется, создается исключение, и происходит сбой запуска службы.  
  
 С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки. Если ни один параметр (например, квоту средств чтения) должен быть изменен, нельзя использовать подход без конфигурации, удалив <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.  
  
 Если службе требуется режим совместимости с ASP.NET — например, если он использует <xref:System.Web.HttpContext> необходим класс или механизмы авторизации ASP.NET - файл конфигурации для включения этого режима. Необходимый элемент конфигурации — [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который необходимо добавить следующим образом.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled=”true” /> </system.serviceModel>`  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) раздела.  
  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> класс является производным от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>. Подробное описание механизма фабрики узла службы см. в разделе [расширение ServiceHostFactory размещения с помощью](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Создание службы WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Практическое руководство: миграция с поддержкой AJAX веб-служб ASP.NET в WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)