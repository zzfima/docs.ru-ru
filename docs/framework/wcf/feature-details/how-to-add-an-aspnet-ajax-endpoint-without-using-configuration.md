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
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="b43de-102">Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации</span><span class="sxs-lookup"><span data-stu-id="b43de-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="b43de-103">Фонд связи Windows (WCF) позволяет создать сервис, который предоставляет ASP.NET топовой с поддержкой AJAX, которая может быть вызвана из JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="b43de-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="b43de-104">Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b43de-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="b43de-105">В этом разделе показано решение этой задачи вторым методом.</span><span class="sxs-lookup"><span data-stu-id="b43de-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="b43de-106">Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="b43de-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="b43de-107">Чтобы активировать ASP.NET конечную точку <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> AJAX с помощью этого подхода, укажите параметр Factory в директиве [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) в файле .svc.</span><span class="sxs-lookup"><span data-stu-id="b43de-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="b43de-108">Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="b43de-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="b43de-109">В рабочем примере см. [службу AJAX без конфигурации.](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="b43de-110">Для набросков того, как настроить конечную точку ASP.NET AJAX с использованием элементов конфигурации, [см. Как: Используйте конфигурацию для добавления ASP.NET конечной точки AJAX.](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="b43de-111">Создание базовой службы WCF</span><span class="sxs-lookup"><span data-stu-id="b43de-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="b43de-112">Определите базовый контракт службы WCF <xref:System.ServiceModel.ServiceContractAttribute> с интерфейсом, отмеченным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="b43de-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="b43de-113">Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b43de-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="b43de-114">Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="b43de-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="b43de-115">Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b43de-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="b43de-116">Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b43de-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="b43de-117">Размещение службы в службах IIS без конфигурации</span><span class="sxs-lookup"><span data-stu-id="b43de-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="b43de-118">Создайте в приложении новый файл с именем "service" и расширением .svc.</span><span class="sxs-lookup"><span data-stu-id="b43de-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="b43de-119">Отобразите этот файл, добавив соответствующую [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивную информацию ServiceHost для службы.</span><span class="sxs-lookup"><span data-stu-id="b43de-119">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="b43de-120">Укажите, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> что это должно использоваться в директиве [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) для автоматической настройки ASP.NET конечную точку AJAX.</span><span class="sxs-lookup"><span data-stu-id="b43de-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="b43de-121">Создайте службу и вызовите ее из клиента.</span><span class="sxs-lookup"><span data-stu-id="b43de-121">Build the service and call it from the client.</span></span> <span data-ttu-id="b43de-122">Internet Information Services (IIS) активирует данную службу при вызове.</span><span class="sxs-lookup"><span data-stu-id="b43de-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="b43de-123">Для получения дополнительной информации о хостинге в IIS, [см.](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="b43de-124">Вызов службы</span><span class="sxs-lookup"><span data-stu-id="b43de-124">To call the service</span></span>  
  
1. <span data-ttu-id="b43de-125">Конечная точка настроена по пустому адресу по отношению к файлу .svc, поэтому служба теперь доступна\<и может быть вызвана, отправив `Add` запросы на service.svc/> операции - например, service.svc/Add для операции.</span><span class="sxs-lookup"><span data-stu-id="b43de-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="b43de-126">Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="b43de-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="b43de-127">Например, см. [службу AJAX без конфигурации.](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b43de-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b43de-128">Example</span></span>  
  
 <span data-ttu-id="b43de-129">Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b43de-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="b43de-130">Этот метод также допускает добавление и использование файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b43de-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="b43de-131">Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="b43de-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="b43de-132">Например, service.svc использует фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, а в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью привязки <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу "soap".</span><span class="sxs-lookup"><span data-stu-id="b43de-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="b43de-133">В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).</span><span class="sxs-lookup"><span data-stu-id="b43de-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="b43de-134">Если файл конфигурации определяет конечную точку по пустому относительному адресу и используется фабрика узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, создается исключение, происходит сбой запуска службы.</span><span class="sxs-lookup"><span data-stu-id="b43de-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="b43de-135">С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b43de-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="b43de-136">При необходимости изменить какой-либо параметр (например, квоту средств чтения) не следует использовать метод без конфигурации, т. е. удалять фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b43de-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="b43de-137">Если службе требуется режим совместимости с ASP.NET (например, если служба использует класс <xref:System.Web.HttpContext> или механизмы авторизации ASP.NET), для включения этого режима все равно понадобится файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b43de-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="b43de-138">Элемент конфигурации требуется [ \<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который должен быть добавлен следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b43de-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="b43de-139">Для получения дополнительной информации, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="b43de-140">Класс <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> наследуется от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="b43de-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="b43de-141">Подробное объяснение механизма завода-хозяина службы можно насайте тему [расширения хостинга с использованием ServiceHostFactory.](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)</span><span class="sxs-lookup"><span data-stu-id="b43de-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43de-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b43de-142">See also</span></span>

- [<span data-ttu-id="b43de-143">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="b43de-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="b43de-144">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="b43de-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
