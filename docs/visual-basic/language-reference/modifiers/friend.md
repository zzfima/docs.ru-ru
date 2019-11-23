---
title: Friend
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
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351564"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.  
  
## <a name="remarks"></a>Заметки  
 In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them. However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary). If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.  
  
 Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.  
  
 `Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.  
  
 You can use `Friend` only at the module, interface, or namespace level. Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.  

> [!NOTE]
> You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined. To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.

 For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`. Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend.md).

## <a name="example"></a>Пример  
 The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Использование  
 You can use the `Friend` modifier in these contexts:  
  
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
- [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
