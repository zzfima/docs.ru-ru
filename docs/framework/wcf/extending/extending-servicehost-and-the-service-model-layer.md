---
title: "Расширение ServiceHost и уровень модели службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 67ed4be3211af141af87da2406e81ff5e2fbb767
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="5dffb-102">Расширение ServiceHost и уровень модели службы</span><span class="sxs-lookup"><span data-stu-id="5dffb-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="5dffb-103">Уровень модели службы отвечает за удаление входящих сообщений из базовых каналов, их перевод в вызовы метода в коде приложения и отправку результатов обратно вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="5dffb-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="5dffb-104">Расширения модели службы изменяют или реализуют поведение и возможности выполнения или взаимодействия, в том числе возможности клиента или диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие возможности расширяемости.</span><span class="sxs-lookup"><span data-stu-id="5dffb-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dffb-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="5dffb-105">In This Section</span></span>  
 [<span data-ttu-id="5dffb-106">Расширение клиентов</span><span class="sxs-lookup"><span data-stu-id="5dffb-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="5dffb-107">Описываются интерфейсы, которые могут перехватывать и изменять среду выполнения клиента, а также классы, в которые можно вставить специальные расширения в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="5dffb-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="5dffb-108">Например, можно выполнять специальную регистрацию сообщений, специальную сериализацию сообщений и т. п.</span><span class="sxs-lookup"><span data-stu-id="5dffb-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="5dffb-109">Расширение диспетчеров</span><span class="sxs-lookup"><span data-stu-id="5dffb-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="5dffb-110">Описываются интерфейсы, которые могут перехватывать и изменять среду выполнения службы, а также классы, в которые можно вставить пользовательские расширения в приложениях служб.</span><span class="sxs-lookup"><span data-stu-id="5dffb-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="5dffb-111">Например, можно выполнять специальную регистрацию службы, проверку сообщений со стороны службы, специальную диспетчеризацию и т. п.</span><span class="sxs-lookup"><span data-stu-id="5dffb-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="5dffb-112">Расширяемые объекты</span><span class="sxs-lookup"><span data-stu-id="5dffb-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="5dffb-113">Описывается пять расширяемых объектов и шаблон <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="5dffb-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="5dffb-114">Шаблон расширяемого объекта используется для расширения существующих классов среды выполнения при помощи новых функций или добавления нового состояния к объекту.</span><span class="sxs-lookup"><span data-stu-id="5dffb-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="5dffb-115">Расширения, привязанные к одному из расширяемых объектов, позволяют использовать поведения на различных этапах обработки для получения доступа к общему состоянию и функциональности, привязанным к общему расширяемому объекту, к которому они могут получить доступ.</span><span class="sxs-lookup"><span data-stu-id="5dffb-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="5dffb-116">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="5dffb-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="5dffb-117">Для изменения параметров или вставки расширений в среду выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются поведения.</span><span class="sxs-lookup"><span data-stu-id="5dffb-117">To change settings on or insert extensions in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime, you use Behaviors.</span></span> <span data-ttu-id="5dffb-118">WCF включает реализованные системой поведения для контроля регулирования количества запросов, использования экземпляров и многих других аспектов, относящихся к службам и операциям.</span><span class="sxs-lookup"><span data-stu-id="5dffb-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="5dffb-119">В данном разделе описывается, как создавать собственные пользовательские поведения и как обеспечить их доступность как программными средствами, так и при помощи файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5dffb-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="5dffb-120">Расширение размещения с использованием ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="5dffb-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="5dffb-121">Описывается, как расширить <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> и использовать классы <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> с целью настройки среды узла.</span><span class="sxs-lookup"><span data-stu-id="5dffb-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5dffb-122">Ссылка</span><span class="sxs-lookup"><span data-stu-id="5dffb-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5dffb-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5dffb-123">Related Sections</span></span>
