---
title: Использование оператора foreach с массивами (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="90365-102">Использование оператора foreach с массивами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="90365-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="90365-103">В C# также предусмотрен оператор [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="90365-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="90365-104">Этот оператор обеспечивает простой и понятный способ итерации по элементам массива или любой перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="90365-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="90365-105">Оператор `foreach` обрабатывает элементы в порядке, возвращенном массивом или перечислителем типа коллекции, обычно от нулевого до последнего элемента.</span><span class="sxs-lookup"><span data-stu-id="90365-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="90365-106">Например, следующий код создает массив `numbers` и осуществляет итерацию по нему с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="90365-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 <span data-ttu-id="90365-107">Этот же метод можно использовать для итерации по элементам в многомерных массивах, например:</span><span class="sxs-lookup"><span data-stu-id="90365-107">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 <span data-ttu-id="90365-108">Однако для лучшего управления элементами в многомерных массивах можно использовать вложенный цикл [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="90365-108">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90365-109">См. также</span><span class="sxs-lookup"><span data-stu-id="90365-109">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="90365-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="90365-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="90365-111">Массивы</span><span class="sxs-lookup"><span data-stu-id="90365-111">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="90365-112">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="90365-112">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="90365-113">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="90365-113">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="90365-114">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="90365-114">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
