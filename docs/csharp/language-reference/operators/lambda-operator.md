---
title: Оператор =>. Справочник по C#
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: b8d1a4e3971eb30e76bf543497931ce029c5541d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036376"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5af7c-102">Оператор => (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5af7c-102">=> operator (C# reference)</span></span>

<span data-ttu-id="5af7c-103">Токен `=>` поддерживается в двух формах: в виде [лямбда-оператора](#lambda-operator) и в виде разделителя имени члена и реализации члена в [определении тела выражения](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="5af7c-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="5af7c-104">Лямбда-оператор</span><span class="sxs-lookup"><span data-stu-id="5af7c-104">Lambda operator</span></span>

<span data-ttu-id="5af7c-105">В [лямбда-выражениях](../../programming-guide/statements-expressions-operators/lambda-expressions.md) лямбда-оператор `=>` используется для отделения входных параметров с левой стороны от тела лямбда-выражения с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="5af7c-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="5af7c-106">В следующих примерах используется функция [LINQ](../../programming-guide/concepts/linq/index.md) с синтаксисом метода для демонстрации применения лямбда-выражений:</span><span class="sxs-lookup"><span data-stu-id="5af7c-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="5af7c-107">Входные параметры лямбда-выражений строго типизируются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="5af7c-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="5af7c-108">Если компилятор может выводить типы входных параметров, как в предыдущем примере, вы можете опустить объявления типа.</span><span class="sxs-lookup"><span data-stu-id="5af7c-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="5af7c-109">Если требуется указать тип входных параметров, это необходимо делать для каждого такого параметра, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5af7c-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="5af7c-110">В следующем примере показано, как определить лямбда-выражение без входных параметров:</span><span class="sxs-lookup"><span data-stu-id="5af7c-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="5af7c-111">Дополнительные сведения см. в разделе [Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5af7c-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="5af7c-112">Определения тела выражения</span><span class="sxs-lookup"><span data-stu-id="5af7c-112">Expression body definition</span></span>

<span data-ttu-id="5af7c-113">Определение тела выражения имеет следующий общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5af7c-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="5af7c-114">где `expression` — любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="5af7c-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="5af7c-115">Тип возвращаемого значения `expression` должен быть неявно преобразуемым в тип возвращаемого значения элемента.</span><span class="sxs-lookup"><span data-stu-id="5af7c-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="5af7c-116">Если для элемента возвращается значение типа `void` или если элемент является конструктором, методом завершения или методом доступа свойства `set`, значение `expression` должно быть [*выражением оператора*](~/_csharplang/spec/statements.md#expression-statements). В этом случае оно может быть любого типа.</span><span class="sxs-lookup"><span data-stu-id="5af7c-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="5af7c-117">В следующем примере приводится определение тела выражения для метода `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="5af7c-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="5af7c-118">Это сокращенная версия следующего определения метода:</span><span class="sxs-lookup"><span data-stu-id="5af7c-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="5af7c-119">Начиная с версии C# 6, поддерживаются определения тела выражения для методов, операторов и доступных только для чтения свойств.</span><span class="sxs-lookup"><span data-stu-id="5af7c-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="5af7c-120">Начиная с версии C# 7.0, поддерживаются определения тела выражения для конструкторов, методов завершения, методов доступа свойств и индексаторов.</span><span class="sxs-lookup"><span data-stu-id="5af7c-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="5af7c-121">Дополнительные сведения см. в разделе [Элементы, воплощающие выражение](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="5af7c-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5af7c-122">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="5af7c-122">Operator overloadability</span></span>

<span data-ttu-id="5af7c-123">Оператор `=>` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="5af7c-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5af7c-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5af7c-124">C# language specification</span></span>

<span data-ttu-id="5af7c-125">См. сведения о лямбда-операторе в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5af7c-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5af7c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5af7c-126">See also</span></span>

- [<span data-ttu-id="5af7c-127">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5af7c-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5af7c-128">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5af7c-128">C# operators</span></span>](index.md)
