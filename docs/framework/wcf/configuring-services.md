---
title: Настройка служб WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: e8ac62809b1269ae810f026c003c7611b3ec548c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593322"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="6dcfc-102">Настройка служб WCF</span><span class="sxs-lookup"><span data-stu-id="6dcfc-102">Configuring WCF services</span></span>

<span data-ttu-id="6dcfc-103">После разработки и реализации контракта службы можно переходить к настройке службы.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="6dcfc-104">В ходе этого определяется и настраивается способ представления службы клиентам, включая задание адреса, по которому ее можно найти, транспорт и кодирование сообщений, используемые для отправки и получения сообщений, а также требуемый тип безопасности.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="6dcfc-105">В используемой конфигурации предусматриваются все способы (принудительно в коде или с помощью файла конфигурации) определения и настройки различных аспектов службы, таких как задание адресов конечных точек, используемых транспортов и схем безопасности.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="6dcfc-106">На практике запись конфигурации является основной частью программирования приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dcfc-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6dcfc-107">In This Section</span></span>  
 [<span data-ttu-id="6dcfc-108">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="6dcfc-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="6dcfc-109">Начиная с [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF поставляется новая модель конфигурации по умолчанию, которая упрощает требования к конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="6dcfc-110">Если вы не укажете любой конфигурации WCF для конкретной службы, среда выполнения автоматически настраивает службы с помощью конечных точек по умолчанию, привязках и поведениях.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="6dcfc-111">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="6dcfc-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="6dcfc-112">Службы Windows Communication Foundation (WCF) может настраиваться с помощью технологии конфигурации .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-112">A Windows Communication Foundation (WCF) service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="6dcfc-113">Чаще всего элементы XML добавляются в файл Web.config для сайта Internet Information Services (IIS), на котором размещена служба WCF.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="6dcfc-114">Эти элементы позволяют изменять данные, такие как адреса конечных точек (фактические адреса, используемые для взаимодействия со службой), по схеме компьютер-компьютер.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="6dcfc-115">Привязки</span><span class="sxs-lookup"><span data-stu-id="6dcfc-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="6dcfc-116">Кроме того WCF включает в себя несколько предоставляемых системой распространенные конфигурации в виде привязок, которые позволяют быстро выбирать основные возможности для взаимодействие клиента и службы, такие как транспорты, безопасность и сообщение, используемое кодировки.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="6dcfc-117">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="6dcfc-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="6dcfc-118">Весь обмен данными со службой WCF осуществляется через *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="6dcfc-119">Конечные точки содержат контракт, сведения о конфигурации, указанные в привязках, и адреса, указывающие, где расположена служба и где получить информацию о ней.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="6dcfc-120">Защита служб</span><span class="sxs-lookup"><span data-stu-id="6dcfc-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="6dcfc-121">С помощью WCF и существующих механизмов обеспечения безопасности, можно реализовать конфиденциальность, целостность, проверку подлинности и авторизацию в любой службе.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="6dcfc-122">Также можно выполнить аудит на предмет успешных и неудачных попыток выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="6dcfc-123">Создание служб для взаимодействия с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="6dcfc-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="6dcfc-124">Требования к развертыванию службы с возможностью взаимодействия со службами и клиентами, размещенными на другой платформе или в другой операционной системе, указаны в спецификации WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="6dcfc-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6dcfc-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6dcfc-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="6dcfc-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6dcfc-126">Related Sections</span></span>  
 [<span data-ttu-id="6dcfc-127">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="6dcfc-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="6dcfc-128">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="6dcfc-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="6dcfc-129">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="6dcfc-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="6dcfc-130">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="6dcfc-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="6dcfc-131">Введение в расширяемость</span><span class="sxs-lookup"><span data-stu-id="6dcfc-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="6dcfc-132">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6dcfc-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dcfc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="6dcfc-133">See also</span></span>

- [<span data-ttu-id="6dcfc-134">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="6dcfc-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="6dcfc-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="6dcfc-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="6dcfc-136">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="6dcfc-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
