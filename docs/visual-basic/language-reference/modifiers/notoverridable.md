---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351449"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Указывает, что свойство или процедура не могут быть переопределены в производном классе.  
  
## <a name="remarks"></a>Примечания  
 Модификатор `NotOverridable` предотвращает переопределение свойства или метода в производном классе.  Модификатор [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) позволяет переопределять свойство или метод в производном классе. Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).  
  
 Если модификатор `Overridable` или `NotOverridable` не указан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса. Если свойство или метод переопределяет свойство или метод базового класса, значение по умолчанию — `Overridable`. в противном случае это `NotOverridable`.  
  
 Элемент, который не может быть переопределен, иногда называется *запечатанным* элементом.  
  
 `NotOverridable` можно использовать только в операторе объявления свойства или процедуры. Можно указать `NotOverridable` только для свойства или процедуры, которые переопределяют другое свойство или процедуру, то есть только в сочетании с `Overrides`.  
  
## <a name="combined-modifiers"></a>Комбинированные модификаторы  
 Для метода `Private` нельзя указать `Overridable` или `NotOverridable`.  
  
 В одном объявлении нельзя указать `NotOverridable` вместе с `MustOverride`, `Overridable`или `Shared`.  
  
## <a name="usage"></a>Использование  
 Модификатор `NotOverridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Затенение в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
