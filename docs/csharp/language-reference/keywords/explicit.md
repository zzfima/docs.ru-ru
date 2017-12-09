---
title: "explicit (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords: explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eab79d3ac48192f3c176ed44685ab58e50fc89be
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="explicit-c-reference"></a><span data-ttu-id="ea5f2-102">explicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ea5f2-102">explicit (C# Reference)</span></span>
<span data-ttu-id="ea5f2-103">Ключевое слово `explicit` объявляет оператор преобразования определяемого пользователем типа, который должен быть вызван с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="ea5f2-104">Например, этот оператор выполняет преобразование из класса Fahrenheit в класс Celsius:</span><span class="sxs-lookup"><span data-stu-id="ea5f2-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="ea5f2-105">Такой оператор преобразования можно вызвать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ea5f2-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="ea5f2-106">Оператор преобразования преобразует исходный тип в конечный.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="ea5f2-107">Исходный тип предоставляет оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="ea5f2-108">В отличие от неявного преобразования, операторы явного преобразования должны вызываться с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="ea5f2-109">Если операция преобразования может вызвать исключения или привести к потере данных, следует пометить ее как `explicit`.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="ea5f2-110">Это предотвращает выполнение компилятором скрытого вызова операции преобразования с возможно непредвиденными последствиями.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="ea5f2-111">Пропуск приведения приводит к ошибке времени компиляции CS0266.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="ea5f2-112">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ea5f2-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea5f2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ea5f2-113">Example</span></span>  
 <span data-ttu-id="ea5f2-114">В следующем примере приводятся классы `Fahrenheit` и `Celsius`, каждый из которых предоставляет явный оператор преобразования в другой класс.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="ea5f2-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ea5f2-115">Example</span></span>  
 <span data-ttu-id="ea5f2-116">В следующем примере определяется структура `Digit`, представляющая одну десятичную цифру.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="ea5f2-117">Оператор определен для преобразования из `byte` в `Digit`, но поскольку не все байты могут быть преобразованы в `Digit`, выполняется явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="ea5f2-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ea5f2-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ea5f2-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea5f2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ea5f2-119">See Also</span></span>  
 [<span data-ttu-id="ea5f2-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ea5f2-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ea5f2-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ea5f2-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ea5f2-122">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ea5f2-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ea5f2-123">implicit</span><span class="sxs-lookup"><span data-stu-id="ea5f2-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="ea5f2-124">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ea5f2-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="ea5f2-125">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="ea5f2-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [<span data-ttu-id="ea5f2-126">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="ea5f2-126">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
