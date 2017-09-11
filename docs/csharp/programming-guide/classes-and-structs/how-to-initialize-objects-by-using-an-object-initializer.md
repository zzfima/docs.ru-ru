---
title: "Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#)."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
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
ms.openlocfilehash: 01f2391680d9236b42f0d015b944b8f12455d0c8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="983bc-102">Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#).</span><span class="sxs-lookup"><span data-stu-id="983bc-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="983bc-103">Инициализаторы объектов можно использовать для декларативной инициализации объектов типов без явного вызова конструктора для типа.</span><span class="sxs-lookup"><span data-stu-id="983bc-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="983bc-104">Следующие примеры демонстрируют использование инициализаторов объектов с именованными объектами.</span><span class="sxs-lookup"><span data-stu-id="983bc-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="983bc-105">Компилятор выполняет обработку инициализаторов объектов, сначала получая доступ к конструктору экземпляра по умолчанию, а затем обрабатывая инициализации членов.</span><span class="sxs-lookup"><span data-stu-id="983bc-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="983bc-106">Таким образом, если конструктор по умолчанию объявляется как `private` в классе, произойдет сбой инициализаторов объектов, требующих открытого доступа.</span><span class="sxs-lookup"><span data-stu-id="983bc-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="983bc-107">При определении анонимного типа использовать инициализатор объекта обязательно.</span><span class="sxs-lookup"><span data-stu-id="983bc-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="983bc-108">Дополнительные сведения см. в разделе [Практическое руководство. Возвращение поднаборов свойств элементов в запросе](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="983bc-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="983bc-109">Пример</span><span class="sxs-lookup"><span data-stu-id="983bc-109">Example</span></span>  
 <span data-ttu-id="983bc-110">В следующем примере показана инициализация нового типа `StudentName` с помощью инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="983bc-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 <span data-ttu-id="983bc-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="983bc-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="983bc-112">Пример</span><span class="sxs-lookup"><span data-stu-id="983bc-112">Example</span></span>  
 <span data-ttu-id="983bc-113">В следующем примере показана инициализация коллекции типов `StudentName` с помощью инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="983bc-113">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="983bc-114">Обратите внимание, что инициализатор коллекции представляет собой ряд инициализаторов объектов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="983bc-114">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 <span data-ttu-id="983bc-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="983bc-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="983bc-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="983bc-116">Compiling the Code</span></span>  
 <span data-ttu-id="983bc-117">Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, которое было создано в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="983bc-117">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="983bc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="983bc-118">See Also</span></span>  
 <span data-ttu-id="983bc-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="983bc-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="983bc-120">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="983bc-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

