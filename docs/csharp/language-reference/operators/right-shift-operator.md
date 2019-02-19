---
title: '>> Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219728"
---
# <a name="-operator-c-reference"></a>Оператор >> (справочник по C#)

Оператор сдвига вправо `>>` сдвигает первый операнд вправо на число битов, определяемое вторым операндом. Оператор `>>` поддерживает все целочисленные типы. Однако второй операнд должен иметь тип [int](../keywords/int.md) или тип, для которого существует [предварительно определенное неявное числовое преобразование](../keywords/implicit-numeric-conversions-table.md) в `int`.

Операция сдвига вправо отменяет биты низкого порядка. Позиции пустых битов высокого порядка задаются с учетом типа первого операнда следующим образом.

- Если первый операнд имеет тип [int](../keywords/int.md) или [long](../keywords/long.md), оператор сдвига вправо выполняет **арифметический** сдвиг. Значение старшего значимого бита (знаковый бит) первого операнда распространяется на пустые битовые позиции высокого разряда. То есть пустые битовые позиции высокого порядка разряда устанавливаются на ноль, если первый операнд неотрицательный, и устанавливаются на единицу, если он отрицательный.

- Если первый операнд имеет тип [uint](../keywords/uint.md) или [ulong](../keywords/ulong.md), оператор сдвига вправо выполняет **логический** сдвиг. Пустым битовым позициям высокого порядка всегда присваивается нулевое значение.

В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a>Величина сдвига

Для выражения `x >> count` фактическая величина сдвига зависит от типа `x` следующим образом.

- Если тип `x` — [int](../keywords/int.md) или [uint](../keywords/uint.md), величина сдвига определяется *пятью* младшими разрядами второго операнда. То есть величина сдвига вычисляется на основе `count & 0x1F` (или `count & 0b_1_1111`).

- Если тип `x` — [long](../keywords/long.md) или [ulong](../keywords/ulong.md), величина сдвига определяется *шестью* младшими разрядами второго операнда. То есть величина сдвига вычисляется на основе `count & 0x3F` (или `count & 0b_11_1111`).

В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a>Примечания

Операции сдвига никогда не приводят к переполнению и дают одинаковые результаты в [проверенных и непроверенных](../keywords/checked-and-unchecked.md) контекстах.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `>>`. Если определяемый пользователем тип `T` перегружает оператор `>>`, то в этом случае первый операнд должен иметь `T`, а второй операнд — тип `int`. При перегрузке оператора `>>` неявно перегружается и соответствующий [оператор присваивания сдвига вправо](right-shift-assignment-operator.md) `>>=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы сдвига](~/_csharplang/spec/expressions.md#shift-operators) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Справочник по C#. Оператор <<](left-shift-operator.md)