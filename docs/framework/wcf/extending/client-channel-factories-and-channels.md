---
title: "Клиент: фабрики каналов и каналы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Клиент: фабрики каналов и каналы
В этом разделе рассматривается создание фабрик каналов и каналов.  
  
## Фабрики каналов и каналы  
 Фабрики каналов отвечают за создание каналов.  Каналы, создаваемые фабриками каналов, используются для отправки сообщений.  Эти каналы отвечают за получение сообщения от вышестоящего уровня, выполнение той или иной обработки и отправку сообщения нижестоящему уровню.  Следующий рисунок иллюстрирует этот процесс.  
  
 ![Фабрики клиентов и каналы](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc\_WCFChannelsigure2HIghLevelFactgoriesc")  
Фабрика каналов создает каналы.  
  
 При закрытии фабрики каналов отвечают за закрытие всех созданных ими каналов, которые еще не закрыты.  Обратите внимание, что модель в данном случае асимметрична: когда закрывается прослушиватель каналов, он прекращает только принимать новые каналы, однако оставляет существующие каналы открытыми, чтобы они могли продолжить получать сообщения.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены вспомогательные базовые классы для этого процесса.  \(Схему обсуждаемых здесь вспомогательных классов каналов см. в разделе [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md).\)  
  
-   Класс <xref:System.ServiceModel.Channels.CommunicationObject> реализует интерфейс <xref:System.ServiceModel.ICommunicationObject> и принудительно создает конечный автомат, описанный в пункте 2 раздела [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   Класс `` <xref:System.ServiceModel.Channels.ChannelManagerBase> реализует класс <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет универсальный базовый класс для классов <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=fullName> и <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=fullName>.  Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> \- базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.  
  
-   Класс `` <xref:System.ServiceModel.Channels.ChannelFactoryBase> реализует класс <xref:System.ServiceModel.Channels.ChannelManagerBase> и интерфейс <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет перегрузки `CreateChannel` в один абстрактный метод `OnCreateChannel`.  
  
-   Класс  `` <xref:System.ServiceModel.Channels.ChannelListenerBase> реализует интерфейс <xref:System.ServiceModel.Channels.IChannelListener>.  Он отвечает за базовое управление состоянием.  
  
 Дальнейшее обсуждение основано на примере [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
### Создание фабрики каналов  
 Фабрика`UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>.  В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений.  Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> для уничтожения созданного экземпляра класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.  
  
#### Выходной канал UDP  
 Класс`UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>.  Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.  
  
 Переопределение метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> создает сокет, используемый для отправки сообщений этому объекту <xref:System.Net.EndPoint>.  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 Канал может быть закрыт правильно или неправильно.  При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса.  Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
  
```  
  
 Реализуйте методы `Send()` и `BeginSend()`\/`EndSend()`.  Реализация делится на две принципиальные части.  Сначала сериализуйте сообщение в байтовый массив:  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
  
```  
  
 Затем отправьте получившиеся данные по сети:  
  
```  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## См. также  
 [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md)