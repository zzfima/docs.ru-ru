---
title: "Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="1b643-102">Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1b643-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="1b643-103">Как и все параметры [out](../../../csharp/language-reference/keywords/out.md), параметр `out` типа массива перед использованием необходимо присвоить, то есть он должен быть присвоен вызываемым объектом.</span><span class="sxs-lookup"><span data-stu-id="1b643-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="1b643-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b643-104">For example:</span></span>  
  
 <span data-ttu-id="1b643-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b643-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="1b643-106">Как и все параметры [ref](../../../csharp/language-reference/keywords/ref.md), параметр `ref` типа массива должен быть явно присвоен вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="1b643-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="1b643-107">Таким образом, явное присвоение вызываемым объектом не требуется.</span><span class="sxs-lookup"><span data-stu-id="1b643-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="1b643-108">Параметр `ref` типа массива в результате вызова может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="1b643-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="1b643-109">Например, массиву можно присвоить значение [null](../../../csharp/language-reference/keywords/null.md), или же его можно инициализировать в другой массив.</span><span class="sxs-lookup"><span data-stu-id="1b643-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="1b643-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b643-110">For example:</span></span>  
  
 <span data-ttu-id="1b643-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b643-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="1b643-112">В следующих двух примерах демонстрируются различия между параметрами `out` и `ref` при их использовании для передачи массивов в методы.</span><span class="sxs-lookup"><span data-stu-id="1b643-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b643-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1b643-113">Example</span></span>  
 <span data-ttu-id="1b643-114">В следующем примере массив `theArray` объявляется в вызывающем объекте (методе `Main`) и инициализируется в методе `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="1b643-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="1b643-115">Затем элементы массива возвращаются вызывающему объекту и отображаются.</span><span class="sxs-lookup"><span data-stu-id="1b643-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="1b643-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b643-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b643-117">Пример</span><span class="sxs-lookup"><span data-stu-id="1b643-117">Example</span></span>  
 <span data-ttu-id="1b643-118">В следующем примере массив `theArray` инициализируется в вызывающем объекте (методе `Main`) и передается в метод `FillArray` с помощью параметра `ref`.</span><span class="sxs-lookup"><span data-stu-id="1b643-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="1b643-119">Некоторые элементы массива в методе `FillArray` обновляются.</span><span class="sxs-lookup"><span data-stu-id="1b643-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="1b643-120">Затем элементы массива возвращаются вызывающему объекту и отображаются.</span><span class="sxs-lookup"><span data-stu-id="1b643-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="1b643-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b643-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b643-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1b643-122">See Also</span></span>  
 <span data-ttu-id="1b643-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="1b643-124">[Модификатор параметров out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="1b643-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1b643-126">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="1b643-127">[Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="1b643-128">[Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1b643-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="1b643-129">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="1b643-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

