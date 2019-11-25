---
title: PNRP в разработке приложений
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: f9a408fbd7fbbb77c0fd5208926f4b06fcf23b38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428208"
---
# <a name="pnrp-in-application-development"></a><span data-ttu-id="5cb0f-102">PNRP в разработке приложений</span><span class="sxs-lookup"><span data-stu-id="5cb0f-102">PNRP in Application Development</span></span>
<span data-ttu-id="5cb0f-103">В ОС Windows Vista сетевые приложения могут получать доступ к функциям публикации и разрешения имен через упрощенный программный интерфейс (API) PNRP.</span><span class="sxs-lookup"><span data-stu-id="5cb0f-103">In Windows Vista, networking applications can access name publication and resolution functions through a simplified PNRP application programming interface (API).</span></span>  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a><span data-ttu-id="5cb0f-104">Реализация протокола PNRP</span><span class="sxs-lookup"><span data-stu-id="5cb0f-104">Implementing the Peer Name Resolution Protocol</span></span>  
 <span data-ttu-id="5cb0f-105">С помощью упрощенного API PNRP не задаются явно облака для регистрации имен и адресов. Компонент PNRP автоматически определяет соответствующие облака, к которым требуется присоединиться, и адреса для публикации в них.</span><span class="sxs-lookup"><span data-stu-id="5cb0f-105">With the simplified PNRP API, clouds are not explicitly specified to register the name and addresses; the PNRP component automatically determines the appropriate clouds to join and the addresses to publish within the clouds.</span></span>  
  
 <span data-ttu-id="5cb0f-106">В оптимально упрощенном разрешении имен PNRP в системе Windows Vista PNRP-имена теперь интегрированы в функцию Windows Sockets getaddrinfo().</span><span class="sxs-lookup"><span data-stu-id="5cb0f-106">For highly simplified PNRP name resolution in Windows Vista, PNRP names are now integrated into the getaddrinfo() Windows Sockets function.</span></span> <span data-ttu-id="5cb0f-107">При использовании PNRP для преобразования имени в IPv6-адрес приложения могут пользоваться функцией getaddrinfo() для преобразования полного доменного имени (FQDN) name.prnp.net, в котором name — это имя однорангового узла, которое преобразуется.</span><span class="sxs-lookup"><span data-stu-id="5cb0f-107">To use PNRP to resolve a name to an IPv6 address, applications can use the getaddrinfo() function to resolve the Fully Qualified Domain Name (FQDN) name.prnp.net, in which name is peer name being resolved.</span></span> <span data-ttu-id="5cb0f-108">Домен pnrp.net — это зарезервированный домен в Windows Vista для разрешения имен PNRP.</span><span class="sxs-lookup"><span data-stu-id="5cb0f-108">The pnrp.net domain is a reserved domain in Windows Vista for PNRP name resolution.</span></span>  
  
 <span data-ttu-id="5cb0f-109">Передача сообщений между одноранговыми приложениями по-прежнему осуществляется с применением базовых архитектур, таких как PeerChannel и [Большие наборы данных и потоковая передача](../wcf/feature-details/large-data-and-streaming.md) WCF.</span><span class="sxs-lookup"><span data-stu-id="5cb0f-109">Message passing between PeerToPeer applications is still handled by underlying architectures such as PeerChannel and WCF [Large Data and Streaming](../wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb0f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5cb0f-110">See also</span></span>

- <xref:System.Net.PeerToPeer>
