---
title: 'Клиент: фабрики каналов и каналы'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: c7890f5fafb4e53053c4c393a7c8af584bd7a520
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="client-channel-factories-and-channels"></a>Клиент: фабрики каналов и каналы
В этом разделе рассматривается создание фабрик каналов и каналов.  
  
## <a name="channel-factories-and-channels"></a>Фабрики каналов и каналы  
 Фабрики каналов отвечают за создание каналов. Каналы, создаваемые фабриками каналов, используются для отправки сообщений. Эти каналы отвечают за получение сообщения от вышестоящего уровня, выполнение той или иной обработки и отправку сообщения нижестоящему уровню. Следующий рисунок иллюстрирует этот процесс.  
  
 ![Каналы и производства клиента](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")  
Фабрика каналов создает каналы.  
  
 При закрытии фабрики каналов отвечают за закрытие всех созданных ими каналов, которые еще не закрыты. Обратите внимание, что модель в данном случае асимметрична: когда закрывается прослушиватель каналов, он прекращает только принимать новые каналы, однако оставляет существующие каналы открытыми, чтобы они могли продолжить получать сообщения.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены вспомогательные базовые классы для этого процесса. (Схема канала вспомогательных классов, описанных в этом разделе, см. [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md).)  
  
-   <xref:System.ServiceModel.Channels.CommunicationObject> Класс реализует <xref:System.ServiceModel.ICommunicationObject> и вводит в действие конечного автомата, описанной на шаге 2 [разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   ''<xref:System.ServiceModel.Channels.ChannelManagerBase> Класс реализует <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет единый базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>. Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> - базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.  
  
-   ''<xref:System.ServiceModel.Channels.ChannelFactoryBase> Класс реализует <xref:System.ServiceModel.Channels.ChannelManagerBase> и <xref:System.ServiceModel.Channels.IChannelFactory> и объединяет `CreateChannel` в одну из перегруженных функций `OnCreateChannel` абстрактный метод.  
  
-   ''<xref:System.ServiceModel.Channels.ChannelListenerBase> Класс реализует <xref:System.ServiceModel.Channels.IChannelListener>. Он отвечает за базовое управление состоянием.  
  
 Следующее обсуждение создается на основе [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.  
  
### <a name="creating-a-channel-factory"></a>Создание фабрики каналов  
 Фабрика`UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>. В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений. Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> для уничтожения созданного экземпляра класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.  
  
#### <a name="the-udp-output-channel"></a>Выходной канал UDP  
 Класс`UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>. Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.  
  
 Переопределение метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> создает сокет, используемый для отправки сообщений этому объекту <xref:System.Net.EndPoint>.  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 Канал может быть закрыт правильно или неправильно. При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса. Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 Реализуйте `Send()` и `BeginSend()` / `EndSend()`. Реализация делится на две принципиальные части. Сначала сериализуйте сообщение в байтовый массив:  
  
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
  
## <a name="see-also"></a>См. также  
 [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md)
