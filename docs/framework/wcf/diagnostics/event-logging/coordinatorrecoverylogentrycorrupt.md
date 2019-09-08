---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797982"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a>CoordinatorRecoveryLogEntryCorrupt
ИД: 139  
  
 "Уровень серьезности" — Ошибка  
  
 Категори трансактионбридже  
  
## <a name="description"></a>Описание  
 Это событие показывает, что запись в журнале восстановления координатора была повреждена и ее не удалось десериализовать. Эта ошибка может привести к потере данных. В событии указаны идентификатор транзакции, данные о восстановлении (в кодировке Base64), исключение, имя и ИД процесса.  
  
## <a name="see-also"></a>См. также

- [Ведение журнала событий](index.md)
- [Общие справочные сведения о событиях](events-general-reference.md)
