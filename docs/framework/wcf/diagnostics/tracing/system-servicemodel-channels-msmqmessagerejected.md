---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674774"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ отклонила сообщение.  
  
## <a name="description"></a>Описание  
 Данная трассировка показывает, что сообщение MSMQ было отклонено.   
  
 Сообщения МСМЗ могут быть отклонены, когда Windows Communication Foundation (WCF) (используется либо с NetMsmqBinding, либо msmqIntegrationBinding) не может их обрабатывать. Такие сообщения считаются подозрительными. Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`. Отклоненное сообщение возвращается в [очередь отправителя Dead-Letter](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).  
  
 Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)  
  
 Для получения более подробной информации о том, что означает отклоненное сообщение в МСМЗ, [см.](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))  
  
## <a name="see-also"></a>См. также раздел

- [Трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Обработка подозрительных сообщений](../../feature-details/poison-message-handling.md)
- [МзМаркСообщение](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
