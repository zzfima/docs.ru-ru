---
title: "Создание элемента привязки BindingElement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdd547a62391d11050071e1ede648b28c28bd3f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="creating-a-bindingelement"></a>Создание элемента привязки BindingElement
С помощью привязок и элементов привязок (объектов, расширяющих <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>, соответственно) модель приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] связывается с фабриками каналов и прослушивателями каналов. Без привязки, с помощью пользовательских каналов требует программирования на уровне канала как описано в [программирования на уровне канала службы](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) и [программирования на уровне канала клиента](../../../../docs/framework/wcf/extending/client-channel-level-programming.md). В этом разделе обсуждаются минимальным требованием для использования канала в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], разработку <xref:System.ServiceModel.Channels.BindingElement> для канала и включить использование из приложения, как описано в шаге 4 [разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="overview"></a>Обзор  
 Создание элемента <xref:System.ServiceModel.Channels.BindingElement> для канала позволяет разработчикам использовать его в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Объекты <xref:System.ServiceModel.Channels.BindingElement> могут использоваться из класса <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> для подключения приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] к каналу без точных сведений о типе канала.  
  
 Один раз <xref:System.ServiceModel.Channels.BindingElement> был создан, можно включить дополнительные функциональные возможности, в зависимости от требований, оставшиеся шаги разработки канала описаны в следующих [разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Добавление элемента привязки  
 Чтобы реализовать настраиваемый элемент <xref:System.ServiceModel.Channels.BindingElement>, напишите класс, наследуемый от <xref:System.ServiceModel.Channels.BindingElement>. Например, если разработан канал `ChunkingChannel`, который может разделять большие сообщения на блоки и восстанавливать сообщения на другой стороне, этот канал можно использовать в любой привязке, реализуя элемент <xref:System.ServiceModel.Channels.BindingElement> и настраивая привязку для использования этого элемента. Далее в этом разделе канал `ChunkingChannel` используется в качестве примера для демонстрации требований к реализации элемента привязки.  
  
 Элемент `ChunkingBindingElement` отвечает за создание фабрики `ChunkingChannelFactory` и прослушивателя `ChunkingChannelListener`. Он переопределяет реализации <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A> и <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A> и проверяет, что параметром типа является <xref:System.ServiceModel.Channels.IDuplexSessionChannel> (в данном примере это единственная форма канала, поддерживаемая каналом `ChunkingChannel`) и что другие элементы привязки поддерживают эту форму канала.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> сначала проверяет возможность создания затребованной формы канала, затем получает список действий, которые должны быть выполнены для разделения сообщения на блоки, после чего создает новую фабрику `ChunkingChannelFactory`, передавая ее фабрике внутреннего канала. (В случае создания элемента привязки транспорта этот элемент является последним элементом в стеке привязок и, следовательно, должен создать прослушиватель канала или фабрику канала).  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> имеет аналогичную реализацию для создания прослушивателя `ChunkingChannelListener` и передаче его прослушивателю внутреннего канала.  
  
 В качестве другого примера, используя канал транспорта [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образец предоставляет следующие переопределения.  
  
 В этом примере в качестве элемента привязки выступает элемент `UdpTransportBindingElement`, являющийся производным элемента <xref:System.ServiceModel.Channels.TransportBindingElement>. Он переопределяет следующие методы для создания фабрик, связанных с каналом.  
  
```  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
            return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
            return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 Он также содержит члены для клонирования элемента `BindingElement` и возврата схемы (soap.udp).  
  
#### <a name="protocol-binding-elements"></a>Элементы привязки протоколов  
 Новые элементы привязки могут заменять или дополнять любые из включенных элементов привязки, добавляя новые типы транспорта, кодирования или протоколы верхних уровней. Чтобы создать новый элемент привязки протокола, начните с расширения класса <xref:System.ServiceModel.Channels.BindingElement>. Как минимум, затем необходимо реализовать <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> и реализовать `ChannelProtectionRequirements` с помощью <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. В результате будут возвращены требования <xref:System.ServiceModel.Security.ChannelProtectionRequirements> для этого элемента привязки.  Для получения дополнительной информации см. <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 Метод <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> должен вернуть новую копию данного элемента привязки. Авторам элемента привязки рекомендуется реализовать метод <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, используя конструктор копии, который вызывает базовый конструктор копии и затем клонирует любые дополнительные поля в этом классе.  
  
#### <a name="transport-binding-elements"></a>Элементы привязки транспорта  
 Чтобы создать новый элемент привязки транспорта, расширьте интерфейс <xref:System.ServiceModel.Channels.TransportBindingElement>. Затем, как минимум, необходимо реализовать метод <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> и свойство <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Этот метод должен вернуть новую копию данного элемента привязки.  Авторам элемента привязки рекомендуется реализовать метод Clone с помощью конструктора копии, который вызывает базовый конструктор копии и затем клонирует любые дополнительные поля в этом классе.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A>. Свойство получения схемы <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> возвращает схему универсального кода ресурса (URI) для транспортного протокола, представленного элементом привязки. Например <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> возвращают «http» и «net.tcp» из соответствующих им <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> свойства.  
  
#### <a name="encoding-binding-elements"></a>Элементы привязки кодирования  
 Чтобы создать новые элементы привязки кодирования, начните с расширения класса <xref:System.ServiceModel.Channels.BindingElement> и реализации класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>. Затем, как минимум, необходимо реализовать методы <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType> и свойство <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Возвращает новую копию этого элемента привязки. Авторам элемента привязки рекомендуется реализовать метод <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>, используя конструктор копии, который вызывает базовый конструктор копии и затем клонирует любые дополнительные поля в этом классе.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Возвращает фабрику <xref:System.ServiceModel.Channels.MessageEncoderFactory>, предоставляющую дескриптор фактическому классу, который реализует новый кодировщик и должен расширить кодировщик <xref:System.ServiceModel.Channels.MessageEncoder>. Дополнительные сведения см. в разделах <xref:System.ServiceModel.Channels.MessageEncoderFactory> и <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Возвращает версию <xref:System.ServiceModel.Channels.MessageVersion>, применяемую в данной кодировке, которая представляет используемые версии протокола SOAP и WS-Addressing.  
  
 Полный список необязательных методов и свойств для определяемых пользователем элементов привязки кодирования см. в разделе <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Дополнительные сведения о создании нового элемента привязки см. в разделе [привязки привязанных к](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 После создания элемента привязки для канала, вернуться к [разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md) раздела, чтобы посмотреть, требуется ли добавить поддержку файла конфигурации элемента привязки, если и как добавить поддержку публикации метаданных, и и способ создания пользовательской привязки, в котором используется элементом привязки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md)  
 [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
