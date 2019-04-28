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
ms.openlocfilehash: 97c651dbcc657fbab0706c9a959bd0031c0fe343
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778629"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Представляет значение по умолчанию любого типа данных. Для ссылочных типов, значение по умолчанию — `null` ссылки. Для типов значений значение по умолчанию зависит от того, является ли тип значения допускает значения NULL.  
  
> [!NOTE]
>  Для типов значений, не допускающие значения NULL `Nothing` в Visual Basic, отличается от `null` в C#. В Visual Basic, если задать для переменной типа значения, не допускающие значения NULL для `Nothing`, переменной присваивается значение по умолчанию для объявленного типа. В C#, если присвоить переменной типа значения, не допускающие значения NULL для `null`, возникает ошибка времени компиляции.  
  
## <a name="remarks"></a>Примечания  
 `Nothing` Представляет значение по умолчанию типа данных. Значение по умолчанию зависит от того, является ли переменная типа значения или ссылочного типа.  
  
 Переменная *тип значения* непосредственно содержит его значение. Типы значений относятся все типы числовых данных, `Boolean`, `Char`, `Date`, все структуры и всех перечислениях. Переменная *ссылочный тип* хранит ссылку на экземпляр объекта в памяти. Ссылочные типы включают классы, массивы, делегаты и строки. Для получения дополнительной информации см. [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Если переменная имеет значение типу, поведение `Nothing` зависит от того, является ли переменная типа данных допускает значения NULL. Чтобы представить тип, допускающий значение, добавьте `?` модификатор к имени типа. Назначение `Nothing` допускает значение NULL переменной присваивается значение `null`. Дополнительные сведения и примеры см. в разделе [значение](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Если переменная имеет тип значения, который не допускает значения NULL, назначение `Nothing` для его заменяет его на значение по умолчанию для объявленного типа. Если тип содержит члены переменной, они все готово к значениям по умолчанию. Следующий пример иллюстрирует это для скалярных типов.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Если переменная имеет ссылочный тип, назначение `Nothing` переменной заменяет его на `null` ссылку на тип переменной. Переменная, которой присваивается `null` ссылки не связан с любым объектом. В следующем примере это показано.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 При проверке ли ссылка (или допускает значения NULL тип значения), переменная является `null`, не используйте `= Nothing` или `<> Nothing`. Всегда используйте `Is Nothing` или `IsNot Nothing`.  
  
 Для строк в Visual Basic, равно пустой строке `Nothing`. Таким образом `"" = Nothing` имеет значение true.  
  
 В следующем примере показано сравнение с использованием `Is` и `IsNot` операторы.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Если переменная объявлена без использования `As` предложение и присвойте ему значение `Nothing`, переменную с типом `Object`. Примером этого является `Dim something = Nothing`. В этом случае возникает ошибка времени компиляции при `Option Strict` включен и `Option Infer` отключен.  
  
 При назначении `Nothing` объектной переменной, он больше не ссылается на экземпляр любого объекта. Если переменная содержалась ссылка на экземпляр, задав для него `Nothing` не завершает сам экземпляр. Экземпляр прекращается, и связанные с ней ресурсы памяти и системы освобождаются только в том случае, после сборщик мусора (GC) обнаруживает, что не осталось активных ссылок.  
  
 `Nothing` отличается от <xref:System.DBNull> объект, который представляет неинициализированный вариант или несуществующий столбец базы данных.  
  
## <a name="see-also"></a>См. также

- [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)
- [Время существования: Способ создания и уничтожения объектов](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Время существования в Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Оператор Is](../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Типы значений, допускающие значение NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
