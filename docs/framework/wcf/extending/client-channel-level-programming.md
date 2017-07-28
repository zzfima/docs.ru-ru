---
title: "Программирование клиентов на уровне канала | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Программирование клиентов на уровне канала
В данном разделе описывается, как создать клиентское приложение [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], не используя класс <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> и связанную с ним объектную модель.  
  
## Отправка сообщений  
 Чтобы подготовиться к отправке сообщений и получению и обработке ответов, необходимы следующие действия.  
  
1.  Создайте привязку.  
  
2.  Создайте фабрику каналов.  
  
3.  Создайте канал.  
  
4.  Отправьте запрос и прочитайте ответ.  
  
5.  Закройте все объекты каналов.  
  
#### Создание привязки  
 Процедура отправки сообщений аналогична процедуре их получения \(см. раздел [Программирование служб на уровне канала](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)\) в том, что в первую очередь создается привязка.В данном примере создается новая привязка <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>, и в коллекцию ее элементов добавляется элемент <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName>.  
  
#### Создание фабрики каналов  
 На этот раз вместо того чтобы создавать прослушиватель каналов <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=fullName>, следует создать производство каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> вызовом метода <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=fullName> в привязке с параметром типа <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName>.Прослушиватели каналов используются ожидающей входящих сообщений стороной, а фабрики каналов — стороной, которая инициирует связь для создания канала.Точно так же, как при работе с прослушивателями каналов, фабрики каналов можно использовать только после того, как они будут открыты.  
  
#### Создание канала  
 Затем, чтобы создать канал <xref:System.ServiceModel.Channels.IRequestChannel>, необходимо вызвать метод <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=fullName>.Этот вызов принимает адрес конечной точки, с которой необходимо установить связь, используя вновь создаваемый канал.После создания канала необходимо вызвать для него функцию "Открыть", чтобы подготовить его к взаимодействию.В зависимости от особенностей транспорта подобный вызов функции "Открыть" может инициировать соединение с целевой конечной точкой или не выполнить никаких действий в сети.  
  
#### Отправка запроса и чтение ответа  
 После открытия канала можно создать сообщение, воспользоваться методом запроса канала для отправки запроса и ожидать ответа.По возвращении этого метода приходит ответное сообщение, прочитав которое, можно узнать, каков был ответ конечной точки.  
  
#### Закрытие объектов  
 Во избежание утечки ресурсов следует закрывать объекты, используемые во взаимодействии, если они больше не требуются.  
  
 В следующем примере кода показан основной клиент, использующий фабрику каналов для отправки сообщения и чтения ответа.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]