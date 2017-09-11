---
title: "explicit (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f11a930f0be5d504c92271b66009613de5d68579
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-c-reference"></a><span data-ttu-id="154ee-102">explicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="154ee-102">explicit (C# Reference)</span></span>
<span data-ttu-id="154ee-103">Ключевое слово `explicit` объявляет оператор преобразования определяемого пользователем типа, который должен быть вызван с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="154ee-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="154ee-104">Например, этот оператор выполняет преобразование из класса Fahrenheit в класс Celsius:</span><span class="sxs-lookup"><span data-stu-id="154ee-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 <span data-ttu-id="154ee-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="154ee-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span></span>  
  
 <span data-ttu-id="154ee-106">Такой оператор преобразования можно вызвать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="154ee-106">This conversion operator can be invoked like this:</span></span>  
  
 <span data-ttu-id="154ee-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="154ee-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span></span>  
  
 <span data-ttu-id="154ee-108">Оператор преобразования преобразует исходный тип в конечный.</span><span class="sxs-lookup"><span data-stu-id="154ee-108">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="154ee-109">Исходный тип предоставляет оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="154ee-109">The source type provides the conversion operator.</span></span> <span data-ttu-id="154ee-110">В отличие от неявного преобразования, операторы явного преобразования должны вызываться с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="154ee-110">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="154ee-111">Если операция преобразования может вызвать исключения или привести к потере данных, следует пометить ее как `explicit`.</span><span class="sxs-lookup"><span data-stu-id="154ee-111">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="154ee-112">Это предотвращает выполнение компилятором скрытого вызова операции преобразования с возможно непредвиденными последствиями.</span><span class="sxs-lookup"><span data-stu-id="154ee-112">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="154ee-113">Пропуск приведения приводит к ошибке времени компиляции CS0266.</span><span class="sxs-lookup"><span data-stu-id="154ee-113">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="154ee-114">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="154ee-114">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="154ee-115">Пример</span><span class="sxs-lookup"><span data-stu-id="154ee-115">Example</span></span>  
 <span data-ttu-id="154ee-116">В следующем примере приводятся классы `Fahrenheit` и `Celsius`, каждый из которых предоставляет явный оператор преобразования в другой класс.</span><span class="sxs-lookup"><span data-stu-id="154ee-116">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 <span data-ttu-id="154ee-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="154ee-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="154ee-118">Пример</span><span class="sxs-lookup"><span data-stu-id="154ee-118">Example</span></span>  
 <span data-ttu-id="154ee-119">В следующем примере определяется структура `Digit`, представляющая одну десятичную цифру.</span><span class="sxs-lookup"><span data-stu-id="154ee-119">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="154ee-120">Оператор определен для преобразования из `byte` в `Digit`, но поскольку не все байты могут быть преобразованы в `Digit`, выполняется явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="154ee-120">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 <span data-ttu-id="154ee-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="154ee-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="154ee-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="154ee-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="154ee-123">См. также</span><span class="sxs-lookup"><span data-stu-id="154ee-123">See Also</span></span>  
 <span data-ttu-id="154ee-124">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="154ee-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="154ee-126">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="154ee-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="154ee-128">[оператор (справочник по C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-128">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="154ee-129">[Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span><span class="sxs-lookup"><span data-stu-id="154ee-129">[How to: Implement User-Defined Conversions Between Structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span></span>  
 [<span data-ttu-id="154ee-130">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="154ee-130">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)

