---
title: протокол IP версии 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2c9b3b1c647d74444fed01e38b65c1b2fe8364c6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185627"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="18e95-102">протокол IP версии 6</span><span class="sxs-lookup"><span data-stu-id="18e95-102">Internet Protocol Version 6</span></span>
<span data-ttu-id="18e95-103">Протокол IP версии 6 (IPv6) — это новый набор стандартных протоколов для сетевого уровня Интернета.</span><span class="sxs-lookup"><span data-stu-id="18e95-103">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="18e95-104">IPv6 позволяет устранить множество проблем текущей версии набора интернет-протоколов (известного как IPv4), связанных с нехваткой адресов, безопасностью, автоматической настройкой, расширяемостью и т. д.</span><span class="sxs-lookup"><span data-stu-id="18e95-104">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="18e95-105">IPv6 расширяет возможности Интернета для активации новых видов приложений, включая приложения для одноранговой сети и мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="18e95-105">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="18e95-106">Ниже приведены основные проблемы текущего протокола IPv4.</span><span class="sxs-lookup"><span data-stu-id="18e95-106">The following are the main issues of the current IPv4 protocol:</span></span>  
  
-   <span data-ttu-id="18e95-107">Быстрое исчерпание диапазона адресов.</span><span class="sxs-lookup"><span data-stu-id="18e95-107">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="18e95-108">Это привело к использованию трансляторов сетевых адресов (NAT), которые сопоставляют несколько частных адресов с одним общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="18e95-108">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="18e95-109">Основными проблемами, создаваемыми этим механизмом, являются затраты на обработку и отсутствие сквозной связи.</span><span class="sxs-lookup"><span data-stu-id="18e95-109">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
-   <span data-ttu-id="18e95-110">Отсутствие поддержки иерархии.</span><span class="sxs-lookup"><span data-stu-id="18e95-110">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="18e95-111">Из-за своей изначально предопределенной организации классов в IPv4 отсутствует настоящая иерархическая поддержка.</span><span class="sxs-lookup"><span data-stu-id="18e95-111">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="18e95-112">Невозможно структурировать IP-адреса таким образом, который действительно сопоставляет топологию сети.</span><span class="sxs-lookup"><span data-stu-id="18e95-112">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="18e95-113">Этот ключевой недостаток приводит к необходимости использования больших таблиц маршрутизации для доставки пакетов IPv4 в любое место в Интернете.</span><span class="sxs-lookup"><span data-stu-id="18e95-113">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
-   <span data-ttu-id="18e95-114">Сложная конфигурация сети.</span><span class="sxs-lookup"><span data-stu-id="18e95-114">Complex network configuration.</span></span>  
  
     <span data-ttu-id="18e95-115">При использовании протокола IPv4 адреса должны назначаться статически или с помощью протокола конфигурации, например DHCP.</span><span class="sxs-lookup"><span data-stu-id="18e95-115">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="18e95-116">В идеальном случае узлам не придется зависеть от администрирования инфраструктуры DHCP.</span><span class="sxs-lookup"><span data-stu-id="18e95-116">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="18e95-117">Вместо этого они смогут выполнять самостоятельную настройку с учетом сегмента сети, в котором они расположены.</span><span class="sxs-lookup"><span data-stu-id="18e95-117">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
-   <span data-ttu-id="18e95-118">Отсутствие встроенной проверки подлинности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="18e95-118">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="18e95-119">Для IPv4 не требуется поддержка какого-либо механизма, обеспечивающего проверку подлинности или шифрование передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="18e95-119">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="18e95-120">Этот момент меняется при использовании IPv6.</span><span class="sxs-lookup"><span data-stu-id="18e95-120">This changes with IPv6.</span></span> <span data-ttu-id="18e95-121">IPSec является требованием поддержки IPv6.</span><span class="sxs-lookup"><span data-stu-id="18e95-121">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="18e95-122">Новый набор протоколов должен удовлетворять следующим базовым требованиям:</span><span class="sxs-lookup"><span data-stu-id="18e95-122">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
-   <span data-ttu-id="18e95-123">Широкомасштабная маршрутизация и адресация с низкими издержками.</span><span class="sxs-lookup"><span data-stu-id="18e95-123">Large-scale routing and addressing with low overhead.</span></span>  
  
-   <span data-ttu-id="18e95-124">Автоматическая настройка для различных ситуаций подключения.</span><span class="sxs-lookup"><span data-stu-id="18e95-124">Auto-configuration for various connecting situations.</span></span>  
  
-   <span data-ttu-id="18e95-125">Встроенная проверка подлинности и конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="18e95-125">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="18e95-126">Дополнительные сведения см. в разделах [Адресация IPv6](../../../docs/framework/network-programming/ipv6-addressing.md), [Маршрутизация IPv6](../../../docs/framework/network-programming/ipv6-routing.md), [Автоматическая настройка IPv6](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Включение и отключение IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) и [Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="18e95-126">For more information, see [IPv6 Addressing](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6 Routing](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 Auto-Configuration](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Enabling and Disabling IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="18e95-127">Ссылки</span><span class="sxs-lookup"><span data-stu-id="18e95-127">References</span></span>  
 <span data-ttu-id="18e95-128">Ниже перечислен ряд документов RFC, которые можно найти на сайте Internet Engineering Task Force ([http://www.ietf.org](http://www.ietf.org/)):</span><span class="sxs-lookup"><span data-stu-id="18e95-128">The following are selected RFC documents that you can find at the Internet Engineering Task Force site ([http://www.ietf.org](http://www.ietf.org/)):</span></span>  
  
-   <span data-ttu-id="18e95-129">RFC 1287, Towards the Future Internet Architecture.</span><span class="sxs-lookup"><span data-stu-id="18e95-129">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
-   <span data-ttu-id="18e95-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span><span class="sxs-lookup"><span data-stu-id="18e95-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
-   <span data-ttu-id="18e95-131">RFC 2373, IP Version 6 Addressing Architecture.</span><span class="sxs-lookup"><span data-stu-id="18e95-131">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
-   <span data-ttu-id="18e95-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span><span class="sxs-lookup"><span data-stu-id="18e95-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="18e95-133">Сведения, относящиеся к IPv6, можно также найти в [разделе о IPv6 на сайте Technet](https://go.microsoft.com/fwlink/?LinkID=179658).</span><span class="sxs-lookup"><span data-stu-id="18e95-133">You can also find IPv6-related information on the [IPv6 area on Technet](https://go.microsoft.com/fwlink/?LinkID=179658).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e95-134">См. также</span><span class="sxs-lookup"><span data-stu-id="18e95-134">See Also</span></span>  
 <span data-ttu-id="18e95-135">[Пример сокетов IPv6](https://msdn.microsoft.com/library/ms180981(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="18e95-135">[IPv6 Sockets Sample](https://msdn.microsoft.com/library/ms180981(v=vs.85).aspx)</span></span>  
 [<span data-ttu-id="18e95-136">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="18e95-136">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="18e95-137">Сокеты</span><span class="sxs-lookup"><span data-stu-id="18e95-137">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
