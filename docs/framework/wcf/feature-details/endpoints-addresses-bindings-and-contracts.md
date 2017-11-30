---
title: "Конечные точки: адреса, привязки и контракты"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1ee80307e0db82f4744970844754a910e81ca3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="fdb9c-102">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="fdb9c-102">Endpoints: Addresses, Bindings, and Contracts</span></span>
<span data-ttu-id="fdb9c-103">Вся связь со [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] службы осуществляется с помощью *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-103">All communication with a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="fdb9c-104">Конечные точки обеспечивают доступ клиентов к функциональным возможностям службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdb9c-104">Endpoints provide clients access to the functionality offered by a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="fdb9c-105">Каждая конечная точка состоит из четырех свойств:</span><span class="sxs-lookup"><span data-stu-id="fdb9c-105">Each endpoint consists of four properties:</span></span>  
  
-   <span data-ttu-id="fdb9c-106">адрес, показывающий, где можно найти конечную точку;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-106">An address that indicates where the endpoint can be found.</span></span>  
  
-   <span data-ttu-id="fdb9c-107">привязку, показывающую, как клиент может связаться с конечной точкой;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-107">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="fdb9c-108">контракт, определяющий доступные операции;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-108">A contract that identifies the operations available.</span></span>  
  
-   <span data-ttu-id="fdb9c-109">набор поведений, задающих сведения о локальной реализации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-109">A set of behaviors that specify local implementation details of the endpoint.</span></span>  
  
 <span data-ttu-id="fdb9c-110">В настоящем разделе описана структура конечной точки и объясняется, каким образом она представлена в объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdb9c-110">This topic discusses this endpoint structure and explains how it is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model.</span></span>  
  
## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="fdb9c-111">Структура конечной точки</span><span class="sxs-lookup"><span data-stu-id="fdb9c-111">The Structure of an Endpoint</span></span>  
 <span data-ttu-id="fdb9c-112">Каждая конечная точка состоит из следующего.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-112">Each endpoint consists of the following:</span></span>  
  
-   <span data-ttu-id="fdb9c-113">Адрес: адрес однозначно определяет конечную точку и указывает потенциальным потребителям на место расположения службы.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-113">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="fdb9c-114">В объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] адрес представлен классом <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-114">It is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="fdb9c-115">Класс <xref:System.ServiceModel.EndpointAddress> содержит следующее.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-115">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>  
  
    -   <span data-ttu-id="fdb9c-116">Свойство <xref:System.ServiceModel.EndpointAddress.Uri%2A>, представляющее адрес службы.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-116">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>  
  
    -   <span data-ttu-id="fdb9c-117">Свойство <xref:System.ServiceModel.EndpointAddress.Identity%2A>, представляющее удостоверение безопасности службы и коллекцию необязательных заголовков сообщений.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-117">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="fdb9c-118">Необязательные заголовки сообщений используются для вывода дополнительной и более подробной информации, необходимой для идентификации конечной точки или взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-118">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fdb9c-119">[Задание адреса конечной точки](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-119"> [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
-   <span data-ttu-id="fdb9c-120">Привязка. Привязка задает способ связи клиента с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-120">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="fdb9c-121">В том числе следующее:</span><span class="sxs-lookup"><span data-stu-id="fdb9c-121">This includes:</span></span>  
  
    -   <span data-ttu-id="fdb9c-122">используемый транспортный протокол (например, TCP или HTTP);</span><span class="sxs-lookup"><span data-stu-id="fdb9c-122">The transport protocol to use (for example, TCP or HTTP).</span></span>  
  
    -   <span data-ttu-id="fdb9c-123">используемую в сообщениях кодировку (например, текст или двоичное кодирование);</span><span class="sxs-lookup"><span data-stu-id="fdb9c-123">The encoding to use for the messages (for example, text or binary).</span></span>  
  
    -   <span data-ttu-id="fdb9c-124">необходимые требования безопасности (например, безопасность сообщений SSL или SOAP).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-124">The necessary security requirements (for example, SSL or SOAP message security).</span></span>  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fdb9c-125">[Общие сведения о привязках WCF](../../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-125"> [WCF Bindings Overview](../../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="fdb9c-126">Привязка в объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] представлена абстрактным базовым классом <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-126">A binding is represented in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="fdb9c-127">В большинстве сценариев пользователи могут использовать только одну из предусмотренных системой привязок.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-127">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="fdb9c-128">Дополнительные сведения см. в разделе [привязка, предоставляемая системой](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-128">For more information, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
-   <span data-ttu-id="fdb9c-129">Контракты. Контракты показывают, какие функциональные возможности дает клиенту конечная точка.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-129">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="fdb9c-130">В контракте задается следующее:</span><span class="sxs-lookup"><span data-stu-id="fdb9c-130">A contract specifies:</span></span>  
  
    -   <span data-ttu-id="fdb9c-131">операции, которые могут быть вызваны клиентом;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-131">What operations can be called by a client.</span></span>  
  
    -   <span data-ttu-id="fdb9c-132">форма сообщения;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-132">The form of the message.</span></span>  
  
    -   <span data-ttu-id="fdb9c-133">тип входных параметров или данных, требуемых для вызова операции;</span><span class="sxs-lookup"><span data-stu-id="fdb9c-133">The type of input parameters or data required to call the operation.</span></span>  
  
    -   <span data-ttu-id="fdb9c-134">тип обработки или ответного сообщения, который может ожидать клиент.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-134">What type of processing or response message the client can expect.</span></span>  
  
     <span data-ttu-id="fdb9c-135">Дополнительные сведения об определении контракта см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-135">For more information about defining a contract, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
-   <span data-ttu-id="fdb9c-136">Поведения. Поведения конечной точки можно использовать для настройки локального поведения конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-136">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="fdb9c-137">Поведения конечной точки выполняют это путем участия в процессе создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-137">Endpoint behaviors achieve this by participating in the process of building a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]runtime.</span></span> <span data-ttu-id="fdb9c-138">Примером поведения является свойство <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, позволяющее указывать отличный от адреса SOAP или WSDL адрес прослушивания.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-138">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fdb9c-139">[ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-139"> [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).</span></span>  
  
## <a name="defining-endpoints"></a><span data-ttu-id="fdb9c-140">Определение конечных точек</span><span class="sxs-lookup"><span data-stu-id="fdb9c-140">Defining Endpoints</span></span>  
 <span data-ttu-id="fdb9c-141">Адрес конечной точки службы можно задать императивно с помощью кода или декларативно с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-141">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fdb9c-142">[Как: создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) и [как: создать конечную точку службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-142"> [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdb9c-143">Содержание</span><span class="sxs-lookup"><span data-stu-id="fdb9c-143">In This Section</span></span>  
 <span data-ttu-id="fdb9c-144">В данном разделе объясняется назначение привязок, конечных точек и адресов; показано, как конфигурировать привязку и конечную точку, и демонстрируется, как использовать поведение `ClientVia` и свойство `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-144">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>  
  
 [<span data-ttu-id="fdb9c-145">Адреса</span><span class="sxs-lookup"><span data-stu-id="fdb9c-145">Addresses</span></span>](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 <span data-ttu-id="fdb9c-146">Описывается, как выполняется обращение к конечным точкам в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdb9c-146">Describes how endpoints are addressed in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="fdb9c-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="fdb9c-147">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 <span data-ttu-id="fdb9c-148">Описывается, как привязки используются для указания транспорта, кодировки и данных протокола, требуемых для связи клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-148">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>  
  
 [<span data-ttu-id="fdb9c-149">Контракты</span><span class="sxs-lookup"><span data-stu-id="fdb9c-149">Contracts</span></span>](../../../../docs/framework/wcf/feature-details/contracts.md)  
 <span data-ttu-id="fdb9c-150">Описывается, как контакты определяют методы службы.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-150">Describes how contracts define the methods of a service.</span></span>  
  
 [<span data-ttu-id="fdb9c-151">Как: создать конечную точку службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="fdb9c-151">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="fdb9c-152">Описывается, как создать конечную точку службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-152">Describes how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="fdb9c-153">Как: создать конечную точку службы в коде</span><span class="sxs-lookup"><span data-stu-id="fdb9c-153">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="fdb9c-154">Описывается, как создать конечную точку службы в коде.</span><span class="sxs-lookup"><span data-stu-id="fdb9c-154">Describes how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="fdb9c-155">Как: использовать Svcutil.exe для проверки скомпилированного кода службы</span><span class="sxs-lookup"><span data-stu-id="fdb9c-155">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 <span data-ttu-id="fdb9c-156">Описывает, как для обнаружения ошибок в реализациях службы и конфигурации без размещения службы с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9c-156">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb9c-157">См. также</span><span class="sxs-lookup"><span data-stu-id="fdb9c-157">See Also</span></span>  
 [<span data-ttu-id="fdb9c-158">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="fdb9c-158">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="fdb9c-159">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="fdb9c-159">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
