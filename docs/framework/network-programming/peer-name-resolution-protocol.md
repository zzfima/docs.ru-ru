---
title: Протокол PNRP
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: c8b7b2190349323bf212d816a77f5f7810f6ca2c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428225"
---
# <a name="peer-name-resolution-protocol"></a><span data-ttu-id="669b7-102">Протокол PNRP</span><span class="sxs-lookup"><span data-stu-id="669b7-102">Peer Name Resolution Protocol</span></span>
<span data-ttu-id="669b7-103">В одноранговых средах одноранговые узлы используют определенные системы разрешения имен для определения сетевого расположения (адреса, протоколы и порты) друг друга на основе имен и идентификаторов других типов.</span><span class="sxs-lookup"><span data-stu-id="669b7-103">In peer-to-peer environments, peers use specific name resolution systems to resolve each other's network locations (addresses, protocols, and ports) from names or other types of identifiers.</span></span> <span data-ttu-id="669b7-104">Раньше разрешение имен одноранговых узлов было затруднено из-за временного характера подключений, а также других недостатков службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="669b7-104">In the past, peer name resolution has been complicated by the inherently transient connectivity as well as other shortcomings within the Domain Name System (DNS).</span></span>  
  
 <span data-ttu-id="669b7-105">Платформа одноранговых сетей Microsoft® Windows® решает эту проблему за счет применения протокола PNRP, который представляет собой безопасный масштабируемый динамический протокол регистрации и разрешения имен, изначально разработанный для Windows XP и позднее модернизированный для Windows Vista™.</span><span class="sxs-lookup"><span data-stu-id="669b7-105">The Microsoft® Windows® Peer-to-Peer Networking platform solves this problem with the Peer Name Resolution Protocol (PNRP), a secure, scalable, and dynamic name registration and name resolution protocol first developed for Windows XP and then upgraded in Windows Vista™.</span></span> <span data-ttu-id="669b7-106">Принципы работы протокола PNRP значительно отличаются от других традиционных систем разрешения имен, что открывает перед разработчиками совершенно новые возможности.</span><span class="sxs-lookup"><span data-stu-id="669b7-106">PNRP works very differently from traditional name resolution systems, opening up exciting new possibilities for application developers.</span></span>  
  
 <span data-ttu-id="669b7-107">При использовании протокола PNRP имена одноранговых узлов могут назначаться компьютерам, отдельным приложениям или службам на компьютере.</span><span class="sxs-lookup"><span data-stu-id="669b7-107">With PNRP, peer names can be applied to the machine, or individual applications or services on the machine.</span></span> <span data-ttu-id="669b7-108">Процесс разрешения имен одноранговых узлов включает адрес, порт и, возможно, расширенные полезные данные.</span><span class="sxs-lookup"><span data-stu-id="669b7-108">A peer name resolution includes an address, port, and possibly an extended payload.</span></span> <span data-ttu-id="669b7-109">К преимуществам такой системы относятся высокая отказоустойчивость, отсутствие узких мест и механизм разрешения имен, ни при каких обстоятельствах не возвращающий устаревшие адреса, что делает этот протокол оптимальным решением для обнаружения мобильных пользователей.</span><span class="sxs-lookup"><span data-stu-id="669b7-109">Benefits of this system include fault tolerance, no bottlenecks, and name resolutions that will never return stale addresses; making the protocol an excellent solution for locating mobile users.</span></span>  
  
 <span data-ttu-id="669b7-110">С точки зрения безопасности имена одноранговых узлов могут публиковаться в безопасной (защищенной) или небезопасной (незащищенной) форме.</span><span class="sxs-lookup"><span data-stu-id="669b7-110">In terms of security, peer names can be published as secured (protected) or unsecured (unprotected).</span></span> <span data-ttu-id="669b7-111">Протокол PNRP использует шифрование с открытым ключом для защиты безопасных имен одноранговых узлов от подделки. Протокол PNRP можно использовать для присвоения имен как компьютерам, так и службам.</span><span class="sxs-lookup"><span data-stu-id="669b7-111">PNRP uses public key cryptography to protect secure peer names against spoofing; both computers and services can be named with PNRP.</span></span>  
  
<span data-ttu-id="669b7-112">Протокол PNRP характеризуется следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="669b7-112">The Peer Name Resolution Protocol demonstrates the following properties:</span></span>  
  
- <span data-ttu-id="669b7-113">Распределенность и практически полное отсутствие серверов.</span><span class="sxs-lookup"><span data-stu-id="669b7-113">Distributed and almost entirely serverless.</span></span> <span data-ttu-id="669b7-114">Использование серверов только в процессе начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="669b7-114">Servers are only required for the bootstrapping process.</span></span>  
  
- <span data-ttu-id="669b7-115">Публикация безопасных имен без привлечения третьих лиц.</span><span class="sxs-lookup"><span data-stu-id="669b7-115">Secure name publication without the involvement of third parties.</span></span> <span data-ttu-id="669b7-116">В отличие от службы DNS, публикация имен с использованием протокола PNRP осуществляется мгновенно и не требует финансовых затрат.</span><span class="sxs-lookup"><span data-stu-id="669b7-116">Unlike DNS name publication, PNRP name publication is instantaneous and without financial cost.</span></span>  
  
- <span data-ttu-id="669b7-117">Обновления протокола PNRP осуществляются в режиме реального времени, что позволяет исключить разрешение устаревших адресов.</span><span class="sxs-lookup"><span data-stu-id="669b7-117">PNRP updates in real-time, which prevents the resolution of stale addresses.</span></span>  
  
- <span data-ttu-id="669b7-118">Протокол PNRP поддерживает разрешение имен не только для компьютеров, но и для служб.</span><span class="sxs-lookup"><span data-stu-id="669b7-118">The resolution of names via PNRP extends beyond computers by also allowing name resolution for services.</span></span>  
  
## <a name="the-systemnetpeertopeer-namespace"></a><span data-ttu-id="669b7-119">Пространство имен System.Net.PeerToPeer</span><span class="sxs-lookup"><span data-stu-id="669b7-119">The System.Net.PeerToPeer namespace</span></span>  
  
- <span data-ttu-id="669b7-120">Функции протокола PNRP определены в пространстве имен <xref:System.Net.PeerToPeer> на платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="669b7-120">PNRP functionality is defined by the <xref:System.Net.PeerToPeer> namespace within the .NET Framework version 3.5.</span></span> <span data-ttu-id="669b7-121">В этом пространстве имен представлен набор типов, которые могут использоваться для регистрации и разрешения имен одноранговых узлов с использованием доступной службы PNRP.</span><span class="sxs-lookup"><span data-stu-id="669b7-121">It provides a set of types that can be used to register and resolve peer names with an available PNRP service.</span></span>  
  
- <span data-ttu-id="669b7-122">(Распознаватели PNRP и пользовательские одноранговые распознаватели, а также их экземпляры могут создаваться с использованием типов, представленных в пространстве имен <xref:System.ServiceModel.PeerResolvers>.)</span><span class="sxs-lookup"><span data-stu-id="669b7-122">(PNRP and custom peer resolvers can be created and instantiated using the types provided in the <xref:System.ServiceModel.PeerResolvers> namespace.)</span></span>  
  
- <span data-ttu-id="669b7-123">Ниже приведены базовые типы, используемые для регистрации и разрешения имен с использованием доступной службы PNRP:</span><span class="sxs-lookup"><span data-stu-id="669b7-123">The basic types used to register and resolve names with an available PNRP service are as follows:</span></span>  
  
- <span data-ttu-id="669b7-124"><xref:System.Net.PeerToPeer.Cloud>. Определяет сведения, описывающие доступное облако PNRP, включая его область действия.</span><span class="sxs-lookup"><span data-stu-id="669b7-124"><xref:System.Net.PeerToPeer.Cloud>: Defines the information describing an available PNRP cloud, including its scope.</span></span>  
  
- <span data-ttu-id="669b7-125"><xref:System.Net.PeerToPeer.PeerName>. Определяет имя однорангового узла, которое может использоваться для регистрации и последующего разрешения этого узла в облаке.</span><span class="sxs-lookup"><span data-stu-id="669b7-125"><xref:System.Net.PeerToPeer.PeerName>: Defines a peer name that can be used to register and subsequently resolve a peer within a cloud.</span></span>  
  
- <span data-ttu-id="669b7-126"><xref:System.Net.PeerToPeer.PeerNameRecord>. Определяет запись в облаке PNRP, которая содержит сведения о регистрации для однорангового узла, включая сетевые конечные точки доступа, которые могут использоваться для связи с этим узлом.</span><span class="sxs-lookup"><span data-stu-id="669b7-126"><xref:System.Net.PeerToPeer.PeerNameRecord>: Defines the record in PNRP cloud that contains the registration information for a peer, which includes the network endpoints at which the peer can be contacted.</span></span>  
  
- <span data-ttu-id="669b7-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>. Определяет процесс регистрации имени однорангового узла, включая методы запуска и остановки регистрации.</span><span class="sxs-lookup"><span data-stu-id="669b7-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Defines the registration process for a peer name, including methods to start and stop peer name registration.</span></span>  
  
- <span data-ttu-id="669b7-128"><xref:System.Net.PeerToPeer.PeerNameResolver>. Определяет процесс разрешения имени однорангового узла в его сетевые конечные точки, включая синхронные и асинхронные методы разрешения.</span><span class="sxs-lookup"><span data-stu-id="669b7-128"><xref:System.Net.PeerToPeer.PeerNameResolver>: Defines the process for resolving a peer name to its network endpoint(s), including both synchronous and asynchronous methods for resolution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669b7-129">См. также</span><span class="sxs-lookup"><span data-stu-id="669b7-129">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [<span data-ttu-id="669b7-130">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="669b7-130">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [PeerToPeer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179571)
-->
