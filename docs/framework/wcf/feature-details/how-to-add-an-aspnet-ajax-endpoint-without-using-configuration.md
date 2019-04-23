---
title: Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 078580b96ab911f65790e58338951532cd7ad704
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344693"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="1f932-102">Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации</span><span class="sxs-lookup"><span data-stu-id="1f932-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="1f932-103">Windows Communication Foundation (WCF) позволяет создавать службы, которая предоставляет конечную точку с поддержкой ASP.NET AJAX, которая может вызываться из JavaScript на веб-сайта клиента.</span><span class="sxs-lookup"><span data-stu-id="1f932-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="1f932-104">Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f932-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="1f932-105">В этом разделе показано решение этой задачи вторым методом.</span><span class="sxs-lookup"><span data-stu-id="1f932-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="1f932-106">Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="1f932-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="1f932-107">Чтобы активировать конечную точку ASP.NET AJAX при таком подходе, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> фабрики в качестве параметра [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив в файле .svc.</span><span class="sxs-lookup"><span data-stu-id="1f932-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="1f932-108">Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="1f932-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="1f932-109">Рабочий пример см. в разделе [служба AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1f932-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="1f932-110">Общие сведения о настройке конечной точки ASP.NET AJAX с помощью элементов конфигурации, см. в разделе [как: Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="1f932-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="1f932-111">Создание базовой службы WCF</span><span class="sxs-lookup"><span data-stu-id="1f932-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="1f932-112">Определение основных контракта службы WCF с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="1f932-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="1f932-113">Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1f932-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="1f932-114">Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f932-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="1f932-115">Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="1f932-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="1f932-116">Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1f932-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="1f932-117">Размещение службы в службах IIS без конфигурации</span><span class="sxs-lookup"><span data-stu-id="1f932-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="1f932-118">Создайте в приложении новый файл с именем "service" и расширением .svc.</span><span class="sxs-lookup"><span data-stu-id="1f932-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="1f932-119">Измените этот файл, добавив соответствующие [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) информацию директивы для службы.</span><span class="sxs-lookup"><span data-stu-id="1f932-119">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="1f932-120">Указать, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> будет использоваться в [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директиву, чтобы автоматически настроить конечную точку ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1f932-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="1f932-121">Создайте службу и вызовите ее из клиента.</span><span class="sxs-lookup"><span data-stu-id="1f932-121">Build the service and call it from the client.</span></span> <span data-ttu-id="1f932-122">Internet Information Services (IIS) активирует данную службу при вызове.</span><span class="sxs-lookup"><span data-stu-id="1f932-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="1f932-123">Дополнительные сведения о размещении в IIS, см. в разделе [как: Размещение службы WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="1f932-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="1f932-124">Вызов службы</span><span class="sxs-lookup"><span data-stu-id="1f932-124">To call the service</span></span>  
  
1. <span data-ttu-id="1f932-125">Конечная точка настраивается с пустым адресом относительно SVC-файла, поэтому служба становится доступной и может быть вызвана отправкой запросов на service.svc/\<операции >, например, service.svc/Add для `Add` операции.</span><span class="sxs-lookup"><span data-stu-id="1f932-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="1f932-126">Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1f932-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="1f932-127">Например, см. в разделе [служба AJAX без конфигурации](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1f932-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f932-128">Пример</span><span class="sxs-lookup"><span data-stu-id="1f932-128">Example</span></span>  
  
 <span data-ttu-id="1f932-129">Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1f932-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="1f932-130">Этот метод также допускает добавление и использование файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f932-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="1f932-131">Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="1f932-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="1f932-132">Например, service.svc использует фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, а в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью привязки <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу "soap".</span><span class="sxs-lookup"><span data-stu-id="1f932-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="1f932-133">В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).</span><span class="sxs-lookup"><span data-stu-id="1f932-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="1f932-134">Если файл конфигурации определяет конечную точку по пустому относительному адресу и используется фабрика узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, создается исключение, происходит сбой запуска службы.</span><span class="sxs-lookup"><span data-stu-id="1f932-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="1f932-135">С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f932-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="1f932-136">При необходимости изменить какой-либо параметр (например, квоту средств чтения) не следует использовать метод без конфигурации, т. е. удалять фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f932-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="1f932-137">Если службе требуется режим совместимости с ASP.NET (например, если служба использует класс <xref:System.Web.HttpContext> или механизмы авторизации ASP.NET), для включения этого режима все равно понадобится файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f932-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="1f932-138">— Необходимый элемент конфигурации [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который необходимо добавить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1f932-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="1f932-139">Дополнительные сведения см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="1f932-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="1f932-140">Класс <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> наследуется от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="1f932-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="1f932-141">Подробное описание механизма фабрики узла службы, см. в разделе [расширение ServiceHostFactory размещение с помощью](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="1f932-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f932-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1f932-142">See also</span></span>

- [<span data-ttu-id="1f932-143">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="1f932-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="1f932-144">Практическое руководство. Миграция с поддержкой AJAX веб-служб ASP.NET в WCF</span><span class="sxs-lookup"><span data-stu-id="1f932-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
