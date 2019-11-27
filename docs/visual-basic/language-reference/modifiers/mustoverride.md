---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351482"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Указывает, что свойство или процедура не реализованы в этом классе и должны быть переопределены в производном классе, прежде чем его можно будет использовать.  
  
## <a name="remarks"></a>Заметки  
 `MustOverride` можно использовать только в операторе объявления свойства или процедуры. Свойство или процедура, указывающая `MustOverride` должен быть членом класса, а класс должен быть помечен как [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Правила  
  
- **Неполное объявление.** При указании `MustOverride`не предоставляются дополнительные строки кода для свойства или процедуры, а не инструкции `End Function`, `End Property`или `End Sub`.  
  
- **Комбинированные модификаторы.** В одном объявлении нельзя указать `MustOverride` вместе с `NotOverridable`, `Overridable`или `Shared`.  
  
- **Затенение и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Альтернативные условия.** Элемент, который нельзя использовать, за исключением переопределения, иногда называют *чисто виртуальным* элементом.  
  
 Модификатор `MustOverride` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Затенение в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
