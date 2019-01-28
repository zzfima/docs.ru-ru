---
title: delegate. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: f9df40c3ca721ca97b575a05377bbac29a29aec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560611"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="f680d-102">delegate (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f680d-102">delegate (C# Reference)</span></span>

<span data-ttu-id="f680d-103">Объявление типа делегата аналогично сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="f680d-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="f680d-104">Оно имеет возвращаемое значение и любое число параметров любого типа:</span><span class="sxs-lookup"><span data-stu-id="f680d-104">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

<span data-ttu-id="f680d-105">Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="f680d-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="f680d-106">Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными.</span><span class="sxs-lookup"><span data-stu-id="f680d-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="f680d-107">Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="f680d-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="f680d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f680d-108">Remarks</span></span>

<span data-ttu-id="f680d-109">Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f680d-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>

<span data-ttu-id="f680d-110">Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом.</span><span class="sxs-lookup"><span data-stu-id="f680d-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="f680d-111">Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f680d-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

<span data-ttu-id="f680d-112">Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры.</span><span class="sxs-lookup"><span data-stu-id="f680d-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="f680d-113">Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="f680d-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="f680d-114">Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе.</span><span class="sxs-lookup"><span data-stu-id="f680d-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="f680d-115">В этом разделе рассматриваются оба способа создания экземпляров делегатов.</span><span class="sxs-lookup"><span data-stu-id="f680d-115">Both ways of instantiating delegates are discussed in this section.</span></span>

## <a name="example"></a><span data-ttu-id="f680d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f680d-116">Example</span></span>

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="f680d-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f680d-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f680d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f680d-118">See also</span></span>

- [<span data-ttu-id="f680d-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f680d-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="f680d-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f680d-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f680d-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f680d-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="f680d-122">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="f680d-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
- [<span data-ttu-id="f680d-123">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f680d-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="f680d-124">События</span><span class="sxs-lookup"><span data-stu-id="f680d-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="f680d-125">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="f680d-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
- [<span data-ttu-id="f680d-126">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="f680d-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="f680d-127">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="f680d-127">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
