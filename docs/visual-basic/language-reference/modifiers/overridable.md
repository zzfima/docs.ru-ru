---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 4844bf7f3ecf23335715b950a96be15e54ebc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603773"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Указывает, что свойство или процедура могут быть переопределены одноименную свойство или процедура в производном классе.  
  
## <a name="remarks"></a>Примечания  
 `Overridable` Модификатор разрешает свойства или метода в классе для переопределения в производном классе. [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) модификатор не позволяет переопределять свойства или метода в производном классе.  Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).  
  
 Если `Overridable` или `NotOverridable` модификатор не указан, значение по умолчанию зависит от того, является ли метод или свойство переопределяет свойство базового класса или метода. Если метод или свойство переопределяет свойство базового класса или метода, значение по умолчанию — `Overridable`; в противном случае он является `NotOverridable`.  
  
 Можно скрывать или переопределить, чтобы переопределить наследуемый элемент, но существуют значительные различия между двумя способами. Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Элемент, который может быть переопределен, иногда называют *виртуальных* элемента. Если он может быть переопределен, но не должен быть, она иногда называется *конкретных* элемента.  
  
 `Overridable` можно использовать только в операторе объявления свойства или процедуры.  
  
## <a name="combined-modifiers"></a>Комбинированные модификаторы  
 Нельзя указать `Overridable` или `NotOverridable` для `Private` метод.  
  
 Нельзя указать `Overridable` вместе с `MustOverride`, `NotOverridable`, или `Shared` в одном объявлении.  
  
 Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
## <a name="usage"></a>Использование  
 Модификатор `Overridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
