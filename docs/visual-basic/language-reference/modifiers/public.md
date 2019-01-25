---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 062d6276ab91705a4554da2afa8459a26453906f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703618"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Указывает, что один или несколько объявленных программных элементов не имеют ограничений доступа.  
  
## <a name="remarks"></a>Примечания  
 При публикации компонента или набора компонентов, таких как библиотеки классов, вам бы хотелось элементы программирования могут оказаться недоступными из любого кода, который взаимодействует со сборкой. Чтобы предоставить такой неограниченный доступ для элемента, его можно объявить с `Public`.  
  
 Общий доступ при обычном уровне для элемента программирования необходимо ограничить доступ к нему. Обратите внимание, что уровень доступа для элемента, объявленные в интерфейсе, модуля, класса или структуры по умолчанию используется `Public` Если иное не объявлено.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `Public` только на уровне модуля, интерфейса или пространства имен. Это означает, что контекст объявления для `Public` элемент должен быть исходный файл, пространство имен, интерфейс, модуля, класса или структуры и не может быть процедурой.  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Весь код, который можно получить доступ к модуля, класса или структуры можно получить доступ к его `Public` элементов.  
  
-   **Доступ по умолчанию.** Локальные переменные внутри процедуры по умолчанию общий доступ и невозможно использовать модификаторы доступа на них.  
  
-   **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Public` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
