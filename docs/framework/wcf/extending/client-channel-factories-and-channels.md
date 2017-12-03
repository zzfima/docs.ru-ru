---
title: "Клиент: фабрики каналов и каналы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4a841fec01b3a0ef29cd836cccf3f337f29ddb6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="client-channel-factories-and-channels"></a><span data-ttu-id="12729-102">Клиент: фабрики каналов и каналы</span><span class="sxs-lookup"><span data-stu-id="12729-102">Client: Channel Factories and Channels</span></span>
<span data-ttu-id="12729-103">В этом разделе рассматривается создание фабрик каналов и каналов.</span><span class="sxs-lookup"><span data-stu-id="12729-103">This topic discusses the creation of channel factories and channels.</span></span>  
  
## <a name="channel-factories-and-channels"></a><span data-ttu-id="12729-104">Фабрики каналов и каналы</span><span class="sxs-lookup"><span data-stu-id="12729-104">Channel Factories and Channels</span></span>  
 <span data-ttu-id="12729-105">Фабрики каналов отвечают за создание каналов.</span><span class="sxs-lookup"><span data-stu-id="12729-105">Channel factories are responsible for creating channels.</span></span> <span data-ttu-id="12729-106">Каналы, создаваемые фабриками каналов, используются для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="12729-106">Channels created by channel factories are used for sending messages.</span></span> <span data-ttu-id="12729-107">Эти каналы отвечают за получение сообщения от вышестоящего уровня, выполнение той или иной обработки и отправку сообщения нижестоящему уровню.</span><span class="sxs-lookup"><span data-stu-id="12729-107">These channels are responsible for getting the message from the layer above, performing whatever processing is necessary, then sending the message to the layer below.</span></span> <span data-ttu-id="12729-108">Следующий рисунок иллюстрирует этот процесс.</span><span class="sxs-lookup"><span data-stu-id="12729-108">The following graphic illustrates this process.</span></span>  
  
 <span data-ttu-id="12729-109">![Каналы и производства клиента](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span><span class="sxs-lookup"><span data-stu-id="12729-109">![Client Factories and Channels](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span></span>  
<span data-ttu-id="12729-110">Фабрика каналов создает каналы.</span><span class="sxs-lookup"><span data-stu-id="12729-110">A channel factory creates channels.</span></span>  
  
 <span data-ttu-id="12729-111">При закрытии фабрики каналов отвечают за закрытие всех созданных ими каналов, которые еще не закрыты.</span><span class="sxs-lookup"><span data-stu-id="12729-111">When closed, channel factories are responsible for closing any channels they created that are not yet closed.</span></span> <span data-ttu-id="12729-112">Обратите внимание, что модель в данном случае асимметрична: когда закрывается прослушиватель каналов, он прекращает только принимать новые каналы, однако оставляет существующие каналы открытыми, чтобы они могли продолжить получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="12729-112">Note that the model is asymmetric here because when a channel listener is closed, it only stops accepting new channels but leaves existing channels open so that they can continue receiving messages.</span></span>  
  
 <span data-ttu-id="12729-113">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены вспомогательные базовые классы для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="12729-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides base class helpers for this process.</span></span> <span data-ttu-id="12729-114">(Схема канала вспомогательных классов, описанных в этом разделе, см. [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="12729-114">(For a diagram of the channel helper classes discussed in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span></span>  
  
-   <span data-ttu-id="12729-115"><xref:System.ServiceModel.Channels.CommunicationObject> Класс реализует <xref:System.ServiceModel.ICommunicationObject> и вводит в действие конечного автомата, описанной на шаге 2 [разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).</span><span class="sxs-lookup"><span data-stu-id="12729-115">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
-   <span data-ttu-id="12729-116">''<xref:System.ServiceModel.Channels.ChannelManagerBase> Класс реализует <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет единый базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12729-116">The``<xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> and <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="12729-117">Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> - базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="12729-117">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
-   <span data-ttu-id="12729-118">''<xref:System.ServiceModel.Channels.ChannelFactoryBase> Класс реализует <xref:System.ServiceModel.Channels.ChannelManagerBase> и <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет `CreateChannel` в одну из перегруженных функций `OnCreateChannel` абстрактный метод.</span><span class="sxs-lookup"><span data-stu-id="12729-118">The``<xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
-   <span data-ttu-id="12729-119">''<xref:System.ServiceModel.Channels.ChannelListenerBase> Класс реализует <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="12729-119">The``<xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="12729-120">Он отвечает за базовое управление состоянием.</span><span class="sxs-lookup"><span data-stu-id="12729-120">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="12729-121">Следующее обсуждение создается на основе [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="12729-121">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="creating-a-channel-factory"></a><span data-ttu-id="12729-122">Создание фабрики каналов</span><span class="sxs-lookup"><span data-stu-id="12729-122">Creating a Channel Factory</span></span>  
 <span data-ttu-id="12729-123">Фабрика`UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="12729-123">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="12729-124">В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений.</span><span class="sxs-lookup"><span data-stu-id="12729-124">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="12729-125">Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> для уничтожения созданного экземпляра класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.</span><span class="sxs-lookup"><span data-stu-id="12729-125">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> to tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="12729-126">Выходной канал UDP</span><span class="sxs-lookup"><span data-stu-id="12729-126">The UDP Output Channel</span></span>  
 <span data-ttu-id="12729-127">Класс`UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="12729-127">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="12729-128">Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="12729-128">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
 <span data-ttu-id="12729-129">Переопределение метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> создает сокет, используемый для отправки сообщений этому объекту <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="12729-129">The override of <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> creates a socket that is used to send messages to this <xref:System.Net.EndPoint>.</span></span>  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 <span data-ttu-id="12729-130">Канал может быть закрыт правильно или неправильно.</span><span class="sxs-lookup"><span data-stu-id="12729-130">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="12729-131">При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса.</span><span class="sxs-lookup"><span data-stu-id="12729-131">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="12729-132">Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.</span><span class="sxs-lookup"><span data-stu-id="12729-132">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 <span data-ttu-id="12729-133">Реализуйте `Send()` и `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="12729-133">Implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="12729-134">Реализация делится на две принципиальные части.</span><span class="sxs-lookup"><span data-stu-id="12729-134">This breaks down into two main sections.</span></span> <span data-ttu-id="12729-135">Сначала сериализуйте сообщение в байтовый массив:</span><span class="sxs-lookup"><span data-stu-id="12729-135">First serialize the message into a byte array:</span></span>  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="12729-136">Затем отправьте получившиеся данные по сети:</span><span class="sxs-lookup"><span data-stu-id="12729-136">Then send the resulting data on the wire:</span></span>  
  
```  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="12729-137">См. также</span><span class="sxs-lookup"><span data-stu-id="12729-137">See Also</span></span>  
 [<span data-ttu-id="12729-138">Разработка каналов</span><span class="sxs-lookup"><span data-stu-id="12729-138">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)
