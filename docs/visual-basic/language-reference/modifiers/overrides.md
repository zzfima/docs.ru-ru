---
title: Overrides
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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351389"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.

## <a name="rules"></a>Правила

- **Declaration Context.** You can use `Overrides` only in a property or procedure declaration statement.

- **Combined Modifiers.** You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration. Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.

- **Matching Signatures.** The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides. Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.

  Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:

  - уровень доступа;

  - тип возвращаемого значения (если применимо).

- **Generic Signatures.** Для универсальной процедуры сигнатура содержит число параметров типа. Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.

- **Additional Matching.** Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:

  - Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))

  - Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))

  - списки ограничений для каждого типа параметра универсальной процедуры.

- **Shadowing and Overriding.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.

Модификатор `Overrides` можно использовать в следующих контекстах:

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>См. также

- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
