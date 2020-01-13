---
title: Справочник по C#. Арифметические операторы
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 19f74e6835ae555a3a38aa6ca8679948c7f290dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712758"
---
# <a name="assignment-operators-c-reference"></a>Справочник по C#. Операторы присваивания

Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../programming-guide/indexers/index.md), которые указаны в операнде слева. Результатом выражения присваивания является значение, назначенное расположенному слева операнду. Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.

Оператор присваивания `=` имеет правую ассоциативность, то есть выражение формы:

```csharp
a = b = c
```

вычисляется как

```csharp
a = (b = c)
```

В следующем примере показано использование оператора присваивания с локальной переменной, свойством и элементом индексатора в качестве левого операнда:

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a>Ссылочный оператор присваивания

Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals). В следующем примере иллюстрируется использование ссылочного оператора присваивания:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

При использовании ссылочного оператора присваивания тип левого и правого операндов должен быть одинаковым.

## <a name="compound-assignment"></a>Составное присваивание

Для бинарного оператора `op` выражение составного присваивания в форме

```csharp
x op= y
```

эквивалентно

```csharp
x = x op y
```

за исключением того, что `x` вычисляется только один раз.

Составное присваивание поддерживается [арифметическими](arithmetic-operators.md#compound-assignment), [логическими](boolean-logical-operators.md#compound-assignment), [побитовыми логическими операторами и операторами смещения](bitwise-and-shift-operators.md#compound-assignment).

## <a name="null-coalescing-assignment"></a>Присваивание объединения со значением NULL

Начиная с C# 8.0 вы можете использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`. Дополнительные сведения см. в статье [Операторы ?? и ??=](null-coalescing-operator.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательский тип не может [перегружать](operator-overloading.md) оператор присваивания. Однако пользовательский тип может определять неявное преобразование в другой тип. Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа. Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).

Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом. Но если пользовательский тип перегружает бинарный оператор `op`, существующий оператор `op=` также будет неявно перегружен.

## <a name="c-language-specification"></a>Спецификация языка C#

Подробные сведения см. в разделе [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) (Операторы присваивания) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

См. сведения о ссылочном операторе присваивания `= ref` в [примечании к функциям](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Ключевое слово ref](../keywords/ref.md)
