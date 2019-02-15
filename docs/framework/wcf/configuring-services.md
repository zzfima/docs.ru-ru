---
title: Настройка служб WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 2435d5c4592de60e07b60f1bf749f2421c798535
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303619"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="eb62a-102">Настройка служб WCF</span><span class="sxs-lookup"><span data-stu-id="eb62a-102">Configuring WCF services</span></span>

<span data-ttu-id="eb62a-103">После разработки и реализации контракта службы можно переходить к настройке службы.</span><span class="sxs-lookup"><span data-stu-id="eb62a-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="eb62a-104">В ходе этого определяется и настраивается способ представления службы клиентам, включая задание адреса, по которому ее можно найти, транспорт и кодирование сообщений, используемые для отправки и получения сообщений, а также требуемый тип безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb62a-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="eb62a-105">В используемой конфигурации предусматриваются все способы (принудительно в коде или с помощью файла конфигурации) определения и настройки различных аспектов службы, таких как задание адресов конечных точек, используемых транспортов и схем безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb62a-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="eb62a-106">На практике запись конфигурации является основной частью программирования приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="eb62a-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb62a-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eb62a-107">In This Section</span></span>  
 [<span data-ttu-id="eb62a-108">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="eb62a-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="eb62a-109">Начиная с [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF поставляется новая модель конфигурации по умолчанию, которая упрощает требования к конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="eb62a-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="eb62a-110">Если вы не укажете любой конфигурации WCF для конкретной службы, среда выполнения автоматически настраивает службы с помощью конечных точек по умолчанию, привязках и поведениях.</span><span class="sxs-lookup"><span data-stu-id="eb62a-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="eb62a-111">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="eb62a-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="eb62a-112">Служба Windows Communication Foundation (WCF) — можно настроить с помощью [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] технологии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eb62a-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="eb62a-113">Чаще всего элементы XML добавляются в файл Web.config для сайта Internet Information Services (IIS), на котором размещена служба WCF.</span><span class="sxs-lookup"><span data-stu-id="eb62a-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="eb62a-114">Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер.</span><span class="sxs-lookup"><span data-stu-id="eb62a-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="eb62a-115">Привязки</span><span class="sxs-lookup"><span data-stu-id="eb62a-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="eb62a-116">Кроме того WCF включает в себя несколько предоставляемых системой распространенные конфигурации в виде привязок, которые позволяют быстро выбирать основные возможности для взаимодействие клиента и службы, такие как транспорты, безопасность и сообщение, используемое кодировки.</span><span class="sxs-lookup"><span data-stu-id="eb62a-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="eb62a-117">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="eb62a-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="eb62a-118">Весь обмен данными со службой WCF осуществляется через *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="eb62a-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="eb62a-119">Конечные точки содержат контракт, сведения о конфигурации, указанные в привязках, и адреса, указывающие, где расположена служба и где получить информацию о ней.</span><span class="sxs-lookup"><span data-stu-id="eb62a-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="eb62a-120">Защита служб</span><span class="sxs-lookup"><span data-stu-id="eb62a-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="eb62a-121">С помощью WCF и существующих механизмов обеспечения безопасности, можно реализовать конфиденциальность, целостность, проверку подлинности и авторизацию в любой службе.</span><span class="sxs-lookup"><span data-stu-id="eb62a-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="eb62a-122">Также можно выполнить аудит на предмет успешных и неудачных попыток выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="eb62a-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="eb62a-123">Создание служб для взаимодействия с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="eb62a-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="eb62a-124">Требования к развертыванию службы с возможностью взаимодействия со службами и клиентами, размещенными на другой платформе или в другой операционной системе, указаны в спецификации WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="eb62a-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eb62a-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="eb62a-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="eb62a-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eb62a-126">Related Sections</span></span>  
 [<span data-ttu-id="eb62a-127">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="eb62a-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="eb62a-128">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="eb62a-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="eb62a-129">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="eb62a-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="eb62a-130">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="eb62a-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="eb62a-131">Введение в расширяемость</span><span class="sxs-lookup"><span data-stu-id="eb62a-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="eb62a-132">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="eb62a-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb62a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="eb62a-133">See also</span></span>
- [<span data-ttu-id="eb62a-134">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="eb62a-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="eb62a-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="eb62a-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="eb62a-136">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="eb62a-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
