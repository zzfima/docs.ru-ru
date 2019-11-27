---
title: Overridable
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
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351391"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Указывает, что свойство или процедура может быть переопределена свойством или процедурой с идентичным именем в производном классе.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `Overridable` позволяет переопределить свойство или метод в классе в производном классе. Модификатор [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) предотвращает переопределение свойства или метода в производном классе.  Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).  
  
 Если модификатор `Overridable` или `NotOverridable` не указан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса. Если свойство или метод переопределяет свойство или метод базового класса, значение по умолчанию — `Overridable`. в противном случае это `NotOverridable`.  
  
 Можно выполнить затенение или переопределение, чтобы переопределить наследуемый элемент, но существуют значительные различия между этими двумя подходами. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Элемент, который можно переопределить, иногда называется *виртуальным* элементом. Если он может быть переопределен, но не обязательно должен быть, он иногда также называется *конкретным* элементом.  
  
 `Overridable` можно использовать только в операторе объявления свойства или процедуры.  
  
## <a name="combined-modifiers"></a>Комбинированные модификаторы  
 Для метода `Private` нельзя указать `Overridable` или `NotOverridable`.  
  
 В одном объявлении нельзя указать `Overridable` вместе с `MustOverride`, `NotOverridable`или `Shared`.  
  
 Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
## <a name="usage"></a>Использование  
 Модификатор `Overridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также:

- [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Затенение в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
