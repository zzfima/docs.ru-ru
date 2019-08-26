---
title: Руководство по программированию на C#. Многомерные массивы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: 63b8729a14e4c309e85a588c5cddc692fb6a6fad
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597411"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="1f610-102">Многомерные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1f610-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="1f610-103">Массивы могут иметь несколько измерений.</span><span class="sxs-lookup"><span data-stu-id="1f610-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="1f610-104">Например, следующее объявление создает двухмерный массив из четырех строк и двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="1f610-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="1f610-105">Следующее объявление создает массив из трех измерений: 4, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="1f610-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="1f610-106">Инициализация массива</span><span class="sxs-lookup"><span data-stu-id="1f610-106">Array Initialization</span></span>

 <span data-ttu-id="1f610-107">Массив можно инициализировать при объявлении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1f610-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="1f610-108">Также можно инициализировать массив без указания ранга.</span><span class="sxs-lookup"><span data-stu-id="1f610-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="1f610-109">Чтобы объявить переменную массива без инициализации, используйте оператор `new` для присвоения массива переменной.</span><span class="sxs-lookup"><span data-stu-id="1f610-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="1f610-110">Использование оператора `new` показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1f610-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="1f610-111">В следующем примере присваивается значение конкретному элементу массива.</span><span class="sxs-lookup"><span data-stu-id="1f610-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="1f610-112">Аналогичным образом, в следующем примере получается значение конкретного элемента массива, которое присваивается переменной `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="1f610-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="1f610-113">В следующем примере кода элементы массива инициализируются с использованием значений по умолчанию (кроме массивов массивов).</span><span class="sxs-lookup"><span data-stu-id="1f610-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="1f610-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1f610-114">See also</span></span>

- [<span data-ttu-id="1f610-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1f610-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1f610-116">Массивы</span><span class="sxs-lookup"><span data-stu-id="1f610-116">Arrays</span></span>](./index.md)
- [<span data-ttu-id="1f610-117">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="1f610-117">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="1f610-118">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="1f610-118">Jagged Arrays</span></span>](./jagged-arrays.md)
