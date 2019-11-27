---
title: Переопределения
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

- **Контекст объявления.** `Overrides` можно использовать только в операторе объявления свойства или процедуры.

- **Комбинированные модификаторы.** Нельзя указать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении. Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.

- **Сопоставление сигнатур.** Сигнатура этого объявления должна точно совпадать с *сигнатурой* свойства или процедуры, которую он переопределяет. Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.

  Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:

  - уровень доступа;

  - тип возвращаемого значения (если применимо).

- **Универсальные подписи.** Для универсальной процедуры сигнатура содержит число параметров типа. Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.

- **Дополнительное сопоставление.** Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:

  - Модификатор уровня доступа (например, [Public](../../../visual-basic/language-reference/modifiers/public.md))

  - Механизм передачи каждого параметра ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))

  - списки ограничений для каждого типа параметра универсальной процедуры.

- **Затенение и переопределение.** Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.

Модификатор `Overrides` можно использовать в следующих контекстах:

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>См. также

- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Затенение в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
