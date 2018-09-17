---
title: delegate (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 7a5f46d137e22da01b2ab6cd3eee57d66c411e8f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45648464"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="40d0c-102">delegate (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="40d0c-102">delegate (C# Reference)</span></span>

<span data-ttu-id="40d0c-103">Объявление типа делегата аналогично сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="40d0c-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="40d0c-104">Оно имеет возвращаемое значение и любое число параметров любого типа:</span><span class="sxs-lookup"><span data-stu-id="40d0c-104">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

<span data-ttu-id="40d0c-105">Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="40d0c-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="40d0c-106">Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными.</span><span class="sxs-lookup"><span data-stu-id="40d0c-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="40d0c-107">Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="40d0c-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="40d0c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="40d0c-108">Remarks</span></span>

<span data-ttu-id="40d0c-109">Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="40d0c-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>

<span data-ttu-id="40d0c-110">Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом.</span><span class="sxs-lookup"><span data-stu-id="40d0c-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="40d0c-111">Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="40d0c-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

<span data-ttu-id="40d0c-112">Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры.</span><span class="sxs-lookup"><span data-stu-id="40d0c-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="40d0c-113">Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="40d0c-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="40d0c-114">Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе.</span><span class="sxs-lookup"><span data-stu-id="40d0c-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="40d0c-115">В этом разделе рассматриваются оба способа создания экземпляров делегатов.</span><span class="sxs-lookup"><span data-stu-id="40d0c-115">Both ways of instantiating delegates are discussed in this section.</span></span>

## <a name="example"></a><span data-ttu-id="40d0c-116">Пример</span><span class="sxs-lookup"><span data-stu-id="40d0c-116">Example</span></span>

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="40d0c-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="40d0c-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="40d0c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="40d0c-118">See also</span></span>

- [<span data-ttu-id="40d0c-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="40d0c-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="40d0c-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="40d0c-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="40d0c-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="40d0c-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="40d0c-122">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="40d0c-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="40d0c-123">Делегаты</span><span class="sxs-lookup"><span data-stu-id="40d0c-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="40d0c-124">События</span><span class="sxs-lookup"><span data-stu-id="40d0c-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="40d0c-125">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="40d0c-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
- [<span data-ttu-id="40d0c-126">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="40d0c-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
