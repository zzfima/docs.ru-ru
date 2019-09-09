---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 3e30267c8aa11ce97b3b3064ff0954378dab57af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959804"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Указывает, что один или несколько объявленных программных элементов доступны только в пределах сборки, содержащей их объявление.  
  
## <a name="remarks"></a>Примечания  
 Во многих случаях требуется, чтобы элементы программирования, такие как классы и структуры, использовались целой сборкой, а не только компонентом, который их объявляет. Однако может быть нежелательно, чтобы они были доступны коду за пределами сборки (например, если приложение является собственным). Если требуется ограничить доступ к элементу таким образом, его можно объявить с помощью `Friend` модификатора.  
  
 Код в других классах, структурах и модулях, компилируемых в одну и ту же сборку `Friend` , может обращаться ко всем элементам в этой сборке.  
  
 `Friend`доступ часто является предпочтительным уровнем для программных элементов приложения, а `Friend` также уровнем доступа по умолчанию для интерфейса, модуля, класса или структуры.  
  
 Можно использовать `Friend` только на уровне модуля, интерфейса или пространства имен. Таким образом, контекст объявления для `Friend` элемента должен быть исходным файлом, пространством имен, интерфейсом, модулем, классом или структурой. он не может быть процедурой.  

> [!NOTE]
> Можно также использовать модификатор доступа [Protected Friend](protected-friend.md) , который делает член класса доступным из этого класса, из производных классов и из той же сборки, в которой определен класс. Для ограничения доступа к члену из его класса и из производных классов в той же сборке используется модификатор [закрытого](private-protected.md) доступа.

 Сравнение `Friend` и других модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> Можно указать, что другая сборка является дружественной, что позволяет ей получить доступ ко всем типам и членам, помеченным как `Friend`. Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend-assemblies.md).  
  
## <a name="example"></a>Пример  
 Следующий класс использует `Friend` модификатор, чтобы разрешить другим элементам программирования в той же сборке доступ к определенным элементам.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Использование  
 `Friend` Модификатор можно использовать в следующих контекстах:  
  
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
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
