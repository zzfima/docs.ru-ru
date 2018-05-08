---
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: ac0a7b7d409ca2273b9d56adbfe054afebb6ddda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Процедура свойства let не определена, а процедура свойства get не вернула объект
Некоторые свойства, методы и операции применимы только к `Collection` объектов. Указанные операция или свойство применимы только к коллекциям, но объект не является коллекцией.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объекта.  
  
2.  Посмотрите на `Add` метод, используемый для добавления в коллекцию, чтобы убедитесь, что синтаксис правильный, и все идентификаторы, правильность написания.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Collection>
