---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205884"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
Сообщение удалено из очереди MSMQ.  
  
## <a name="description"></a>Описание  
 Данная трассировка указывает, что сообщение MSMQ было отброшено. Сообщения MSMQ может быть удален, когда Windows Communication Foundation (WCF) (используется с классом NetMsmqBinding или MsmqIntegrationBinding) не может их обработать. Такие сообщения считаются подозрительными.  
  
 Подозрительное сообщение удаляется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`. Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.  
  
 См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546)
