---
title: Оператор ^ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 8cdfbec917608211e19c39eb37bd12dbc7c4d33f
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592214"
---
# <a name="-operator-visual-basic"></a>Оператор ^ (Visual Basic)

Порождает число в степень другого числа.

## <a name="syntax"></a>Синтаксис

```vb
number ^ exponent
```

## <a name="parts"></a>Части

`number`\
Обязательный. Произвольное числовое выражение.

`exponent`\
Обязательный. Произвольное числовое выражение.

## <a name="result"></a>Результат

Результат `number`, возведенный в степень `exponent`, всегда как значение `Double`.

## <a name="supported-types"></a>Поддерживаемые типы

`Double`. Операнды любого другого типа преобразуются в `Double`.

## <a name="remarks"></a>Примечания

Visual Basic всегда выполняет возведение в степень в [типе данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).

Значение `exponent` может быть дробным, отрицательным или обоими.

Если в одном выражении выполняется несколько возможного возведения в степень, то оператор `^` вычисляется так, как он встретился слева направо.

> [!NOTE]
> Оператор `^` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Пример

В следующем примере оператор `^` используется для возведения числа в степень экспоненты. Результатом является первый операнд, возведенный в степень второго.

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

В предыдущем примере получены следующие результаты.

значение `exp1` равно 4 (2 в квадрате).

для `exp2` задано значение 19683 (3 куб, затем это значение Cube).

`exp3` имеет значение-125 (-5 кубd).

для `exp4` устанавливается значение 625 (от-5 до четвертого).

значение `exp5` равно 2 (кубический корень из 8).

для `exp6` установлено значение 0,5 (1,0, деленное на кубический корень из 8).

Обратите внимание на важность круглых скобок в выражениях из предыдущего примера. Из-за *приоритета операторов*Visual Basic обычно выполняет оператор `^` перед любыми другими, даже унарным оператором `–`. Если `exp4` и `exp6` были вычислены без скобок, они могли бы получить следующие результаты:

`exp4 = -5 ^ 4` будет вычисляться как – (от 5 до четвертой мощности), что приведет к появлению-625.

`exp6 = 8 ^ -1.0 / 3.0` будет рассчитываться как (от 8 до – 1 или 0,125), деленное на 3,0, что приведет к 0.041666666666666666666666666666667.

## <a name="see-also"></a>См. также

- [Оператор ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
