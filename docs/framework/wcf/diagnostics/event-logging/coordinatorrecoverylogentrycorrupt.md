---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3f51d1269f5ca89f4f02257c8accef3423aa7eb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="coordinatorrecoverylogentrycorrupt"></a>CoordinatorRecoveryLogEntryCorrupt
Идентификатор: 139  
  
 Важность: ошибка  
  
 Категория: TransactionBridge  
  
## <a name="description"></a>Описание  
 Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать. Эта ошибка может привести к потере данных. В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.  
  
## <a name="see-also"></a>См. также  
 [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
