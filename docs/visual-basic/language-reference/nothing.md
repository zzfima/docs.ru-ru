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
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603994"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Представляет значение по умолчанию для любого типа данных. Для ссылочных типов значение по умолчанию — `null` ссылки. Для типов значений значение по умолчанию зависит от того, является ли тип значения допускает значения NULL.  
  
> [!NOTE]
>  Для типов значений, не допускающим `Nothing` в Visual Basic, отличается от `null` в C#. В Visual Basic, если задать для переменной типа значения, не допускающим значения `Nothing`, переменной присваивается значение по умолчанию для объявленного типа. В C#, если присвоить переменной типа значения, не допускающим значения `null`, то возникает ошибка времени компиляции.  
  
## <a name="remarks"></a>Примечания  
 `Nothing` Представляет значение по умолчанию для типа данных. Значение по умолчанию зависит от того, является ли переменная типа значения или ссылочного типа.  
  
 Переменная *тип значения* непосредственно содержащего его значение. Значение типам относятся все числовые типы данных, `Boolean`, `Char`, `Date`, все структуры и всех перечислениях. Переменная *ссылочному типу* хранит ссылку на экземпляр объекта в памяти. Ссылочные типы включают классы, массивы, делегаты и строк. Для получения дополнительной информации см. [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Если переменная имеет значение тип, поведение `Nothing` зависит от того, является ли переменная имеет тип данных допускает значения NULL. Чтобы представить тип, допускающий значение, добавьте `?` модификатор к имени типа. Назначение `Nothing` для переменной со значением NULL задает значение, равное `null`. Дополнительные сведения и примеры см. в разделе [значение](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Если переменная имеет тип значения, который не допускает значения NULL, назначение `Nothing` чтобы он устанавливает его значение по умолчанию для объявленного типа. Если тип содержит члены переменной, они задаются все значения по умолчанию. Следующий пример иллюстрирует это для скалярных типов.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 Если переменная имеет ссылочный тип, назначение `Nothing` переменной задается значение `null` ссылку на тип переменной. Переменная, которой присваивается `null` ссылка не связан с любым объектом. В следующем примере это показано.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 При проверке ссылки (или введите значение NULL), переменная `null`, не используйте `= Nothing` или `<> Nothing`. Всегда используйте `Is Nothing` или `IsNot Nothing`.  
  
 Для строк в Visual Basic, равняется пустая строка `Nothing`. Таким образом `"" = Nothing` имеет значение true.  
  
 В следующем примере показано сравнение с использованием `Is` и `IsNot` операторы.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 Если переменная объявлена без использования `As` предложения и присвойте ему значение `Nothing`, переменная имеет тип `Object`. Примером этого является `Dim something = Nothing`. В этом случае возникает ошибка времени компиляции при `Option Strict` включен и `Option Infer` отключен.  
  
 При назначении `Nothing` переменной объекта, он больше не ссылается на любой экземпляр объекта. Если переменная содержалась ссылка на экземпляр, задание `Nothing` не прекращает самого экземпляра. Выполнение экземпляра завершается и освобождаются ресурсы памяти и системы, связанные с ним, только после того, что сборщик мусора (GC) обнаружит, что не осталось активных ссылок.  
  
 `Nothing` отличается от <xref:System.DBNull> объект, который представляет неинициализированный вариант или несуществующий столбец базы данных.  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Время существования. Создание и уничтожение объектов](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Время существования в Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Оператор Is](../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Типы значений, допускающие значение NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
