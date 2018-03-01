---
title: NetworkInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 897f094f512e423f055f0abea04d5403552ba31c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="networkinformation"></a><span data-ttu-id="f7b5a-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="f7b5a-102">NetworkInformation</span></span>
<span data-ttu-id="f7b5a-103">Пространство имен <xref:System.Net.NetworkInformation> содержит классы для программного сбора информации о событиях, изменениях, статистике и свойствах сети.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="f7b5a-104">Можно также определить доступность удаленного узла с помощью класса <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="f7b5a-105">Доступность сети и события</span><span class="sxs-lookup"><span data-stu-id="f7b5a-105">Network Availability and Events</span></span>  
 <span data-ttu-id="f7b5a-106">Класс <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> позволяет определить, изменились ли адрес или состояние доступности сети.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="f7b5a-107">Чтобы использовать этот класс, создайте обработчик событий для обработки этого изменения и свяжите его с <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> или <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="f7b5a-108">Дополнительные сведения см. в разделе [Практическое руководство. Определение доступности сети и изменений адреса](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).</span><span class="sxs-lookup"><span data-stu-id="f7b5a-108">For more information, see [How to: Detect Network Availability and Address Changes](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="f7b5a-109">Статистика сети и свойства</span><span class="sxs-lookup"><span data-stu-id="f7b5a-109">Network Statistics and Properties</span></span>  
 <span data-ttu-id="f7b5a-110">Вы можете собирать статистику сетевой активности и сведения о свойствах на основе интерфейса или протокола.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="f7b5a-111">Классы <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> и <xref:System.Net.NetworkInformation.PhysicalAddress> предоставляют информацию о конкретном сетевом интерфейсе, а классы <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> и <xref:System.Net.NetworkInformation.UdpStatistics> — информацию о пакетах уровня 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="f7b5a-112">Дополнительные сведения см. в разделе [Практическое руководство. Получение информации об интерфейсах и протоколах](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).</span><span class="sxs-lookup"><span data-stu-id="f7b5a-112">For more information, see [How to: Get Interface and Protocol Information](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="f7b5a-113">Определение доступности удаленного узла</span><span class="sxs-lookup"><span data-stu-id="f7b5a-113">Determine if a Remote Host is Reachable</span></span>  
 <span data-ttu-id="f7b5a-114">С помощью класса <xref:System.Net.NetworkInformation.Ping> можно определить, работает ли удаленный узел, находится ли он в сети и возможен ли доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="f7b5a-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="f7b5a-115">Дополнительные сведения см. в статье [Практическое руководство. Проверка связи с узлом](../../../docs/framework/network-programming/how-to-ping-a-host.md).</span><span class="sxs-lookup"><span data-stu-id="f7b5a-115">For more information, see [How to: Ping a Host](../../../docs/framework/network-programming/how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b5a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f7b5a-116">See Also</span></span>  
 [<span data-ttu-id="f7b5a-117">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="f7b5a-117">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="f7b5a-118">Пример сетевых информационных технологий</span><span class="sxs-lookup"><span data-stu-id="f7b5a-118">Network Information Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179564)  
 [<span data-ttu-id="f7b5a-119">Пример технологии средства NetStat</span><span class="sxs-lookup"><span data-stu-id="f7b5a-119">NetStat Tool Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179562)  
 [<span data-ttu-id="f7b5a-120">Пример клиентской технологии проверки связи</span><span class="sxs-lookup"><span data-stu-id="f7b5a-120">Ping Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179565)
