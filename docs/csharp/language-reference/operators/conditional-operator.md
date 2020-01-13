---
title: Оператор ?:. Справочник по C#
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 60156585dd21d5d2f9c9f3916452bb8574ddd4e4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712732"
---
# <a name="-operator-c-reference"></a>Оператор ?: (справочник по C#)

Условный оператор `?:`, известный как тернарный условный оператор, вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений в зависимости от того, чему равно значение логического выражения: `true` или `false`. Начиная с C# 7.2, [условное выражение REF](#conditional-ref-expression) возвращает ссылку на результат одного из двух выражений.

Для условного оператора используется следующий синтаксис:

```csharp
condition ? consequent : alternative
```

Выражение `condition` должно принимать значение `true` или `false`. Если `condition` принимает значение `true`, вычисляется выражение `consequent`, а результат становится результатом операции. Если `condition` принимает значение `false`, вычисляется выражение `alternative`, а результат становится результатом операции. Вычисляется только выражение `consequent` или `alternative`.

Параметры `consequent` и `alternative` должны быть одинакового типа, или должно существовать неявное преобразование из одного типа в другой.

Условный оператор имеет правую ассоциативность, то есть выражение формы.

```csharp
a ? b : c ? d : e
```

вычисляется как

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> Вы можете использовать следующий мнемонический прием, чтобы запомнить, как оценивается условный оператор:
>
> ```text
> is this condition true ? yes : no
> ```

В следующем примере иллюстрируется использование условного оператора:

[!code-csharp-interactive[non ref conditional](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Условное выражение REF

Начиная с C# 7.2, условное выражение REF можно использовать для того, чтобы вернуть ссылку на результат одного из двух выражений. Можно назначить эту ссылку [ссылочной локальной переменной](../keywords/ref.md#ref-locals) или [ссылочной локальной переменной только для чтения](../keywords/ref.md#ref-readonly-locals) или же использовать ее как [возвращаемое ссылочное значение](../keywords/ref.md#reference-return-values) или как [`ref` параметр метода](../keywords/ref.md#passing-an-argument-by-reference).

Для условного выражения REF используется следующий синтаксис:

```csharp
condition ? ref consequent : ref alternative
```

Подобно исходному условному оператору, условное выражение REF вычисляет только одно из двух выражений: `consequent` или `alternative`.

Для условного выражения REF тип `consequent` и `alternative` должны совпадать.

В следующем примере иллюстрируется использование условного выражения REF:

[!code-csharp-interactive[conditional ref](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Условный оператор и оператор `if..else`

Если использовать условный оператор с оператором [if-else](../keywords/if-else.md), может получиться более лаконичный код в случаях, когда необходимо условно вычислить значение. В следующем примере иллюстрируются два вида классификации целого числа как положительного или отрицательного:

[!code-csharp[conditional and if-else](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип не может перегружать условный оператор.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Условный оператор](~/_csharplang/spec/expressions.md#conditional-operator) статьи [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).

См. сведения об условном ссылочном выражении в [примечании к функциям](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [if-else (Справочник по C#)](../keywords/if-else.md)
- [Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Операторы ?? и ??=](null-coalescing-operator.md)
- [Ключевое слово ref](../keywords/ref.md)
