---
title: "Контракты маршрутизации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Контракты маршрутизации
Контракты маршрутизации определяют схемы обмена сообщениями, которые может обрабатывать служба маршрутизации.Эти контракты являются бестиповыми, с их помощью служба может получать сообщение без набора знаний о схеме сообщения или действии.Благодаря этому служба маршрутизации может перенаправлять сообщения без дополнительной настройки под особенности маршрутизируемых сообщений.  
  
## Контракты маршрутизации  
 Поскольку служба маршрутизации принимает общий объект сообщения WCF, наиболее важным аспектом при выборе контракта является форма канала, который будет использоваться для связи с клиентами и серверами.При обработке сообщений служба маршрутизации использует симметричные циклы обработки сообщений, поэтому, как правило, форма входящего контракта должна быть такой же, как форма исходящего контракта.Однако в некоторых случаях диспетчер модели службы может изменять эти формы, например в случае, когда он преобразует дуплексный канал в канал типа «запрос\-ответ» или удаляет поддержку сеанса из канала, если она не требуется и не используется \(то есть когда **SessionMode.Allowed** с преобразованием **IInputSessionChannel** в **IInputChannel**\).  
  
 Для поддержки этих циклов сообщений служба маршрутизации предоставляет контракты из пространства имен <xref:System.ServiceModel.Routing>, которые должны использоваться при определении конечных точек службы, используемых службой маршрутизации.Эти контракты являются бестиповыми, что позволяет принимать любые типы сообщений или действия, а также позволяет службе маршрутизации обрабатывать сообщения без набора знаний их схемы.Дополнительные сведения о контрактах, используемых службой маршрутизации, см. в разделе [Routing Contracts](../../../../docs/framework/wcf/feature-details/routing-contracts.md).  
  
 Контракты, предоставляемые службой маршрутизации, находятся в пространстве имен <xref:System.ServiceModel.Routing>, они описаны в следующей таблице.  
  
|Контракт|Фигура|Форма канала|  
|--------------|------------|------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode \= SessionMode.Allowed<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true|IInputChannel \-\> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode \= SessionMode.Required<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true|IInputSessionChannel \-\> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode \= SessionMode.Allowed<br /><br /> AsyncPattern \= true|IReplyChannel \-\> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode\=SessionMode.Required<br /><br /> CallbackContract\=typeof\(ISimplexSession\)<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true<br /><br /> TransactionFlow\(TransactionFlowOption.Allowed\)|IDuplexSessionChannel \-\> IDuplexSessionChannel|  
  
## См. также  
 [Routing Service](http://msdn.microsoft.com/ru-ru/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)   
 [Введение в маршрутизацию](../../../../docs/framework/wcf/feature-details/routing-introduction.md)