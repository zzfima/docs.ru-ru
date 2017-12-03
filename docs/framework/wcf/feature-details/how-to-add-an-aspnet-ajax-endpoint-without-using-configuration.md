---
title: "Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5369fd0520529aa9403c3909233cced66e0fcff1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать службу, предоставляющую конечную точку с поддержкой ASP.NET AJAX, которую можно вызвать из кода JavaScript на веб-сайте клиента. Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации. В этом разделе показано решение этой задачи вторым методом.  
  
 Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS. Чтобы активировать конечную точку ASP.NET AJAX этот подход, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> как параметр фабрики в [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивы в файле .svc. Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.  
  
 Рабочий пример см. в разделе [службы AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Описание того, как настроить конечную точку ASP.NET AJAX с помощью элементов конфигурации, в разделе [как: использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1.  Определите контракт базовой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью интерфейса, помеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp  
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
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Размещение службы в службах IIS без конфигурации  
  
1.  Создайте в приложении новый файл с именем "service" и расширением .svc. Измените этот файл, добавив соответствующие [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив сведения о службе. Указать, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> будет использоваться в [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директиву, чтобы автоматически настроить конечную точку ASP.NET AJAX.  
  
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
  
1.  Конечная точка настраивается с пустым адресом относительно SVC-файла, поэтому служба становится доступной и может быть вызвана отправкой запросов на service.svc/\<операции > — Например, service.svc/Add для `Add` операции. Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX. Пример см. в разделе [службы AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Пример  
  
 Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса. Этот метод также допускает добавление и использование файла конфигурации. Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.  
  
 Например, service.svc использует фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, а в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью привязки <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу "soap". В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).  
  
 Если файл конфигурации определяет конечную точку по пустому относительному адресу и используется фабрика узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, создается исключение, происходит сбой запуска службы.  
  
 С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки. При необходимости изменить какой-либо параметр (например, квоту средств чтения) не следует использовать метод без конфигурации, т. е. удалять фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.  
  
 Если службе требуется режим совместимости с ASP.NET (например, если служба использует класс <xref:System.Web.HttpContext> или механизмы авторизации ASP.NET), для включения этого режима все равно понадобится файл конфигурации. Элемент конфигурации, необходимый — [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который необходимо добавить следующим образом.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) раздела.  
  
 Класс <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> наследуется от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>. Подробное описание механизма фабрики узла службы см. в разделе [расширение ServiceHostFactory размещения с помощью](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Создание службы WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Как: миграция с поддержкой AJAX веб-служб ASP.NET в WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
