---
title: Оператор % (Справочник по C#)
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: 9cd2f7ad3856feb34667686979c942ecb21887c2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45645922"
---
# <a name="-operator-c-reference"></a>Оператор % (Справочник по C#)

Оператор остатка `%` вычисляет остаток от деления первого операнда на второй. Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `%`. Когда `%` перегружается, [оператор присваивания остатка](remainder-assignment-operator.md) `%=` также неявно перегружается.

Все числовые типы поддерживают оператор остатка.

## <a name="integer-remainder"></a>Целочисленный остаток
  
Для целочисленных операндов результатом `a % b` является значение, произведенное `a - (a / b) * b`. Знак ненулевого остатка такой же, как и у первого операнда, как показано в следующем примере.

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a>Остаток с плавающей запятой

Для операндов типа [float](../keywords/float.md) и [double](../keywords/double.md) результатом `x % y` для конечных `x` и `y` будет значение `z`, так что:

- знак `z`, если отлично от нуля, совпадает со знаком `x`;
- абсолютное значение `z` является значением, произведенным `|x| - n * |y|`, где `n` — это наибольшее возможное целое число, которое меньше или равно `|x| / |y|`, а `|x|` и `|y|` являются абсолютными значениями `x` и `y` соответственно.

Сведения о поведение оператора `%` в случае неконечных операндов см. в разделе [Оператор остатка](/dotnet/csharp/language-reference/language-specification/expressions#remainder-operator) в [спецификации языка C#](/dotnet/csharp/language-reference/language-specification/index).

> [!NOTE]
> Этот метод вычисления остатка аналогичен тому, который использовался для целочисленных операндов, но отличается от IEEE 754. Если вам нужна операция остатка, которая соответствует IEEE 754, используйте метод <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

В следующем примере показано поведение оператора остатка для операндов `float` и `double`.

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

Обратите внимание на ошибки округления, которые могут быть связаны с типами с плавающей запятой.

Для [десятичных](../keywords/decimal.md) операндов оператор остатка `%` эквивалентен [оператору остатка](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) типа <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
