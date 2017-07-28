---
title: "Служба: прослушиватели каналов и каналы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Служба: прослушиватели каналов и каналы
Есть три категории объектов каналов: каналы, прослушиватели каналов и фабрики каналов.Каналы — это интерфейс между приложением и стеком канала.Прослушиватели каналов отвечают за создание каналов на принимающей \(ожидающей передачи данных\) стороне, обычно в ответ на новое входящее сообщение или подключение.Фабрики каналов отвечают за создание каналов на передающей стороне для инициации связи с конечной точкой.  
  
## Прослушиватели каналов и каналы  
 Прослушиватели каналов отвечают за создание каналов и прием сообщений с более низкого уровня или из сети.Принятые сообщения доставляются на уровень выше с помощью канала, созданного прослушивателем каналов.  
  
 Следующая схема показывает процесс приема сообщения и доставки его на уровень выше.  
  
 ![Прослушиватели каналов и каналы](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc\_WCFChannelsigure1HighLevelc")  
Прослушиватель каналов принимает сообщения и доставляет их на уровень выше через каналы.  
  
 Процесс можно концептуально представить в виде очереди внутри каждого канала, хотя реализация может не использовать очередь.Прослушиватель канала отвечает за прием сообщений с более низкого уровня или из сети и добавление их в очередь.Канал отвечает за получение сообщений из очереди и передачу их на уровень выше, откуда приходит запрос на сообщение, например вызовом команды `Receive` для данного канала.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены вспомогательные базовые классы для этого процесса.\(Схему обсуждаемых здесь вспомогательных классов каналов см. в разделе [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md).\)  
  
-   Класс <xref:System.ServiceModel.Channels.CommunicationObject> реализует интерфейс <xref:System.ServiceModel.ICommunicationObject> и принудительно создает конечный автомат, описанный в пункте 2 раздела [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> реализует объект <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет универсальный базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase> и <xref:System.ServiceModel.Channels.ChannelListenerBase>.Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> — базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.  
  
-   Класс``<xref:System.ServiceModel.Channels.ChannelFactoryBase> реализует класс <xref:System.ServiceModel.Channels.ChannelManagerBase> и интерфейс <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет перегрузки `CreateChannel` в один абстрактный метод `OnCreateChannel`.  
  
-   Класс <xref:System.ServiceModel.Channels.ChannelListenerBase> реализует интерфейс <xref:System.ServiceModel.Channels.IChannelListener>.Он отвечает за базовое управление состоянием.  
  
 Дальнейшее обсуждение основано на примере [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## Создание прослушивателя каналов  
 Класс``UdpChannelListener, реализованный в образце, унаследован от класса <xref:System.ServiceModel.Channels.ChannelListenerBase>.Он использует один UDP\-сокет для приема датаграмм.Метод `OnOpen` принимает данные через UDP\-сокет в асинхронном цикле.Затем данные преобразуются в сообщения с помощью системы кодирования:  
  
```  
message = UdpConstants.MessageEncoder.ReadMessage(  
  new ArraySegment<byte>(buffer, 0, count),   
  bufferManager  
);  
```  
  
 Поскольку один канал датаграмм представляет сообщения, приходящие из нескольких источников, `UdpChannelListener` — одноэлементный прослушиватель.С этим прослушивателем в каждый момент времени может быть связано не более одного активного интерфейса <xref:System.ServiceModel.Channels.IChannel>``.В примере создается новый экземпляр только в том случае, если канал, возвращенный методом <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>, был впоследствии освобожден.Когда сообщение принято, оно ставится в очередь в этот одноэлементный канал.  
  
### UdpInputChannel  
 Класс `UdpInputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IInputChannel>.Он состоит из очереди входящих сообщений, которая заполняется сокетом прослушивателя `UdpChannelListener`.Эти сообщения удаляются из очереди с помощью метода <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>.