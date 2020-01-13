---
title: Делегаты с именованными методами и Руководство по программированию на C#. Анонимные методы
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 1ec366999ca6457471b705fa83f06fcde4293f4e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712381"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="68e59-102">Делегаты с именованными методами и Анонимные методы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="68e59-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="68e59-103">[Делегат](../../language-reference/builtin-types/reference-types.md) можно связать с именованным методом.</span><span class="sxs-lookup"><span data-stu-id="68e59-103">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="68e59-104">При создании экземпляра делегата с использованием именованного метода этот метод передается в качестве параметра, например:</span><span class="sxs-lookup"><span data-stu-id="68e59-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="68e59-105">Это называется использованием именованного метода.</span><span class="sxs-lookup"><span data-stu-id="68e59-105">This is called using a named method.</span></span> <span data-ttu-id="68e59-106">Делегаты, сконструированные с использованием именованного метода, могут инкапсулировать либо [статический](../../language-reference/keywords/static.md) метод, либо метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="68e59-106">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="68e59-107">Именованные методы являются единственным способом создать экземпляр делегата в ранних версиях C#.</span><span class="sxs-lookup"><span data-stu-id="68e59-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="68e59-108">Тем не менее в ситуациях, когда создание нового метода нежелательно, C# позволяет создать экземпляр делегата напрямую, указав код блока, который делегат будет обрабатывать при его вызове.</span><span class="sxs-lookup"><span data-stu-id="68e59-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="68e59-109">Этот блок может содержать лямбда-выражение или анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="68e59-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="68e59-110">Дополнительные сведения см. в разделе [Анонимные функции](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="68e59-110">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68e59-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="68e59-111">Remarks</span></span>  
 <span data-ttu-id="68e59-112">Метод, который передается как параметр делегата, должен иметь такую же сигнатуру, что и объявление делегата.</span><span class="sxs-lookup"><span data-stu-id="68e59-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="68e59-113">Экземпляр делегата может инкапсулировать статический метод или метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="68e59-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="68e59-114">Несмотря на то, что делегат может использовать параметр [out](../../language-reference/keywords/out-parameter-modifier.md), не рекомендуется делать это для делегатов многоадресных событий, поскольку в этом случае невозможно определить, какой делегат будет вызван.</span><span class="sxs-lookup"><span data-stu-id="68e59-114">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="68e59-115">Пример 1</span><span class="sxs-lookup"><span data-stu-id="68e59-115">Example 1</span></span>  
 <span data-ttu-id="68e59-116">Ниже приведен простой пример объявления и использования делегата.</span><span class="sxs-lookup"><span data-stu-id="68e59-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="68e59-117">Обратите внимание, что делегат `Del` и связанный с ним метод `MultiplyNumbers` имеют одинаковые сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="68e59-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="68e59-118">Пример 2</span><span class="sxs-lookup"><span data-stu-id="68e59-118">Example 2</span></span>  
 <span data-ttu-id="68e59-119">В следующем примере делегат, сопоставленный одновременно со статическим методом и методом экземпляра, возвращает информацию из каждого из них.</span><span class="sxs-lookup"><span data-stu-id="68e59-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="68e59-120">См. также</span><span class="sxs-lookup"><span data-stu-id="68e59-120">See also</span></span>

- [<span data-ttu-id="68e59-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="68e59-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="68e59-122">Делегаты</span><span class="sxs-lookup"><span data-stu-id="68e59-122">Delegates</span></span>](./index.md)
- [<span data-ttu-id="68e59-123">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="68e59-123">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="68e59-124">События</span><span class="sxs-lookup"><span data-stu-id="68e59-124">Events</span></span>](../events/index.md)
