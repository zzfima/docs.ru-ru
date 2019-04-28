---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: 0ddd7d0d2a57afc02aa7483ba5e83b65c48af534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920761"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Указывает, что свойство или процедура в этом классе не реализован и должен быть переопределен в производном классе, прежде чем можно будет использовать.  
  
## <a name="remarks"></a>Примечания  
 `MustOverride` можно использовать только в операторе объявления свойства или процедуры. Свойство или процедуру, которая указывает `MustOverride` должен быть членом класса, и класс должен быть помечен [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Правила  
  
- **Неполное объявление.** При указании `MustOverride`, не нужно вводить любые дополнительные строки кода для свойства или процедуры, не даже `End Function`, `End Property`, или `End Sub` инструкции.  
  
- **Комбинированные модификаторы.** Нельзя указать `MustOverride` вместе с `NotOverridable`, `Overridable`, или `Shared` в одном объявлении.  
  
- **Сокрытие и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Альтернативные условия.** Элемент, который не может использоваться только в переопределении иногда называют *чисто виртуальный* элемент.  
  
 Модификатор `MustOverride` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
