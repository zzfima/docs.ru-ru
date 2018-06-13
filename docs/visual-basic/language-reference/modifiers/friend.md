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
ms.openlocfilehash: d906fc8ada19f22059da44acbd76dd07dacd4801
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234593"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Указывает, что один или несколько объявленных программных элементов доступны только из внутри сборки, содержащей их объявления.  
  
## <a name="remarks"></a>Примечания  
 Во многих случаях требуется программных элементов, таких как классы и структуры, используемые всей сборке, не только компонентом, который объявляет их. Тем не менее могут не хотелось бы быть доступны для кода за пределами сборки (например, если приложение является собственным). Если вы хотите ограничить доступ к элементу таким образом, можно объявить его с помощью `Friend` модификатор.  
  
 Код в других классах, структурах и модули, скомпилированные с тем же сборке может получать доступ ко всем `Friend` элементы в этой сборке.  
  
 `Friend` доступ часто является предпочтительным уровнем для элементов программирования приложений, и `Friend` — доступ по умолчанию уровне интерфейса, модуля, класса или структуры.  
  
 Можно использовать `Friend` только на уровне модуля, интерфейсом или пространством имен. Таким образом, что контекст объявления для `Friend` элемент должен быть исходный файл, пространство имен, интерфейсом, модуля, класса или структуры; он не может быть процедурой.  

> [!NOTE]
> Можно также использовать [Protected Friend](protected-friend.md) модификатор доступа, что делает член класса, доступный из этого класса из производных классов и из той же сборки, в котором определен класс. Чтобы ограничить доступ к члену из внутри класса и из производных классов в той же сборке, используйте [защищенный закрытый](private-protected.md) модификатор доступа.

 Сравнение `Friend` и другие модификаторы доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Можно указать, что другая сборка является дружественной сборки, что позволяет получить доступ к все типы и члены, помеченные как `Friend`. Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
## <a name="example"></a>Пример  
 Следующий класс использует `Friend` модификатор, чтобы разрешить другими элементами программирования в одной и той же сборки для доступа к определенным элементам.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
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
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
 [Protected Private](./private-protected.md)   
 [Protected Friend](./protected-friend.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
