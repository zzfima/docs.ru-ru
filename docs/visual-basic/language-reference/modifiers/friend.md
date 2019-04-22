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
ms.openlocfilehash: 18681935d0380f9be3970fdb5d17ffb089152f59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819155"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Указывает, что один или несколько объявленных программных элементов доступны только внутри сборки, которая содержит их объявления.  
  
## <a name="remarks"></a>Примечания  
 Во многих случаях требуется программных элементов, таких как классы и структуры, используемые для всей сборки не только компонент, который объявляет их. Тем не менее вы не можете их доступными коду вне сборки (например, если приложение является собственным). Если вы хотите ограничить доступ к элементу таким образом, его можно объявить с помощью `Friend` модификатор.  
  
 Код в другие классы, структуры и модули, скомпилированные в тот же сборки можно получить доступ ко всем `Friend` элементы в этой сборке.  
  
 `Friend` доступ часто является предпочтительным уровнем для элементов программирования приложения, и `Friend` — по умолчанию доступ уровня интерфейса, модуля, класса или структуры.  
  
 Можно использовать `Friend` только на уровне модуля, интерфейса или пространства имен. Таким образом, что контекст объявления для `Friend` элемент должен быть исходным файлом, пространство имен, интерфейсом, модуля, класса или структуры; не может быть процедуры.  

> [!NOTE]
> Можно также использовать [Protected Friend](protected-friend.md) модификатор доступа, что делает член класса, доступный из этого класса из производных классов, а также из той же сборке, в котором определен класс. Чтобы ограничить доступ к элементу из внутри класса и из производных классов в той же сборке, используйте [Private Protected](private-protected.md) модификатор доступа.

 Сравнение `Friend` и другие модификаторы доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Можно указать, что другой сборки является дружественной сборки, что обеспечивает доступ ко всем типы и члены, помеченные как `Friend`. Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend-assemblies.md).  
  
## <a name="example"></a>Пример  
 Следующий класс использует `Friend` модификатор, чтобы разрешить другими элементами программирования в той же сборке, для доступа к определенным элементам.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Использование  
 Можно использовать `Friend` модификатор в следующих контекстах:  
  
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
