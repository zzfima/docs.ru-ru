---
title: Оператор = — справочник по C#
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: f30b48fc6bd1e896658a7234a58409ea9a0f5e6f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69601953"
---
# <a name="-operator-c-reference"></a>Оператор = (справочник по C#)

Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../programming-guide/indexers/index.md), которые указаны в операнде слева. Результатом выражения присваивания является значение, назначенное расположенному слева операнду. Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.

Оператор присваивания имеет правую ассоциативность, то есть выражение формы:

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

В случае ссылочного оператора присваивания тип левого и правого операндов должен быть одинаковым.

Дополнительные сведения см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

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

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательский тип не может перегружать оператор присваивания. Однако пользовательский тип может определять неявное преобразование в другой тип. Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа. Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Подробные сведения см. в разделе [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) (Операторы присваивания) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Ключевое слово ref](../keywords/ref.md)
