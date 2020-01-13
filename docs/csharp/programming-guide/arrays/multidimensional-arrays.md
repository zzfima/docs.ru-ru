---
title: Руководство по программированию на C#. Многомерные массивы
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: eb49f4386b6106328f1613b5ec70794ac26fc9b7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715041"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="59a8d-102">Многомерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="59a8d-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="59a8d-103">Массивы могут иметь несколько измерений.</span><span class="sxs-lookup"><span data-stu-id="59a8d-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="59a8d-104">Например, следующее объявление создает двухмерный массив из четырех строк и двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="59a8d-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="59a8d-105">Следующее объявление создает массив из трех измерений: 4, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="59a8d-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="59a8d-106">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="59a8d-106">Array Initialization</span></span>

 <span data-ttu-id="59a8d-107">Массив можно инициализировать при объявлении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="59a8d-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="59a8d-108">Также можно инициализировать массив без указания ранга.</span><span class="sxs-lookup"><span data-stu-id="59a8d-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="59a8d-109">Чтобы объявить переменную массива без инициализации, используйте оператор `new` для присвоения массива переменной.</span><span class="sxs-lookup"><span data-stu-id="59a8d-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="59a8d-110">Использование оператора `new` показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="59a8d-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="59a8d-111">В следующем примере присваивается значение конкретному элементу массива.</span><span class="sxs-lookup"><span data-stu-id="59a8d-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="59a8d-112">Аналогичным образом, в следующем примере получается значение конкретного элемента массива, которое присваивается переменной `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="59a8d-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="59a8d-113">В следующем примере кода элементы массива инициализируются с использованием значений по умолчанию (кроме массивов массивов).</span><span class="sxs-lookup"><span data-stu-id="59a8d-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="59a8d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="59a8d-114">See also</span></span>

- [<span data-ttu-id="59a8d-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="59a8d-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="59a8d-116">Массивы</span><span class="sxs-lookup"><span data-stu-id="59a8d-116">Arrays</span></span>](./index.md)
- [<span data-ttu-id="59a8d-117">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="59a8d-117">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="59a8d-118">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="59a8d-118">Jagged Arrays</span></span>](./jagged-arrays.md)
