---
title: Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9935e2a7738796fff9a037b09237a6acbf7bf988
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185136"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
Фонд связи Windows (WCF) позволяет создать сервис, который предоставляет ASP.NET топовой с поддержкой AJAX, которая может быть вызвана из JavaScript на веб-сайте клиента. Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации. В этом разделе показано решение этой задачи вторым методом.  
  
 Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS. Чтобы активировать ASP.NET конечную точку <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> AJAX с помощью этого подхода, укажите параметр Factory в директиве [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) в файле .svc. Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.  
  
 В рабочем примере см. [службу AJAX без конфигурации.](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)  
  
 Для набросков того, как настроить конечную точку ASP.NET AJAX с использованием элементов конфигурации, [см. Как: Используйте конфигурацию для добавления ASP.NET конечной точки AJAX.](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
  
### <a name="to-create-a-basic-wcf-service"></a>Создание базовой службы WCF  
  
1. Определите базовый контракт службы WCF <xref:System.ServiceModel.ServiceContractAttribute> с интерфейсом, отмеченным атрибутом. Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>. Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
2. Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Размещение службы в службах IIS без конфигурации  
  
1. Создайте в приложении новый файл с именем "service" и расширением .svc. Отобразите этот файл, добавив соответствующую [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивную информацию ServiceHost для службы. Укажите, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> что это должно использоваться в директиве [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) для автоматической настройки ASP.NET конечную точку AJAX.  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Создайте службу и вызовите ее из клиента. Internet Information Services (IIS) активирует данную службу при вызове. Для получения дополнительной информации о хостинге в IIS, [см.](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
  
### <a name="to-call-the-service"></a>Вызов службы  
  
1. Конечная точка настроена по пустому адресу по отношению к файлу .svc, поэтому служба теперь доступна\<и может быть вызвана, отправив `Add` запросы на service.svc/> операции - например, service.svc/Add для операции. Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX. Например, см. [службу AJAX без конфигурации.](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)  
  
## <a name="example"></a>Пример  
  
 Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса. Этот метод также допускает добавление и использование файла конфигурации. Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.  
  
 Например, service.svc использует фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, а в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью привязки <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу "soap". В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).  
  
 Если файл конфигурации определяет конечную точку по пустому относительному адресу и используется фабрика узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, создается исключение, происходит сбой запуска службы.  
  
 С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки. При необходимости изменить какой-либо параметр (например, квоту средств чтения) не следует использовать метод без конфигурации, т. е. удалять фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.  
  
 Если службе требуется режим совместимости с ASP.NET (например, если служба использует класс <xref:System.Web.HttpContext> или механизмы авторизации ASP.NET), для включения этого режима все равно понадобится файл конфигурации. Элемент конфигурации требуется [ \<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который должен быть добавлен следующим образом.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Для получения дополнительной информации, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
  
 Класс <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> наследуется от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>. Подробное объяснение механизма завода-хозяина службы можно насайте тему [расширения хостинга с использованием ServiceHostFactory.](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
  
## <a name="see-also"></a>См. также раздел

- [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
