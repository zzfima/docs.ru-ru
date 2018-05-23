---
title: Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#).
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 1f5f068cd8dc3787eb8cb2cd72cc30e9ea159390
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="02571-102">Практическое руководство. Инициализация объектов с помощью инициализатора объектов (Руководство по программированию на C#).</span><span class="sxs-lookup"><span data-stu-id="02571-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="02571-103">Инициализаторы объектов можно использовать для декларативной инициализации объектов типов без явного вызова конструктора для типа.</span><span class="sxs-lookup"><span data-stu-id="02571-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="02571-104">Следующие примеры демонстрируют использование инициализаторов объектов с именованными объектами.</span><span class="sxs-lookup"><span data-stu-id="02571-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="02571-105">Компилятор выполняет обработку инициализаторов объектов, сначала получая доступ к конструктору экземпляра по умолчанию, а затем обрабатывая инициализации членов.</span><span class="sxs-lookup"><span data-stu-id="02571-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="02571-106">Таким образом, если конструктор по умолчанию объявляется как `private` в классе, произойдет сбой инициализаторов объектов, требующих открытого доступа.</span><span class="sxs-lookup"><span data-stu-id="02571-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="02571-107">При определении анонимного типа использовать инициализатор объекта обязательно.</span><span class="sxs-lookup"><span data-stu-id="02571-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="02571-108">Дополнительные сведения см. в разделе [Практическое руководство. Возвращение поднаборов свойств элементов в запросе](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="02571-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02571-109">Пример</span><span class="sxs-lookup"><span data-stu-id="02571-109">Example</span></span>  
 <span data-ttu-id="02571-110">В следующем примере показана инициализация нового типа `StudentName` с помощью инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="02571-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="02571-111">Пример</span><span class="sxs-lookup"><span data-stu-id="02571-111">Example</span></span>  
 <span data-ttu-id="02571-112">В следующем примере показана инициализация коллекции типов `StudentName` с помощью инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="02571-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="02571-113">Обратите внимание, что инициализатор коллекции представляет собой ряд инициализаторов объектов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="02571-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="02571-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="02571-114">Compiling the Code</span></span>  
 <span data-ttu-id="02571-115">Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, созданный в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02571-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02571-116">См. также</span><span class="sxs-lookup"><span data-stu-id="02571-116">See Also</span></span>  
 [<span data-ttu-id="02571-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="02571-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="02571-118">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="02571-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
