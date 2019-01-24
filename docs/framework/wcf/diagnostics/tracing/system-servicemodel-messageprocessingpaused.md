---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ba067303d861bbd7d88c67f6fd868bd808e07dfd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528684"
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
- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
