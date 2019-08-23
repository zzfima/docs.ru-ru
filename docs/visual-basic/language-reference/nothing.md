---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963759"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Представляет значение по умолчанию для любого типа данных. Для ссылочных типов значением по умолчанию является `null` ссылка. Для типов значений значение по умолчанию зависит от того, допускает ли тип значения значение null.  
  
> [!NOTE]
> Для типов значений, не допускающих `Nothing` значения NULL, в `null` Visual Basic C#отличается от в. В Visual Basic при задании переменной типа `Nothing`значения, не допускающего значения NULL, переменной присваивается значение по умолчанию для его объявленного типа. В C#при присвоении переменной типа `null`значения, не допускающего значения NULL, возникает ошибка времени компиляции.  
  
## <a name="remarks"></a>Примечания  
 `Nothing`представляет значение по умолчанию для типа данных. Значение по умолчанию зависит от того, имеет ли переменная тип значения или ссылочный тип.  
  
 Переменная *типа значения* напрямую содержит его значение. Типы значений включают все числовые типы данных `Boolean`, `Char` `Date`,,, все структуры и все перечисления. Переменная *ссылочного типа* хранит ссылку на экземпляр объекта в памяти. Ссылочные типы включают классы, массивы, делегаты и строки. Для получения дополнительной информации см. [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Если переменная имеет тип значения, поведение `Nothing` зависит от того, имеет ли переменная тип данных, допускающий значение null. Для представления типа значения, допускающего значение NULL `?` , добавьте модификатор к имени типа. Присваивание `Nothing` переменной, допускающей значение null, `null`присваивает значение. Дополнительные сведения и примеры см. в разделе [типы значений](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), допускающие значения NULL.  
  
 Если переменная имеет тип значения, не допускающий значения NULL, при присвоении `Nothing` ей присваивается значение по умолчанию для его объявленного типа. Если этот тип содержит члены переменных, все они устанавливаются в значения по умолчанию. Следующий пример иллюстрирует это для скалярных типов.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Если переменная имеет ссылочный тип, присвоение `Nothing` переменной задает `null` ссылку на тип переменной. Переменная, для `null` которой задана ссылка, не связана ни с одним объектом. В следующем примере это показано.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 При проверке наличия переменной `null`ссылки (или типа значения, допускающего значение null) не используйте `= Nothing` или. `<> Nothing` Всегда используйте `Is Nothing` или `IsNot Nothing`.  
  
 Для строк в Visual Basic пустая строка равна `Nothing`. Таким образом `"" = Nothing` , имеет значение true.  
  
 В следующем примере показаны сравнения, в `Is` которых используются операторы и. `IsNot`  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Если объявить переменную без использования `As` предложения и присвоить `Nothing`ей значение, `Object`переменная имеет тип. Примером этого является `Dim something = Nothing`. В этом случае возникает ошибка времени компиляции, когда `Option Strict` имеет значение on и `Option Infer` отключено.  
  
 При назначении `Nothing` объектной переменной она больше не ссылается ни на один экземпляр объекта. Если переменная ранее ссылалась на экземпляр, задание для `Nothing` него значения не завершает сам экземпляр. Экземпляр завершается, и связанные с ним память и системные ресурсы освобождаются, только если сборщик мусора (GC) обнаружит, что активные ссылки не остались.  
  
 `Nothing`отличается от <xref:System.DBNull> объекта, который представляет неинициализированный вариант или несуществующий столбец базы данных.  
  
## <a name="see-also"></a>См. также

- [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
- [Время существования объекта: Как создаются и уничтожаются объекты](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Время существования в Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Оператор Is](../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Типы значений, допускающие значение NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
