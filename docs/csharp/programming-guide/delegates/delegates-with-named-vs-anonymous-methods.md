---
title: "Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
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
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="1b8d8-102">Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="1b8d8-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="1b8d8-103">[Делегат](../../../csharp/language-reference/keywords/delegate.md) можно связать с именованным методом.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="1b8d8-104">При создании экземпляра делегата с использованием именованного метода этот метод передается в качестве параметра, например:</span><span class="sxs-lookup"><span data-stu-id="1b8d8-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 <span data-ttu-id="1b8d8-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b8d8-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="1b8d8-106">Это называется использованием именованного метода.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-106">This is called using a named method.</span></span> <span data-ttu-id="1b8d8-107">Делегаты, сконструированные с использованием именованного метода, могут инкапсулировать либо [статический](../../../csharp/language-reference/keywords/static.md) метод, либо метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-107">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="1b8d8-108">Именованные методы являются единственным способом создать экземпляр делегата в ранних версиях C#.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-108">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="1b8d8-109">Тем не менее в ситуациях, когда создание нового метода нежелательно, C# позволяет создать экземпляр делегата напрямую, указав код блока, который делегат будет обрабатывать при его вызове.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-109">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="1b8d8-110">Этот блок может содержать лямбда-выражение или анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-110">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="1b8d8-111">Дополнительные сведения см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1b8d8-111">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b8d8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b8d8-112">Remarks</span></span>  
 <span data-ttu-id="1b8d8-113">Метод, который передается как параметр делегата, должен иметь такую же сигнатуру, что и объявление делегата.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-113">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="1b8d8-114">Экземпляр делегата может инкапсулировать статический метод или метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-114">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="1b8d8-115">Несмотря на то, что делегат может использовать параметр [out](../../../csharp/language-reference/keywords/out.md), не рекомендуется делать это для делегатов многоадресных событий, поскольку в этом случае невозможно определить, какой делегат будет вызван.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-115">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="1b8d8-116">Пример 1</span><span class="sxs-lookup"><span data-stu-id="1b8d8-116">Example 1</span></span>  
 <span data-ttu-id="1b8d8-117">Ниже приведен простой пример объявления и использования делегата.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-117">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="1b8d8-118">Обратите внимание, что делегат `Del` и связанный с ним метод `MultiplyNumbers` имеют одинаковые сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-118">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 <span data-ttu-id="1b8d8-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b8d8-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="1b8d8-120">Пример 2</span><span class="sxs-lookup"><span data-stu-id="1b8d8-120">Example 2</span></span>  
 <span data-ttu-id="1b8d8-121">В следующем примере делегат, сопоставленный одновременно со статическим методом и методом экземпляра, возвращает информацию из каждого из них.</span><span class="sxs-lookup"><span data-stu-id="1b8d8-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 <span data-ttu-id="1b8d8-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b8d8-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8d8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1b8d8-123">See Also</span></span>  
 <span data-ttu-id="1b8d8-124">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b8d8-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1b8d8-125">[Делегаты](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b8d8-125">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="1b8d8-126">[Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="1b8d8-126">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="1b8d8-127">[Практическое руководство. Объединение делегатов (многоадресные делегаты)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="1b8d8-127">[How to: Combine Delegates (Multicast Delegates)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span></span>  
 [<span data-ttu-id="1b8d8-128">События</span><span class="sxs-lookup"><span data-stu-id="1b8d8-128">Events</span></span>](../../../csharp/programming-guide/events/index.md)

