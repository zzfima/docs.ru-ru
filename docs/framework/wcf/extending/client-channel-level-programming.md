---
title: "Программирование клиентов на уровне канала"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c3d9bc1819045c8261f003cbab52dd71c4da408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="1dfd0-102">Программирование клиентов на уровне канала</span><span class="sxs-lookup"><span data-stu-id="1dfd0-102">Client Channel-Level Programming</span></span>
<span data-ttu-id="1dfd0-103">В данном разделе описывается, как создать клиентское приложение [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], не используя класс <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> и связанную с ним объектную модель.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-103">This topic describes how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="1dfd0-104">Отправка сообщений</span><span class="sxs-lookup"><span data-stu-id="1dfd0-104">Sending Messages</span></span>  
 <span data-ttu-id="1dfd0-105">Чтобы подготовиться к отправке сообщений и получению и обработке ответов, необходимы следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1.  <span data-ttu-id="1dfd0-106">Создайте привязку.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-106">Create a binding.</span></span>  
  
2.  <span data-ttu-id="1dfd0-107">Создайте фабрику каналов.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-107">Build a channel factory.</span></span>  
  
3.  <span data-ttu-id="1dfd0-108">Создайте канал.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-108">Create a channel.</span></span>  
  
4.  <span data-ttu-id="1dfd0-109">Отправьте запрос и прочитайте ответ.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-109">Send a request and read the reply.</span></span>  
  
5.  <span data-ttu-id="1dfd0-110">Закройте все объекты каналов.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="1dfd0-111">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="1dfd0-111">Creating a Binding</span></span>  
 <span data-ttu-id="1dfd0-112">Аналогично принимающей (см. [программирования на уровне канала службы](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), отправка сообщений начинается при создании привязки.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-112">Similar to the receiving case (see [Service Channel-Level Programming](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="1dfd0-113">В данном примере создается новая привязка <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, и в коллекцию ее элементов добавляется элемент <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="1dfd0-114">Создание фабрики каналов</span><span class="sxs-lookup"><span data-stu-id="1dfd0-114">Building a ChannelFactory</span></span>  
 <span data-ttu-id="1dfd0-115">На этот раз вместо того чтобы создавать прослушиватель каналов <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, следует создать производство каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> вызовом метода <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> в привязке с параметром типа <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1dfd0-116">Прослушиватели каналов используются ожидающей входящих сообщений стороной, а фабрики каналов - стороной, которая инициирует связь для создания канала.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="1dfd0-117">Точно так же, как при работе с прослушивателями каналов, фабрики каналов можно использовать только после того, как они будут открыты.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="1dfd0-118">Создание канала</span><span class="sxs-lookup"><span data-stu-id="1dfd0-118">Creating a Channel</span></span>  
 <span data-ttu-id="1dfd0-119">Затем, чтобы создать канал <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>, необходимо вызвать метод <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="1dfd0-120">Этот вызов принимает адрес конечной точки, с которой необходимо установить связь, используя вновь создаваемый канал.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="1dfd0-121">После создания канала необходимо вызвать для него функцию "Открыть", чтобы подготовить его к взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="1dfd0-122">В зависимости от особенностей транспорта подобный вызов функции "Открыть" может инициировать соединение с целевой конечной точкой или не выполнить никаких действий в сети.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="1dfd0-123">Отправка запроса и чтение ответа</span><span class="sxs-lookup"><span data-stu-id="1dfd0-123">Sending a Request and Reading the Reply</span></span>  
 <span data-ttu-id="1dfd0-124">После открытия канала можно создать сообщение, воспользоваться методом запроса канала для отправки запроса и ожидать ответа.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="1dfd0-125">По возвращении этого метода приходит ответное сообщение, прочитав которое, можно узнать, каков был ответ конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="1dfd0-126">Закрытие объектов</span><span class="sxs-lookup"><span data-stu-id="1dfd0-126">Closing Objects</span></span>  
 <span data-ttu-id="1dfd0-127">Во избежание утечки ресурсов следует закрывать объекты, используемые во взаимодействии, если они больше не требуются.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="1dfd0-128">В следующем примере кода показан основной клиент, использующий фабрику каналов для отправки сообщения и чтения ответа.</span><span class="sxs-lookup"><span data-stu-id="1dfd0-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
