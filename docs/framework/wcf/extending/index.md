---
title: Расширение WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c84f25dfd5d3066f9c5d0b62bc0b28bc98c283d
ms.sourcegitcommit: 08684dd61444c2f072b89b926370f750e456fca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="extending-wcf"></a><span data-ttu-id="9596b-102">Расширение WCF</span><span class="sxs-lookup"><span data-stu-id="9596b-102">Extending WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] <span data-ttu-id="9596b-103">позволяет изменять и расширять компоненты времени выполнения для точного управления и расширения приложений на основе служб.</span><span class="sxs-lookup"><span data-stu-id="9596b-103">allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="9596b-104">Статьи данного раздела подробно описывают архитектуру расширяемости.</span><span class="sxs-lookup"><span data-stu-id="9596b-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="9596b-105">Дополнительные сведения о базовое программирование в разделе [базовое Программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="9596b-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9596b-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9596b-106">In This Section</span></span>  
 [<span data-ttu-id="9596b-107">Расширение ServiceHost и уровень модели службы</span><span class="sxs-lookup"><span data-stu-id="9596b-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="9596b-108">Уровень модели службы отвечает за удаление входящих сообщений из базовых каналов, их перевод в вызовы метода в коде приложения и отправку результатов обратно вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="9596b-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="9596b-109">Расширения модели службы изменяют или реализуют порядок и компоненты выполнения или взаимодействия, в том числе компоненты, включающие возможности диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие расширяемые возможности.</span><span class="sxs-lookup"><span data-stu-id="9596b-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="9596b-110">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="9596b-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="9596b-111">Привязки - это объекты, которые описывают сведения о связи, требуемые для подключения к конечной точке.</span><span class="sxs-lookup"><span data-stu-id="9596b-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="9596b-112">Расширения привязок и пользовательские привязки реализуют пользовательскую функциональность связи, необходимую для поддержки возможностей приложения.</span><span class="sxs-lookup"><span data-stu-id="9596b-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="9596b-113">Расширение уровня каналов</span><span class="sxs-lookup"><span data-stu-id="9596b-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="9596b-114">Уровень канала находится в уровне модели службы и отвечает за обмен сообщениями между клиентами и службами.</span><span class="sxs-lookup"><span data-stu-id="9596b-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="9596b-115">Расширения каналов могут реализовывать новые функциональные возможности протокола, такие как безопасность.</span><span class="sxs-lookup"><span data-stu-id="9596b-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="9596b-116">Они также реализуют транспортные функциональные возможности, такие как новый сетевой транспорт для передачи сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="9596b-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="9596b-117">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="9596b-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="9596b-118">Безопасность в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] состоит из транспортной безопасности (целостности, конфиденциальности и проверки подлинности), управления доступом и аудита.</span><span class="sxs-lookup"><span data-stu-id="9596b-118">Security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="9596b-119">Классы, находящиеся в пространстве имен `IdentityModel`, используются [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для управления доступом.</span><span class="sxs-lookup"><span data-stu-id="9596b-119">The classes found in the `IdentityModel` namespace are used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for access control.</span></span> <span data-ttu-id="9596b-120">Понимание архитектуры безопасности позволяет создавать пользовательские типы утверждений для использования в системах управления доступом.</span><span class="sxs-lookup"><span data-stu-id="9596b-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="9596b-121">Расширение системы метаданных</span><span class="sxs-lookup"><span data-stu-id="9596b-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="9596b-122">Система метаданных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является набором классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб.</span><span class="sxs-lookup"><span data-stu-id="9596b-122">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="9596b-123">Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="9596b-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="9596b-124">Расширение кодировщиков и сериализаторов</span><span class="sxs-lookup"><span data-stu-id="9596b-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="9596b-125">Кодировщики и сериализаторы преобразовывают данные из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="9596b-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="9596b-126">Статьи данного раздела описывают, как расширять переданные классы для удовлетворения конкретных требований.</span><span class="sxs-lookup"><span data-stu-id="9596b-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9596b-127">Ссылка</span><span class="sxs-lookup"><span data-stu-id="9596b-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="9596b-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9596b-128">Related Sections</span></span>  
 [<span data-ttu-id="9596b-129">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="9596b-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="9596b-130">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="9596b-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="9596b-131">Правила и рекомендации</span><span class="sxs-lookup"><span data-stu-id="9596b-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
