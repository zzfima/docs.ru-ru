---
title: Обработка ошибок WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d951c0d85294dfcef56e231f7702cb2d37efa967
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="wcf-error-handling"></a>Обработка ошибок WCF
Ошибки, с которыми столкнулось приложение WCF, относится к одной из трех групп:  
  
1.  Ошибки обмена данными  
  
2.  Ошибки прокси-сервера/канала  
  
3.  Ошибки приложения  
  
 Ошибки обмена данными возникают, когда сеть недоступна, клиент использует неверный адрес или узел службы не прослушивает входящие сообщения. Ошибки данного типа возвращаются клиенту в виде производных классов <xref:System.ServiceModel.CommunicationException> или <xref:System.ServiceModel.CommunicationException>.  
  
 Ошибки прокси-сервера/канала - это ошибки, возникающие непосредственно в канале или на прокси-сервере. К ошибкам этого типа относятся попытка использовать прокси-сервер или канал, который был закрыт, несоответствие контракта между клиентом и службой или отклонение службой учетных данных клиента. Относящихся к этой категории ошибок различных типов настолько много, что их невозможно здесь перечислить. Ошибки этого типа возвращаются клиенту в исходном виде (какие-либо преобразования над объектами исключений не выполняются).  
  
 Ошибки приложения возникают во время выполнения одной из операций службы. Ошибки такого рода передаются клиенту как <xref:System.ServiceModel.FaultException> или <xref:System.ServiceModel.FaultException%601>.  
  
 Обработка ошибок в WCF выполняется одним или несколькими методами из следующих:  
  
-   Непосредственная обработка возникшего исключения. Этот метод применяется только для ошибок обмена данными и ошибок прокси-сервера/канала.  
  
-   Использование контрактов сбоя  
  
-   Реализация интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler>  
  
-   Обработка событий <xref:System.ServiceModel.ServiceHost>  
  
## <a name="fault-contracts"></a>Контракты сбоя  
 Контракты сбоев позволяют определять ошибки, которые могут возникать во время выполнения работы службы, независимо от платформы. По умолчанию все ошибки, возникающие при работе службы, возвращаются клиенту в виде объекта <xref:System.ServiceModel.FaultException>. Объект <xref:System.ServiceModel.FaultException> содержит очень мало сведений. Для управления тем, какие сведения передаются клиенту, можно определить контракт сбоя и возвращать ошибки в виде исключения <xref:System.ServiceModel.FaultException%601>. Дополнительные сведения см. в разделе [указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="ierrorhandler"></a>IErrorHandler  
 Интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler> обеспечивает больший контроль над тем, как приложение WCF будет реагировать на ошибки.  Он предоставляет разработчику полный доступ над содержанием сообщений об ошибках, которые возвращаются клиенту, и позволяет выполнять пользовательскую обработку ошибок, например ведение журнала.  Дополнительные сведения о <xref:System.ServiceModel.Dispatcher.IErrorHandler> и [расширение управления через обработка ошибок и отчеты](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
## <a name="servicehost-events"></a>События ServiceHost  
 Класс <xref:System.ServiceModel.ServiceHost> применяется для размещения служб и определяет несколько событий, которые могут потребоваться для обработки ошибок. Пример:  
  
1.  <!--zz <xref:System.ServiceModel.ServiceHost.Faulted>-->  `System.ServiceModel.ServiceHost.Faulted`
  
2. <!--zz  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  --> `System.ServiceModel.ServiceHost.UnknownMessageReceived`
  
 Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceHost>.
