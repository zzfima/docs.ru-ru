---
title: "delegate (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="f6913-102">delegate (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f6913-102">delegate (C# Reference)</span></span>
<span data-ttu-id="f6913-103">Объявление типа делегата аналогично сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="f6913-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="f6913-104">Оно имеет возвращаемое значение и любое число параметров любого типа:</span><span class="sxs-lookup"><span data-stu-id="f6913-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="f6913-105">Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="f6913-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="f6913-106">Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными.</span><span class="sxs-lookup"><span data-stu-id="f6913-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="f6913-107">Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="f6913-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6913-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6913-108">Remarks</span></span>  
 <span data-ttu-id="f6913-109">Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6913-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="f6913-110">Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом.</span><span class="sxs-lookup"><span data-stu-id="f6913-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="f6913-111">Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f6913-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="f6913-112">Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры.</span><span class="sxs-lookup"><span data-stu-id="f6913-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="f6913-113">Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span><span class="sxs-lookup"><span data-stu-id="f6913-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="f6913-114">Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе.</span><span class="sxs-lookup"><span data-stu-id="f6913-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="f6913-115">В этом разделе рассматриваются оба способа создания экземпляров делегатов.</span><span class="sxs-lookup"><span data-stu-id="f6913-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6913-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f6913-116">Example</span></span>  
 <span data-ttu-id="f6913-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6913-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f6913-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f6913-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6913-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f6913-119">See Also</span></span>  
 <span data-ttu-id="f6913-120">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f6913-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f6913-122">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f6913-123">[Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="f6913-124">[Делегаты](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="f6913-125">[События](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="f6913-126">[Делегаты с именованными методами и Делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f6913-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="f6913-127">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="f6913-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

