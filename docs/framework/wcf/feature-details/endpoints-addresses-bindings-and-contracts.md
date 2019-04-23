---
title: 'Конечные точки: адреса, привязки и контракты'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3e78e7cf0c5acde53d7ee23294fd52134414e860
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207530"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="f00b5-102">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="f00b5-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="f00b5-103">Весь обмен данными со службой Windows Communication Foundation (WCF) осуществляется через *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="f00b5-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="f00b5-104">Конечные точки предоставляют клиентам доступ к функциональным возможностям службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f00b5-104">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>  
  
 <span data-ttu-id="f00b5-105">Каждая конечная точка состоит из четырех свойств:</span><span class="sxs-lookup"><span data-stu-id="f00b5-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="f00b5-106">адрес, показывающий, где можно найти конечную точку;</span><span class="sxs-lookup"><span data-stu-id="f00b5-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="f00b5-107">привязку, показывающую, как клиент может связаться с конечной точкой;</span><span class="sxs-lookup"><span data-stu-id="f00b5-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="f00b5-108">контракт, определяющий доступные операции;</span><span class="sxs-lookup"><span data-stu-id="f00b5-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="f00b5-109">набор поведений, задающих сведения о локальной реализации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f00b5-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="f00b5-110">В этом разделе рассматривается структура этой конечной точки и объясняется, каким образом она представлена в объектной модели WCF.</span><span class="sxs-lookup"><span data-stu-id="f00b5-110">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="f00b5-111">Структура конечной точки</span><span class="sxs-lookup"><span data-stu-id="f00b5-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="f00b5-112">Каждая конечная точка состоит из следующего.</span><span class="sxs-lookup"><span data-stu-id="f00b5-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="f00b5-113">Адрес: Адрес, уникально идентифицирующего конечную точку и указывает потенциальным потребителям службы, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="f00b5-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="f00b5-114">Он представлен в объектной модели WCF <xref:System.ServiceModel.EndpointAddress> класса.</span><span class="sxs-lookup"><span data-stu-id="f00b5-114">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="f00b5-115">Класс <xref:System.ServiceModel.EndpointAddress> содержит следующее.</span><span class="sxs-lookup"><span data-stu-id="f00b5-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="f00b5-116">Свойство <xref:System.ServiceModel.EndpointAddress.Uri%2A>, представляющее адрес службы.</span><span class="sxs-lookup"><span data-stu-id="f00b5-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="f00b5-117">Свойство <xref:System.ServiceModel.EndpointAddress.Identity%2A>, представляющее удостоверение безопасности службы и коллекцию необязательных заголовков сообщений.</span><span class="sxs-lookup"><span data-stu-id="f00b5-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="f00b5-118">Необязательные заголовки сообщений используются для вывода дополнительной и более подробной информации, необходимой для идентификации конечной точки или взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="f00b5-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     <span data-ttu-id="f00b5-119">Дополнительные сведения см. в разделе [Задание адреса конечной точки](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-119">For more information, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="f00b5-120">Привязка: Привязка задает способ связи клиента с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="f00b5-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="f00b5-121">В том числе следующее:</span><span class="sxs-lookup"><span data-stu-id="f00b5-121">This includes:</span></span>  
  
    -   <span data-ttu-id="f00b5-122">используемый транспортный протокол (например, TCP или HTTP);</span><span class="sxs-lookup"><span data-stu-id="f00b5-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="f00b5-123">используемую в сообщениях кодировку (например, текст или двоичное кодирование);</span><span class="sxs-lookup"><span data-stu-id="f00b5-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="f00b5-124">необходимые требования безопасности (например, безопасность сообщений SSL или SOAP).</span><span class="sxs-lookup"><span data-stu-id="f00b5-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     <span data-ttu-id="f00b5-125">Дополнительные сведения см. в разделе [Общие сведения о привязках WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-125">For more information, see [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="f00b5-126">Привязка представлено в объектной модели WCF с абстрактный базовый класс <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f00b5-126">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="f00b5-127">В большинстве сценариев пользователи могут использовать только одну из предусмотренных системой привязок.</span><span class="sxs-lookup"><span data-stu-id="f00b5-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="f00b5-128">Дополнительные сведения см. в разделе [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="f00b5-129">Контракты: Контракты показывают, какие функциональные возможности, конечная точка предоставляет клиенту.</span><span class="sxs-lookup"><span data-stu-id="f00b5-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="f00b5-130">В контракте задается следующее:</span><span class="sxs-lookup"><span data-stu-id="f00b5-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="f00b5-131">операции, которые могут быть вызваны клиентом;</span><span class="sxs-lookup"><span data-stu-id="f00b5-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="f00b5-132">форма сообщения;</span><span class="sxs-lookup"><span data-stu-id="f00b5-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="f00b5-133">тип входных параметров или данных, требуемых для вызова операции;</span><span class="sxs-lookup"><span data-stu-id="f00b5-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="f00b5-134">тип обработки или ответного сообщения, который может ожидать клиент.</span><span class="sxs-lookup"><span data-stu-id="f00b5-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="f00b5-135">Дополнительные сведения об определении контракта см. в разделе [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="f00b5-136">Поведения. Поведения конечных точек можно использовать для настройки локального поведения конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="f00b5-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="f00b5-137">Поведения конечной точки выполняют это путем участия в процессе построения WCFruntime.</span><span class="sxs-lookup"><span data-stu-id="f00b5-137">Endpoint behaviors achieve this by participating in the process of building a WCFruntime.</span></span> <span data-ttu-id="f00b5-138">Примером поведения является свойство <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, позволяющее указывать отличный от адреса SOAP или WSDL адрес прослушивания.</span><span class="sxs-lookup"><span data-stu-id="f00b5-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="f00b5-139">Дополнительные сведения см. в разделе [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-139">For more information, see [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="f00b5-140">Определение конечных точек</span><span class="sxs-lookup"><span data-stu-id="f00b5-140">Defining Endpoints</span></span>  
 <span data-ttu-id="f00b5-141">Адрес конечной точки службы можно задать императивно с помощью кода или декларативно с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f00b5-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="f00b5-142">Дополнительные сведения см. в разделе [Как Создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) и [как: Создать конечную точку службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-142">For more information, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f00b5-143">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f00b5-143">In This Section</span></span>  
 <span data-ttu-id="f00b5-144">В данном разделе объясняется назначение привязок, конечных точек и адресов; показано, как конфигурировать привязку и конечную точку, и демонстрируется, как использовать поведение `ClientVia` и свойство `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="f00b5-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="f00b5-145">Адреса</span><span class="sxs-lookup"><span data-stu-id="f00b5-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="f00b5-146">Описывает, как конечные точки адресуются в WCF.</span><span class="sxs-lookup"><span data-stu-id="f00b5-146">Describes how endpoints are addressed in WCF.</span></span>  
  
 [<span data-ttu-id="f00b5-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="f00b5-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="f00b5-148">Описывается, как привязки используются для указания транспорта, кодировки и данных протокола, требуемых для связи клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="f00b5-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="f00b5-149">Контракты</span><span class="sxs-lookup"><span data-stu-id="f00b5-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="f00b5-150">Описывается, как контакты определяют методы службы.</span><span class="sxs-lookup"><span data-stu-id="f00b5-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="f00b5-151">Практическое руководство. Создать конечную точку службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="f00b5-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="f00b5-152">Описывается, как создать конечную точку службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f00b5-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="f00b5-153">Практическое руководство. Создать конечную точку службы в коде</span><span class="sxs-lookup"><span data-stu-id="f00b5-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="f00b5-154">Описывается, как создать конечную точку службы в коде.</span><span class="sxs-lookup"><span data-stu-id="f00b5-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="f00b5-155">Практическое руководство. Использовать Svcutil.exe для проверки скомпилированного кода службы</span><span class="sxs-lookup"><span data-stu-id="f00b5-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="f00b5-156">Описывает, как для обнаружения ошибок в реализациях службы и конфигурациях, не размещая службу при помощи [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f00b5-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00b5-157">См. также</span><span class="sxs-lookup"><span data-stu-id="f00b5-157">See also</span></span>

- [<span data-ttu-id="f00b5-158">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="f00b5-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="f00b5-159">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="f00b5-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
