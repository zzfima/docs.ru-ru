---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 6fb1463b811d985f54b9a99e59d1280eaa040256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482818"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Описание  
 При обработке сообщения произошло переключение потоков.  
  
 Обработка сообщения может быть приостановлена по следующим причинам:  
  
-   ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.  
  
-   Транзакция разрешена; служба обрабатывает другую транзакцию.  
  
-   Контекст синхронизации устарел.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
