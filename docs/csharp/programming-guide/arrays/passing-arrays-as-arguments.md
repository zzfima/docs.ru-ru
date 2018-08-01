---
title: Передача массивов в качестве аргументов (руководство по программированию на C#)
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 0289297be9d7b4989cc95d2b50b92dae9ee831f7
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199235"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="3256d-102">Передача массивов в качестве аргументов (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3256d-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="3256d-103">Массивы можно передавать в качестве аргументов в параметры метода.</span><span class="sxs-lookup"><span data-stu-id="3256d-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="3256d-104">Поскольку массивы представляют собой ссылочные типы, метод может изменять значения элементов.</span><span class="sxs-lookup"><span data-stu-id="3256d-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="3256d-105">Передача одномерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="3256d-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="3256d-106">Инициализированный одномерный массив можно передать в метод.</span><span class="sxs-lookup"><span data-stu-id="3256d-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="3256d-107">Например, следующий оператор передает массив в метод печати.</span><span class="sxs-lookup"><span data-stu-id="3256d-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="3256d-108">В следующем примере кода показана разделяемая реализация метода печати.</span><span class="sxs-lookup"><span data-stu-id="3256d-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="3256d-109">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3256d-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="3256d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3256d-110">Example</span></span>

<span data-ttu-id="3256d-111">В следующем примере массив строк инициализируется и передается в качестве аргумента в метод `DisplayArray` для строк.</span><span class="sxs-lookup"><span data-stu-id="3256d-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="3256d-112">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="3256d-112">The method displays the elements of the array.</span></span> <span data-ttu-id="3256d-113">Затем метод `ChangeArray` размещает элементы массива в обратном порядке, а метод `ChangeArrayElements` изменяет первые три элемента массива.</span><span class="sxs-lookup"><span data-stu-id="3256d-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="3256d-114">После возврата каждого метода метод `DisplayArray` показывает, что передача массива по значению не препятствует изменению элементов массива.</span><span class="sxs-lookup"><span data-stu-id="3256d-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="3256d-115">Передача многомерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="3256d-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="3256d-116">Инициализированный многомерный массив можно передать в метод так же, как и одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="3256d-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="3256d-117">В следующем коде показано разделяемое объявление метода печати, который принимает в качестве аргумента двухмерный массив.</span><span class="sxs-lookup"><span data-stu-id="3256d-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="3256d-118">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3256d-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="3256d-119">Пример</span><span class="sxs-lookup"><span data-stu-id="3256d-119">Example</span></span>

<span data-ttu-id="3256d-120">В следующем примере инициализируется двухмерный массив целых чисел, который передается в метод `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="3256d-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="3256d-121">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="3256d-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="3256d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3256d-122">See also</span></span>

[<span data-ttu-id="3256d-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3256d-123">C# Programming Guide</span></span>](../index.md)  
[<span data-ttu-id="3256d-124">Массивы</span><span class="sxs-lookup"><span data-stu-id="3256d-124">Arrays</span></span>](index.md)  
[<span data-ttu-id="3256d-125">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="3256d-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
[<span data-ttu-id="3256d-126">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="3256d-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
[<span data-ttu-id="3256d-127">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="3256d-127">Jagged Arrays</span></span>](jagged-arrays.md)  