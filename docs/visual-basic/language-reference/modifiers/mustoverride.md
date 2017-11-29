---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2f7bdba4b01bd307e0c52802509669f772b5eb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Указывает, что свойство или процедура не реализована в этом классе и должен быть переопределен в производном классе, прежде чем можно будет использовать.  
  
## <a name="remarks"></a>Примечания  
 `MustOverride` можно использовать только в операторе объявления свойства или процедуры. Свойство или процедура, которая указывает `MustOverride` должен быть членом класса, и класс должен быть помечен [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Правила  
  
-   **Неполные объявление.** При указании `MustOverride`, можно не указывать любые дополнительные строки кода для свойства или процедуры, не даже `End Function`, `End Property`, или `End Sub` инструкции.  
  
-   **Комбинированные модификаторы.** Нельзя указать `MustOverride` вместе с `NotOverridable`, `Overridable`, или `Shared` в одном объявлении.  
  
-   **Сокрытие и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Альтернативные условия.** Иногда называется элемент, который не может использоваться только в переопределение *чистые виртуальные* элемента.  
  
 Модификатор `MustOverride` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
