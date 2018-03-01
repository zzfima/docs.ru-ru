---
title: "Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2d4e613491b26e82523d230398af3ec34b4d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="8011c-102">Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8011c-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="8011c-103">Как и все параметры [out](../../../csharp/language-reference/keywords/out.md), параметр `out` типа массива перед использованием необходимо присвоить, то есть он должен быть присвоен вызываемым объектом.</span><span class="sxs-lookup"><span data-stu-id="8011c-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="8011c-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="8011c-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="8011c-105">Как и все параметры [ref](../../../csharp/language-reference/keywords/ref.md), параметр `ref` типа массива должен быть явно присвоен вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="8011c-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="8011c-106">Таким образом, явное присвоение вызываемым объектом не требуется.</span><span class="sxs-lookup"><span data-stu-id="8011c-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="8011c-107">Параметр `ref` типа массива в результате вызова может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="8011c-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="8011c-108">Например, массиву можно присвоить значение [null](../../../csharp/language-reference/keywords/null.md), или же его можно инициализировать в другой массив.</span><span class="sxs-lookup"><span data-stu-id="8011c-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="8011c-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="8011c-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="8011c-110">В следующих двух примерах демонстрируются различия между параметрами `out` и `ref` при их использовании для передачи массивов в методы.</span><span class="sxs-lookup"><span data-stu-id="8011c-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8011c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8011c-111">Example</span></span>  
 <span data-ttu-id="8011c-112">В следующем примере массив `theArray` объявляется в вызывающем объекте (методе `Main`) и инициализируется в методе `FillArray`.</span><span class="sxs-lookup"><span data-stu-id="8011c-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="8011c-113">Затем элементы массива возвращаются вызывающему объекту и отображаются.</span><span class="sxs-lookup"><span data-stu-id="8011c-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="8011c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8011c-114">Example</span></span>  
 <span data-ttu-id="8011c-115">В следующем примере массив `theArray` инициализируется в вызывающем объекте (методе `Main`) и передается в метод `FillArray` с помощью параметра `ref`.</span><span class="sxs-lookup"><span data-stu-id="8011c-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="8011c-116">Некоторые элементы массива в методе `FillArray` обновляются.</span><span class="sxs-lookup"><span data-stu-id="8011c-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="8011c-117">Затем элементы массива возвращаются вызывающему объекту и отображаются.</span><span class="sxs-lookup"><span data-stu-id="8011c-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8011c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8011c-118">See Also</span></span>  
 [<span data-ttu-id="8011c-119">ref</span><span class="sxs-lookup"><span data-stu-id="8011c-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="8011c-120">модификатор параметра out</span><span class="sxs-lookup"><span data-stu-id="8011c-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="8011c-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8011c-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8011c-122">Массивы</span><span class="sxs-lookup"><span data-stu-id="8011c-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="8011c-123">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="8011c-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="8011c-124">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="8011c-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="8011c-125">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="8011c-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
