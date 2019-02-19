---
title: Оператор << — справочник по C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219441"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор \<\<

Оператор сдвига влево `<<` сдвигает первый операнд влево на число битов, определяемое вторым операндом. Оператор `<<` поддерживает все целочисленные типы. Однако второй операнд должен иметь тип [int](../keywords/int.md) или тип, для которого существует [предварительно определенное неявное числовое преобразование](../keywords/implicit-numeric-conversions-table.md) в `int`.

Биты высокого порядка, выходящие за пределы диапазона типа результата, отменяются, а позиции пустого бита низкого порядка устанавливаются на ноль, как показано в следующем примере.

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a>Величина сдвига

Для выражения `x << count` фактическая величина сдвига зависит от типа `x` следующим образом.

- Если тип `x` — [int](../keywords/int.md) или [uint](../keywords/uint.md), величина сдвига определяется *пятью* младшими разрядами второго операнда. То есть величина сдвига вычисляется на основе `count & 0x1F` (или `count & 0b_1_1111`).

- Если тип `x` — [long](../keywords/long.md) или [ulong](../keywords/ulong.md), величина сдвига определяется *шестью* младшими разрядами второго операнда. То есть величина сдвига вычисляется на основе `count & 0x3F` (или `count & 0b_11_1111`).

В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a>Примечания

Операции сдвига никогда не приводят к переполнению и дают одинаковые результаты в [проверенных и непроверенных](../keywords/checked-and-unchecked.md) контекстах.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `<<`. Если определяемый пользователем тип `T` перегружает оператор `<<`, то в этом случае первый операнд должен иметь `T`, а второй операнд — тип `int`. При перегрузке оператора `<<` неявно перегружается и соответствующий [оператор присваивания сдвига влево](left-shift-assignment-operator.md) `<<=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы сдвига](~/_csharplang/spec/expressions.md#shift-operators) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор >> (справочник по C#)](right-shift-operator.md)
