---
title: "Одноранговая сеть"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a26f10a323b44e7954245ab90a02f62745e84e87
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="b1f97-102">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="b1f97-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="b1f97-103">Одноранговый канал — это многопользовательская одноранговая (P2P) технология связи в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1f97-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="b1f97-104">Она предоставляет надежный и масштабируемый одноранговый канал связи на основе обмена сообщениями для разработчиков приложений.</span><span class="sxs-lookup"><span data-stu-id="b1f97-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="b1f97-105">Одним из типичных примеров многопользовательского приложения, в котором могут использоваться преимущества однорангового канала, является приложение для совместной работы, такое как разговор, в котором группа людей общается друг с другом по одноранговой сети без использования серверов.</span><span class="sxs-lookup"><span data-stu-id="b1f97-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="b1f97-106">Одноранговый канал поддерживает одноранговую совместную работу, распространение содержимого, балансировку нагрузки и распределенную обработку сценариев потребителя и предприятия.</span><span class="sxs-lookup"><span data-stu-id="b1f97-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="b1f97-107">Одноранговый канал включается в [!INCLUDE[wv](../../../../includes/wv-md.md)] по умолчанию, как и все элементы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1f97-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="b1f97-108">Для того чтобы получить доступ к классам однорангового канала, необходимо добавить в проект ссылки на System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="b1f97-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="b1f97-109">В следующих разделах содержится информация об одноранговых сетях и использовании классов одноранговых каналов для создания сетевых приложений с поддержкой одноранговых объектов.</span><span class="sxs-lookup"><span data-stu-id="b1f97-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1f97-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b1f97-110">In This Section</span></span>  
 <span data-ttu-id="b1f97-111">[Сценарии одноранговых каналов](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): описание сценариев разработки, поддерживаемых интерфейсов API одноранговых каналов, например публикации или подписки обмена сообщениями и совместной работы, распределенная обработка и игры.</span><span class="sxs-lookup"><span data-stu-id="b1f97-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="b1f97-112">[Основные понятия одноранговых каналов](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): описываются одноранговые сетки, одноранговые узлы, безопасность одноранговых каналов и одноранговые распознаватели.</span><span class="sxs-lookup"><span data-stu-id="b1f97-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="b1f97-113">[Создание приложения одноранговых каналов](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): руководство по разработке приложений одноранговых каналов.</span><span class="sxs-lookup"><span data-stu-id="b1f97-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="b1f97-114">Примеры кода одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="b1f97-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="b1f97-115">Одноранговый канал настраиваемого распознавателя одноранговых узлов</span><span class="sxs-lookup"><span data-stu-id="b1f97-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/library/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="b1f97-116">Блог команды разработчиков одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="b1f97-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="b1f97-117">[Блог команды разработчиков одноранговых каналов](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="b1f97-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
