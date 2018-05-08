---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d7935cf691d961591ff5e3d2a290afb88de9165a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Указывает, что один или несколько элементов доступны только внутри контекста, включая из любых вложенных типов.  
  
## <a name="remarks"></a>Примечания  
 Если элемент программирования представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему. Максимальное ограничение добиться, позволяя модуля, класса или структуры, которые определяют его для доступа к нему. Чтобы ограничить доступ к элементу таким образом, можно объявить его с `Private`.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `Private` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Private` элемент должен быть модуля, класса или структуры и не может быть исходным файлом, пространства имен, интерфейса или процедуры.  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Весь код в контексте объявления можно получить доступ к его `Private` элементов. Это относится к коду вложенного типа, такие как вложенный класс или выражение присваивания в перечислении. Код вне контекста объявления можно получить доступ к его `Private` элементов.  
  
-   **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Private` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
