---
title: "Настройка служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 857ec77e54d6a55bde1a94fd9fd5758ef7a24309
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-services"></a><span data-ttu-id="eed09-102">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="eed09-102">Configuring Services</span></span>
<span data-ttu-id="eed09-103">После разработки и реализации контракта службы можно переходить к настройке службы.</span><span class="sxs-lookup"><span data-stu-id="eed09-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="eed09-104">В ходе этого определяется и настраивается способ представления службы клиентам, включая задание адреса, по которому ее можно найти, транспорт и кодирование сообщений, используемые для отправки и получения сообщений, а также требуемый тип безопасности.</span><span class="sxs-lookup"><span data-stu-id="eed09-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="eed09-105">В используемой конфигурации предусматриваются все способы (принудительно в коде или с помощью файла конфигурации) определения и настройки различных аспектов службы, таких как задание адресов конечных точек, используемых транспортов и схем безопасности.</span><span class="sxs-lookup"><span data-stu-id="eed09-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="eed09-106">На практике запись конфигурации является основной частью процесса программирования приложений [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eed09-106">In practice, writing configuration is a major part of programming [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eed09-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eed09-107">In This Section</span></span>  
 [<span data-ttu-id="eed09-108">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="eed09-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="eed09-109">Начиная с версии [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] входит новая модель конфигурации по умолчанию, которая обладает упрощенными требованиями к настройке [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eed09-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] comes with a new default configuration model that simplifies [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration requirements.</span></span> <span data-ttu-id="eed09-110">Если для службы не указана конфигурация [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], то среда выполнения автоматически выполняет настройку службы, указывая конечные точки по умолчанию, привязки и поведения.</span><span class="sxs-lookup"><span data-stu-id="eed09-110">If you do not provide any [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="eed09-111">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="eed09-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="eed09-112">Службу [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] можно настроить с помощью технологии конфигурации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eed09-112">A [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="eed09-113">Чаще всего элементы XML добавляются в файл Web.config для узла служб IIS, на котором размещена служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eed09-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="eed09-114">Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер.</span><span class="sxs-lookup"><span data-stu-id="eed09-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="eed09-115">Привязки</span><span class="sxs-lookup"><span data-stu-id="eed09-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="eed09-116">Кроме того, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] включает несколько общих предоставляемых системой конфигураций в виде привязок, позволяющих быстро выбирать основные функции для взаимодействия клиента и службы, такие как транспорты, безопасность и кодирование сообщений.</span><span class="sxs-lookup"><span data-stu-id="eed09-116">In addition, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="eed09-117">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="eed09-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="eed09-118">Вся связь со [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службы осуществляется с помощью *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="eed09-118">All communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="eed09-119">Конечные точки содержат контракт, сведения о конфигурации, указанные в привязках, и адреса, указывающие, где расположена служба и где получить информацию о ней.</span><span class="sxs-lookup"><span data-stu-id="eed09-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="eed09-120">Защита служб</span><span class="sxs-lookup"><span data-stu-id="eed09-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="eed09-121">С помощью [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и существующих механизмов безопасности можно реализовать конфиденциальность, целостность, проверку подлинности и авторизацию в любой службе.</span><span class="sxs-lookup"><span data-stu-id="eed09-121">Using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="eed09-122">Также можно выполнить аудит на предмет успешных и неудачных попыток выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="eed09-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="eed09-123">Создание служб для взаимодействия с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="eed09-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="eed09-124">Требования к развертыванию службы с возможностью взаимодействия со службами и клиентами, размещенными на другой платформе или в другой операционной системе, указаны в спецификации WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="eed09-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eed09-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="eed09-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="eed09-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eed09-126">Related Sections</span></span>  
 [<span data-ttu-id="eed09-127">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="eed09-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="eed09-128">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="eed09-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="eed09-129">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="eed09-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="eed09-130">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="eed09-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="eed09-131">Введение в расширяемость</span><span class="sxs-lookup"><span data-stu-id="eed09-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="eed09-132">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="eed09-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="eed09-133">См. также</span><span class="sxs-lookup"><span data-stu-id="eed09-133">See Also</span></span>  
 [<span data-ttu-id="eed09-134">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="eed09-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="eed09-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="eed09-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="eed09-136">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="eed09-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
