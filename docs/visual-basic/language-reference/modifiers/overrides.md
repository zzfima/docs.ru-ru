---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 81118b9e97f320bffdbb58e5e1a2859052c4cee5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602534"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)
Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `Overrides` можно использовать только в операторе объявления свойства или процедуры.  
  
-   **Комбинированные модификаторы.** Невозможно указать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении. Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
-   **Соответствие сигнатур.** Подпись этого объявления должна точно соответствовать *подписи* свойства или процедуры, которую она переопределяет. Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.  
  
     Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:  
  
    -   уровень доступа;  
  
    -   тип возвращаемого значения (если применимо).  
  
-   **Универсальные сигнатуры.** Для универсальной процедуры сигнатура содержит число параметров типа. Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.  
  
-   **Дополнительные соответствия.** Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:  
  
    -   Модификатор уровня доступа (такие как [открытый](../../../visual-basic/language-reference/modifiers/public.md))  
  
    -   Передачи каждого параметра ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))  
  
    -   списки ограничений для каждого типа параметра универсальной процедуры.  
  
-   **Сокрытие и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.  
  
 Модификатор `Overrides` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
