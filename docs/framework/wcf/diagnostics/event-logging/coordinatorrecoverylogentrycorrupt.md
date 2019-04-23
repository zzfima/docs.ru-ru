---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121632"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a>CoordinatorRecoveryLogEntryCorrupt
ИД: 139  
  
 Уровень серьезности: Error  
  
 Категория: TransactionBridge  
  
## <a name="description"></a>Описание  
 Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать. Эта ошибка может привести к потере данных. В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.  
  
## <a name="see-also"></a>См. также

- [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
