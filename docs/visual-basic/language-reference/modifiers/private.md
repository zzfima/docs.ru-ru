---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819481"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Указывает, что один или несколько объявленных программных элементов доступны только из их объявление контекста, в том числе и из всех вложенных типов.  
  
## <a name="remarks"></a>Примечания  
 Если программный элемент представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему. Максимальное ограничение добиться, разрешив только модуля, класса или структуры, определяющего его для доступа к нему. Чтобы ограничить доступ к элементу таким образом, его можно объявить с `Private`.  

> [!NOTE]
> Можно также использовать [Private Protected](private-protected.md) модификатор доступа, что делает член доступен из внутри этого класса и из производных классов, расположенных в его соответствующая сборка.

## <a name="rules"></a>Правила  

-   **Контекст объявления.** `Private` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Private` элемент должен быть модуля, класса или структуры и не может быть исходный файл, пространство имен, интерфейса или процедуры.  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Весь код в контексте объявления можно получить доступ к его `Private` элементов. Это включает в себя код вложенного типа, таких как вложенный класс или выражения присваивания в перечисление. Код вне контекста объявления можно получить доступ к его `Private` элементов.  
  
-   **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)[Access levels в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
