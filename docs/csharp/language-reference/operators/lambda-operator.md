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
ms.openlocfilehash: 4c075cedb3cf479f53409f3b0acf4463fc3d7a03
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758213"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0b81d-102">Оператор => (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0b81d-102">=> operator (C# Reference)</span></span>

<span data-ttu-id="0b81d-103">Токен `=>` поддерживается в двух формах: в виде лямбда-оператора и в виде разделителя имени члена и реализации члена в определении тела выражения.</span><span class="sxs-lookup"><span data-stu-id="0b81d-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="0b81d-104">Лямбда-оператор</span><span class="sxs-lookup"><span data-stu-id="0b81d-104">Lambda operator</span></span>

<span data-ttu-id="0b81d-105">В [лямбда-выражениях](../../programming-guide/statements-expressions-operators/lambda-expressions.md) лямбда-оператор `=>` используется для отделения входных переменных с левой стороны от тела лямбда-выражения с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="0b81d-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="0b81d-106">В следующих примерах используется функция [LINQ](../../programming-guide/concepts/linq/index.md) с синтаксисом метода для демонстрации применения лямбда-выражений:</span><span class="sxs-lookup"><span data-stu-id="0b81d-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="0b81d-107">Входные переменные лямбда-выражений строго типизируются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0b81d-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="0b81d-108">Если компилятор может вывести типы входных переменных, как в предыдущем примере, вы можете опустить объявления типа.</span><span class="sxs-lookup"><span data-stu-id="0b81d-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="0b81d-109">Если требуется указать тип входных переменных, это необходимо делать для каждой переменной, как демонстрируется в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0b81d-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="0b81d-110">В следующем примере показано, как определить лямбда-выражение без входных переменных:</span><span class="sxs-lookup"><span data-stu-id="0b81d-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="0b81d-111">Дополнительные сведения см. в разделе [Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0b81d-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="0b81d-112">Определения тела выражения</span><span class="sxs-lookup"><span data-stu-id="0b81d-112">Expression body definition</span></span>

<span data-ttu-id="0b81d-113">Определение тела выражения имеет следующий общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0b81d-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="0b81d-114">здесь *expression* является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="0b81d-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="0b81d-115">Обратите внимание, что *выражение* может быть *выражением оператора* только в том случае, если для элемента возвращается значение типа `void`, либо если элемент является конструктором, методом завершения или методом доступа свойства `set`.</span><span class="sxs-lookup"><span data-stu-id="0b81d-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="0b81d-116">В следующем примере приводится определение тела выражения для метода `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="0b81d-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="0b81d-117">Это сокращенная версия следующего определения метода:</span><span class="sxs-lookup"><span data-stu-id="0b81d-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="0b81d-118">Определения тела выражения для методов и доступных только для чтения свойств поддерживаются начиная с версии C# 6.</span><span class="sxs-lookup"><span data-stu-id="0b81d-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="0b81d-119">Определения тела выражения для конструкторов, методов завершения, методов доступа свойств и индексаторов поддерживаются начиная с версии C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="0b81d-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="0b81d-120">Дополнительные сведения см. в разделе [Элементы, воплощающие выражение](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="0b81d-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0b81d-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="0b81d-121">Operator overloadability</span></span>

<span data-ttu-id="0b81d-122">Оператор `=>` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="0b81d-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b81d-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b81d-123">C# language specification</span></span>

<span data-ttu-id="0b81d-124">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b81d-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b81d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0b81d-125">See also</span></span>

- [<span data-ttu-id="0b81d-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0b81d-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0b81d-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0b81d-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0b81d-128">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0b81d-128">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0b81d-129">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="0b81d-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="0b81d-130">Элементы, воплощающие выражение</span><span class="sxs-lookup"><span data-stu-id="0b81d-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
