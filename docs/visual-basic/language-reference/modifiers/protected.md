---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 5f279ed0a33840bb1f2321c17a1ffba412837c07
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Модификатор доступа члена, который указывает, один или несколько объявленных программных элементов доступны только внутри собственного класса или из производного класса.  
  
## <a name="remarks"></a>Примечания  
 Иногда программный элемент объявлен в классе содержит конфиденциальные данные или ограниченный код, и вы хотите ограничить доступ к элементу. Однако если класс является наследуемым и предполагается в иерархии производных классов, возможно, необходимые для этих производных классов для доступа к данным или коду. В этом случае требуется, чтобы элемент был доступен как из базового класса, так и из всех производных классов. Чтобы ограничить доступ к элементу таким образом, можно объявить его с `Protected`.  

> [!NOTE]
> `Protected` Модификатор доступа может сочетаться с двух других модификаторов:
> - [Protected Friend](protected-friend.md) модификатор делает член класса, доступный из этого класса из производных классов и из той же сборки, в котором определен класс. 
> - [Защищенный закрытый](private-protected.md) модификатор делает член класса доступны с помощью производных типов, но только в пределах содержащего сборки.
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `Protected` только на уровне класса. Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры.  

## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Весь код в классе можно получить доступ к его элементам. Код в любой класс, производный от базового класса можно получить доступ ко всем `Protected` элементы базового класса. Это справедливо для всех поколений наследования. Это означает, что класс может получить доступ к `Protected` элементы базового класса базового класса и т. д.  
  
     Защищенный доступ не является надмножеством или подмножеством дружественный доступ.  
  
-   **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Protected` можно использовать в следующих контекстах:  
  
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
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
 [Protected Private](private-protected.md)   
 [Protected Friend](protected-friend.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
