---
title: Оператор =>. Справочник по C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 15c02e11610866f359e3e3a7e2751ded918154b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846261"
---
# <a name="-operator-c-reference"></a>Оператор => (справочник по C#)

Токен `=>` поддерживается в двух формах: в виде [лямбда-оператора](#lambda-operator) и в виде разделителя имени члена и реализации члена в [определении тела выражения](#expression-body-definition).

## <a name="lambda-operator"></a>Лямбда-оператор

В [лямбда-выражениях](../../programming-guide/statements-expressions-operators/lambda-expressions.md) лямбда-оператор `=>` используется для отделения входных параметров с левой стороны от тела лямбда-выражения с правой стороны.

В следующих примерах используется функция [LINQ](../../programming-guide/concepts/linq/index.md) с синтаксисом метода для демонстрации применения лямбда-выражений:

[!code-csharp-interactive[infer types of input variables](snippets/LambdaOperator.cs#InferredTypes)]

Входные параметры лямбда-выражений строго типизируются во время компиляции. Если компилятор может выводить типы входных параметров, как в предыдущем примере, вы можете опустить объявления типа. Если требуется указать тип входных параметров, это необходимо делать для каждого такого параметра, как показано в следующем примере:

[!code-csharp-interactive[specify types of input variables](snippets/LambdaOperator.cs#ExplicitTypes)]

В следующем примере показано, как определить лямбда-выражение без входных параметров:

[!code-csharp-interactive[without input variables](snippets/LambdaOperator.cs#WithoutInput)]

Дополнительные сведения см. в разделе [Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Определения тела выражения

Определение тела выражения имеет следующий общий синтаксис:

```csharp
member => expression;
```

где `expression` — любое допустимое выражение. Тип возвращаемого значения `expression` должен быть неявно преобразуемым в тип возвращаемого значения элемента. Если для элемента возвращается значение типа `void` или если элемент является конструктором, методом завершения или методом доступа свойства `set`, значение `expression` должно быть [*выражением оператора*](~/_csharplang/spec/statements.md#expression-statements). В этом случае оно может быть любого типа.

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

Начиная с версии C# 6, поддерживаются определения тела выражения для методов, операторов и доступных только для чтения свойств. Начиная с версии C# 7.0, поддерживаются определения тела выражения для конструкторов, методов завершения, методов доступа свойств и индексаторов.

Дополнительные сведения см. в разделе [Элементы, воплощающие выражение](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор `=>` перегрузить нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

См. сведения о лямбда-операторе в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
