---
title: Маршрутизация IPv6
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c3e2662eb444c70d2376a05e44ac84f472f27384
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ipv6-routing"></a><span data-ttu-id="98e4a-102">Маршрутизация IPv6</span><span class="sxs-lookup"><span data-stu-id="98e4a-102">IPv6 Routing</span></span>
<span data-ttu-id="98e4a-103">Гибкий механизм маршрутизации является преимуществом IPv6.</span><span class="sxs-lookup"><span data-stu-id="98e4a-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="98e4a-104">Способ выделения идентификаторов сетей IPv4 требует от маршрутизаторов, находящихся в магистральных каналах в Интернете, поддержки больших таблиц маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="98e4a-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="98e4a-105">Эти маршрутизаторы должны знать все маршруты, чтобы пересылать пакеты, которые могут быть направлены на любой узел в Интернете.</span><span class="sxs-lookup"><span data-stu-id="98e4a-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="98e4a-106">Благодаря возможности объединения адресов IPv6 обеспечивает гибкую адресацию и существенно сокращает размер таблиц маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="98e4a-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="98e4a-107">В этой новой архитектуре адресации промежуточные маршрутизаторы должны отслеживать локальную часть своей сети для правильной пересылки сообщений.</span><span class="sxs-lookup"><span data-stu-id="98e4a-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="98e4a-108">Обнаружение окружения</span><span class="sxs-lookup"><span data-stu-id="98e4a-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="98e4a-109">Ниже приведены некоторые функции, предоставляемые обнаружением окружения.</span><span class="sxs-lookup"><span data-stu-id="98e4a-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
-   <span data-ttu-id="98e4a-110">Обнаружение маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-110">Router discovery.</span></span> <span data-ttu-id="98e4a-111">Это позволяет узлам определять локальные маршрутизаторы.</span><span class="sxs-lookup"><span data-stu-id="98e4a-111">This allows hosts to identify local routers.</span></span>  
  
-   <span data-ttu-id="98e4a-112">Разрешение адресов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-112">Address resolution.</span></span> <span data-ttu-id="98e4a-113">Это позволяет узлам разрешать для адрес канального уровня для соответствующего адреса следующего прыжка (замена протокола ARP).</span><span class="sxs-lookup"><span data-stu-id="98e4a-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
-   <span data-ttu-id="98e4a-114">Автоматическая настройка адресов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-114">Address auto-configuration.</span></span> <span data-ttu-id="98e4a-115">Это позволяет узлам выполнять автоматическую настройку адресов локальных узлов и глобальных адресов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="98e4a-116">Обнаружение окружения использует ICMPv6-сообщения, которые включают:</span><span class="sxs-lookup"><span data-stu-id="98e4a-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
-   <span data-ttu-id="98e4a-117">Объявление маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-117">Router advertisement.</span></span> <span data-ttu-id="98e4a-118">Отправляется маршрутизатором на псевдопериодической основе или в ответ на запрос маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="98e4a-119">Маршрутизаторы IPv6 используют объявления маршрутизаторов для сообщения о своей доступности, для указания префиксов адресов и других параметров.</span><span class="sxs-lookup"><span data-stu-id="98e4a-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
-   <span data-ttu-id="98e4a-120">Запрос маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-120">Router solicitation.</span></span> <span data-ttu-id="98e4a-121">Отправляется узлом для запроса того, чтобы маршрутизаторы в канале немедленно отправили объявление маршрутизаторов.</span><span class="sxs-lookup"><span data-stu-id="98e4a-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
-   <span data-ttu-id="98e4a-122">Запрос поиска соседей.</span><span class="sxs-lookup"><span data-stu-id="98e4a-122">Neighbor solicitation.</span></span> <span data-ttu-id="98e4a-123">Отправляется узлами для разрешения адресов, обнаружения повторяющихся адресов или для проверки доступности соседей.</span><span class="sxs-lookup"><span data-stu-id="98e4a-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
-   <span data-ttu-id="98e4a-124">Объявление соседей.</span><span class="sxs-lookup"><span data-stu-id="98e4a-124">Neighbor advertisement.</span></span> <span data-ttu-id="98e4a-125">Рассылается узлами в ответ на запрос поиска соседей или для предупреждения соседей об изменении адреса канального уровня.</span><span class="sxs-lookup"><span data-stu-id="98e4a-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
-   <span data-ttu-id="98e4a-126">Перенаправление.</span><span class="sxs-lookup"><span data-stu-id="98e4a-126">Redirect.</span></span> <span data-ttu-id="98e4a-127">Отправляется маршрутизаторами, чтобы указать лучший адрес следующего прыжка для конкретного назначения для отправляющего узла.</span><span class="sxs-lookup"><span data-stu-id="98e4a-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e4a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="98e4a-128">See Also</span></span>  
 [<span data-ttu-id="98e4a-129">Протокол IP версии 6</span><span class="sxs-lookup"><span data-stu-id="98e4a-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="98e4a-130">Сокеты</span><span class="sxs-lookup"><span data-stu-id="98e4a-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
