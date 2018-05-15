---
title: Настройка служб
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 7718edaefbad18afa11b3e3680fac39da585a610
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="configuring-services"></a><span data-ttu-id="f8810-102">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="f8810-102">Configuring Services</span></span>
<span data-ttu-id="f8810-103">После разработки и реализации контракта службы можно переходить к настройке службы.</span><span class="sxs-lookup"><span data-stu-id="f8810-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="f8810-104">В ходе этого определяется и настраивается способ представления службы клиентам, включая задание адреса, по которому ее можно найти, транспорт и кодирование сообщений, используемые для отправки и получения сообщений, а также требуемый тип безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8810-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="f8810-105">В используемой конфигурации предусматриваются все способы (принудительно в коде или с помощью файла конфигурации) определения и настройки различных аспектов службы, таких как задание адресов конечных точек, используемых транспортов и схем безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8810-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="f8810-106">На практике запись конфигурации является основной частью программирования приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="f8810-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8810-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f8810-107">In This Section</span></span>  
 [<span data-ttu-id="f8810-108">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="f8810-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="f8810-109">Начиная с [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF поставляется новая модель конфигурации по умолчанию, которая упрощает требования к конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="f8810-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="f8810-110">Если любой конфигурации WCF для конкретной службы не указано, среда выполнения автоматически выполняет настройку службы с помощью конечных точек по умолчанию, привязок и поведений.</span><span class="sxs-lookup"><span data-stu-id="f8810-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="f8810-111">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="f8810-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="f8810-112">Служба Windows Communication Foundation (WCF) — можно настроить с помощью [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] технологии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8810-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="f8810-113">Чаще всего элементы XML добавляются в файл Web.config для узла службы Internet Information Services (IIS), на котором размещена служба WCF.</span><span class="sxs-lookup"><span data-stu-id="f8810-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="f8810-114">Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер.</span><span class="sxs-lookup"><span data-stu-id="f8810-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="f8810-115">Привязки</span><span class="sxs-lookup"><span data-stu-id="f8810-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="f8810-116">Кроме того WCF включает в себя несколько предоставляемых системой общих конфигураций в виде привязок, позволяющих быстро выбирать основные функции для взаимодействия клиента и службы, такие как транспорты, безопасность и кодирование использовано сообщение.</span><span class="sxs-lookup"><span data-stu-id="f8810-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="f8810-117">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="f8810-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="f8810-118">Вся связь со службой WCF осуществляется через *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="f8810-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="f8810-119">Конечные точки содержат контракт, сведения о конфигурации, указанные в привязках, и адреса, указывающие, где расположена служба и где получить информацию о ней.</span><span class="sxs-lookup"><span data-stu-id="f8810-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="f8810-120">Защита служб</span><span class="sxs-lookup"><span data-stu-id="f8810-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="f8810-121">С помощью WCF и существующих механизмов обеспечения безопасности, можно реализовать конфиденциальность, целостность, проверку подлинности и авторизацию в любой службе.</span><span class="sxs-lookup"><span data-stu-id="f8810-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="f8810-122">Также можно выполнить аудит на предмет успешных и неудачных попыток выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="f8810-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="f8810-123">Создание служб для взаимодействия с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="f8810-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="f8810-124">Требования к развертыванию службы с возможностью взаимодействия со службами и клиентами, размещенными на другой платформе или в другой операционной системе, указаны в спецификации WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="f8810-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f8810-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f8810-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="f8810-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f8810-126">Related Sections</span></span>  
 [<span data-ttu-id="f8810-127">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="f8810-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="f8810-128">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="f8810-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="f8810-129">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="f8810-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="f8810-130">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="f8810-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="f8810-131">Введение в расширяемость</span><span class="sxs-lookup"><span data-stu-id="f8810-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="f8810-132">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f8810-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8810-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f8810-133">See Also</span></span>  
 [<span data-ttu-id="f8810-134">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="f8810-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="f8810-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="f8810-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="f8810-136">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="f8810-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
