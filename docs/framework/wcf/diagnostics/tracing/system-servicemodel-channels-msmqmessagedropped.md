---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 55b489bcad85eff5adba16f6f40493c88e476505
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
Сообщение удалено из очереди MSMQ.  
  
## <a name="description"></a>Описание  
 Данная трассировка указывает, что сообщение MSMQ было удалено. Сообщения MSMQ могут быть удалены, если [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (при использовании либо с классом NetMsmqBinding, либо с классом MsmqIntegrationBinding) не удается их обработать. Такие сообщения считаются подозрительными.  
  
 Подозрительное сообщение удаляется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`. Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.  
  
 В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546)
