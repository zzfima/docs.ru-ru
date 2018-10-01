---
title: Многомерные массивы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a1d7a0a014c330682316e869f6727082fa3b31ef
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47421483"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="ad2bb-102">Многомерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ad2bb-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="ad2bb-103">Массивы могут иметь несколько измерений.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="ad2bb-104">Например, следующее объявление создает двухмерный массив из четырех строк и двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 <span data-ttu-id="ad2bb-105">Следующее объявление создает массив из трех измерений: 4, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="ad2bb-106">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="ad2bb-106">Array Initialization</span></span>

 <span data-ttu-id="ad2bb-107">Массив можно инициализировать при объявлении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 <span data-ttu-id="ad2bb-108">Также можно инициализировать массив без указания ранга.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 <span data-ttu-id="ad2bb-109">Чтобы объявить переменную массива без инициализации, используйте оператор `new` для присвоения массива переменной.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="ad2bb-110">Использование оператора `new` показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 <span data-ttu-id="ad2bb-111">В следующем примере присваивается значение конкретному элементу массива.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 <span data-ttu-id="ad2bb-112">Аналогичным образом, в следующем примере получается значение конкретного элемента массива, которое присваивается переменной `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 <span data-ttu-id="ad2bb-113">В следующем примере кода элементы массива инициализируются с использованием значений по умолчанию (кроме массивов массивов).</span><span class="sxs-lookup"><span data-stu-id="ad2bb-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ad2bb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ad2bb-114">See Also</span></span>

- [<span data-ttu-id="ad2bb-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ad2bb-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ad2bb-116">Массивы</span><span class="sxs-lookup"><span data-stu-id="ad2bb-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="ad2bb-117">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="ad2bb-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="ad2bb-118">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="ad2bb-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
