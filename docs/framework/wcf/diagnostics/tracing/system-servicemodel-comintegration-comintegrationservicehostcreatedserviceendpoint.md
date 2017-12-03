---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 474895e7fbcf1b9ed7ad7da6d28313ae4894f720
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Не удается переместить или удалить сообщение.  
  
## <a name="description"></a>Описание  
 Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.  
  
 Сообщения MSMQ используются [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (при использовании с привязкой NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка относится к выбранному значению свойства `ReceiveErrorHandling` привязки NetMsmqBinding или MsmqIntegrationBinding.  
  
 Эта трассировка не указывает на общий сбой системы. Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения. В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
