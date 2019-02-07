---
title: Оператор => — справочник по C#
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 0cded9d23d67e6afc8b01d6711e42759b4b51fab
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275864"
---
# <a name="-operator-c-reference"></a>Оператор => (справочник по C#)

Токен `=>` поддерживается в двух формах: в виде лямбда-оператора и в виде разделителя имени члена и реализации члена в определении тела выражения.

## <a name="lambda-operator"></a>Лямбда-оператор

В [лямбда-выражениях](../../programming-guide/statements-expressions-operators/lambda-expressions.md) лямбда-оператор `=>` используется для отделения входных переменных с левой стороны от тела лямбда-выражения с правой стороны.

В следующих примерах используется функция [LINQ](../../programming-guide/concepts/linq/index.md) с синтаксисом метода для демонстрации применения лямбда-выражений:

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

Входные переменные лямбда-выражений строго типизируются во время компиляции. Если компилятор может вывести типы входных переменных, как в предыдущем примере, вы можете опустить объявления типа. Если требуется указать тип входных переменных, это необходимо делать для каждой переменной, как демонстрируется в следующем примере:

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

В следующем примере показано, как определить лямбда-выражение без входных переменных:

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

Дополнительные сведения см. в разделе [Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Определения тела выражения

Определение тела выражения имеет следующий общий синтаксис:

```csharp
member => expression;
```

здесь *expression* является допустимым выражением. Обратите внимание, что *выражение* может быть *выражением оператора* только в том случае, если для элемента возвращается значение типа `void`, либо если элемент является конструктором, методом завершения или методом доступа свойства `set`.

В следующем примере приводится определение тела выражения для метода `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Это сокращенная версия следующего определения метода:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

Определения тела выражения для методов и доступных только для чтения свойств поддерживаются начиная с версии C# 6. Определения тела выражения для конструкторов, методов завершения, методов доступа свойств и индексаторов поддерживаются начиная с версии C# 7.0.

Дополнительные сведения см. в разделе [Элементы, воплощающие выражение](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор `=>` перегрузить нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Элементы, воплощающие выражение](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)