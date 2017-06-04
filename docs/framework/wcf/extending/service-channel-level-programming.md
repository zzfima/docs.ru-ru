---
title: "Программирование служб на уровне канала | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Программирование служб на уровне канала
В данном разделе описывается, как создать приложение службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], не используя класс <xref:System.ServiceModel.ServiceHost?displayProperty=fullName> и связанную с ним объектную модель.  
  
## Получение сообщений  
 Для того чтобы подготовиться к получению и обработке сообщений, необходимо выполнить следующие действия.  
  
1.  Создайте привязку.  
  
2.  Создайте прослушиватель каналов.  
  
3.  Откройте прослушиватель каналов.  
  
4.  Прочтите запрос и отправьте ответ.  
  
5.  Закройте все объекты каналов.  
  
#### Создание привязки  
 Первым шагом для прослушивания и получения сообщений является создание привязки.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поставляется с несколькими встроенными или предоставляемыми системой привязками, которые можно использовать напрямую путем создания экземпляра одной из них.Кроме того, всегда можно создать собственную пользовательскую привязку, создав класс CustomBinding, что и делает код в примере 1.  
  
 Пример кода, показанный ниже, создает экземпляр класса <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> и добавляет элемент <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> в его коллекцию элементов, то есть коллекцию элементов привязки, используемую для построения стека канала.Поскольку коллекция элементов в этом примере состоит только из экземпляров класса <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, у получившегося стека канала имеется только канал транспорта HTTP.  
  
#### Создание прослушивателя каналов  
 После создания привязки вызывается метод <xref:System.ServiceModel.Channels.Binding.BuildChannelListener%601%2A?displayProperty=fullName>, с помощью которого создается прослушиватель канала, параметр Type которого указывает форму создаваемого канала.В этом примере используется интерфейс <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=fullName>, поскольку требуется ожидать передачи данных для входящих сообщений в рамках шаблона обмена сообщениями запрос\-ответ.  
  
 Интерфейс <xref:System.ServiceModel.Channels.IReplyChannel> используется для приема сообщений запросов и отправки обратно сообщений ответов.Вызов метода <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=fullName> возвращает интерфейс <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName>, с помощью которого можно принимать сообщения запросов и отправлять обратно сообщения ответов.  
  
 При создании прослушивателя передается сетевой адрес, на котором он ожидает передачи данных, в данном случае `http://localhost:8080/channelapp`.В общем случае каждый канал транспорта поддерживает одну или, возможно, несколько схем адресов, например HTTP\-транспорт поддерживает как схему HTTP, так и HTTPS.  
  
 Также при создании прослушивателя передается пустая коллекция <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=fullName>.Параметр привязки — механизм передачи параметра, который определяет, как будет устроен прослушиватель.В нашем примере параметры такого рода не используются, поэтому передается пустая коллекция.  
  
#### Ожидание передачи входящих сообщений  
 Затем вызывается метод прослушивателя <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> и запускается прием каналов.Поведение метода <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=fullName> зависит от того, использует транспорт подключения или нет.В случае транспортов, использующих подключения, метод <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> блокируется до тех пор, пока не поступит запрос на новое соединение; в этот момент он возвращает новый канал, представляющий новое соединение.Для транспортов, не использующих подключение, например HTTP, метод <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> немедленно возвращает один и единственный канал, созданный прослушивателем транспорта.  
  
 В данном примере прослушиватель возвращает канал, реализующий интерфейс <xref:System.ServiceModel.Channels.IReplyChannel>.Для получения сообщений на этом канале в первую очередь необходимо вызвать для него метод <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName>, чтобы перевести его в состояние готовности к взаимодействию.Затем вызвать метод <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>, который блокируется до прибытия сообщения.  
  
#### Чтение запроса и отправка ответа  
 Когда метод <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> возвращает объект <xref:System.ServiceModel.Channels.RequestContext>, можно получить принятое сообщение из его свойства <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A>.Можно сохранить действие сообщения и содержимое его тела \(предполагая, что это строка\).  
  
 Для отправки ответа создается новое сообщение, в данном случае передающее обратно строковые данные, полученные в запросе.Затем вызывается метод <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> для отправки ответного сообщения.  
  
#### Закрытие объектов  
 Во избежание утечки ресурсов очень важно закрывать объекты, используемые во взаимодействии, если они больше не требуются.В данном примере закрываются сообщение запроса, контекст запроса, канал и прослушиватель.  
  
 В следующем примере показана базовая служба: прослушиватель канала принимает одно сообщение.Реальная служба продолжает прием каналов и получение сообщений до своего завершения.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]