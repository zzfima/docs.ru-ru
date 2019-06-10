---
title: Справочник по C#. Оператор =
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 85182acb84ea79cb00a9edb315c3954f440305f4
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758363"
---
# <a name="-operator-c-reference"></a>Оператор = (Справочник по C#)

Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../../csharp/programming-guide/indexers/index.md), которые указаны в операнде слева. Результатом выражения присваивания является значение, назначенное расположенному слева операнду. Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.

Оператор присваивания имеет правую ассоциативность, то есть выражение формы:

```csharp
a = b = c
```

вычисляется как

```csharp
a = (b = c)
```

В следующем примере показано использование оператора присваивания для назначения значений локальной переменной, свойству и элементу индексатора:

[!code-csharp-interactive[assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>Ссылочный оператор присваивания

Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals). В следующем примере иллюстрируется использование ссылочного оператора присваивания:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

В случае ссылочного оператора присваивания тип левого и правого операнда должен быть одинаковым.

Дополнительные сведения см. в [примечании к предлагаемой функции](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательский тип не может перегружать оператор присваивания. Однако пользовательский тип может определять неявное преобразование в другой тип. Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа. Дополнительные сведения см. в статье [implicit (Справочник по C#)](../keywords/implicit.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Простое присваивание](~/_csharplang/spec/expressions.md#simple-assignment) в статье о [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Ключевое слово ref](../keywords/ref.md)
