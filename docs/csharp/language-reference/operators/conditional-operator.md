---
title: '?: Справочник по C#. Оператор'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: c3c875cf5b8d1b5e69cd76cb0ee4df0a989a35a0
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202903"
---
# <a name="-operator-c-reference"></a>?: Оператор (ссылка C#)

Условный оператор `?:`, известный как тернарный условный оператор, вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений, в зависимости от того, чему равно значение логического выражения: `true` или `false`. Начиная с C# 7.2, [условное выражение REF](#conditional-ref-expression) возвращает ссылку на результат одного из двух выражений.

Для условного оператора используется следующий синтаксис:

```csharp
condition ? consequence : alternative
```

Выражение `condition` должно принимать значение `true` или `false`. Если `condition` принимает значение `true`, вычисляется выражение `consequence`, а результат становится результатом операции. Если `condition` принимает значение `false`, вычисляется выражение `alternative`, а результат становится результатом операции. Вычисляется только выражение `consequence` или `alternative`.

Параметры `consequence` и `alternative` должны быть одинакового типа, или должно существовать неявное преобразование из одного типа в другой.

Условный оператор имеет правую ассоциативность, то есть выражение формы.

```csharp
a ? b : c ? d : e
```

вычисляется как

```csharp
a ? b : (c ? d : e)
```

В следующем примере иллюстрируется использование условного оператора:

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Условное выражение REF

Начиная с C# 7.2, условное выражение REF можно использовать для того, чтобы вернуть ссылку на результат одного из двух выражений. Можно назначить эту ссылку [ссылочной локальной переменной](../keywords/ref.md#ref-locals) или [ссылочной локальной переменной только для чтения](../keywords/ref.md#ref-readonly-locals) или же использовать ее как [возвращаемое ссылочное значение](../keywords/ref.md#reference-return-values) или как [`ref` параметр метода](../keywords/ref.md#passing-an-argument-by-reference).

Для условного выражения REF используется следующий синтаксис:

```csharp
condition ? ref consequence : ref alternative
```

Подобно исходному условному оператору, условное выражение REF вычисляет только одно из двух выражений: `consequence` или `alternative`.

Для условного выражения REF тип `consequence` и `alternative` должны совпадать.

В следующем примере иллюстрируется использование условного выражения REF:

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

Дополнительные сведения см. в [примечании к предлагаемой функции](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).

## <a name="conditional-operator-and-an-ifelse-statement"></a>Условный оператор и оператор `if..else`

Если использовать условный оператор с оператором [if-else](../keywords/if-else.md), может получиться более лаконичный код в случаях, когда необходимо условно вычислить значение. В следующем примере иллюстрируются два вида классификации целого числа как положительного или отрицательного:

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Условный оператор не может быть перегружен.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Условный оператор](~/_csharplang/spec/expressions.md#conditional-operator) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [if-else (Справочник по C#)](../keywords/if-else.md)
- [Операторы ?. и ?[]](null-conditional-operators.md)
- [?? Оператор](null-coalescing-operator.md)
- [Ключевое слово ref](../keywords/ref.md)
