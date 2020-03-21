---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674801"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
Сообщение удалено из очереди MSMQ.  
  
## <a name="description"></a>Описание  
 Данная трассировка указывает, что сообщение MSMQ было удалено. Сообщения МСМЗ могут быть удалены, когда Windows Communication Foundation (WCF) (используется либо с NetMsmqBinding, либо msmqIntegrationBinding) не может их обрабатывать. Такие сообщения считаются подозрительными.  
  
 Подозрительное сообщение отбрасывается, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`. Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.  
  
 Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)  
  
## <a name="see-also"></a>См. также раздел

- [Трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md)
