---
title: Передача массивов в качестве аргументов (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315520"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="51e38-102">Передача массивов в качестве аргументов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="51e38-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="51e38-103">Массивы можно передавать в качестве аргументов в параметры метода.</span><span class="sxs-lookup"><span data-stu-id="51e38-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="51e38-104">Поскольку массивы представляют собой ссылочные типы, метод может изменять значения элементов.</span><span class="sxs-lookup"><span data-stu-id="51e38-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="51e38-105">Передача одномерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="51e38-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="51e38-106">Инициализированный одномерный массив можно передать в метод.</span><span class="sxs-lookup"><span data-stu-id="51e38-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="51e38-107">Например, следующий оператор передает массив в метод печати.</span><span class="sxs-lookup"><span data-stu-id="51e38-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="51e38-108">В следующем примере кода показана разделяемая реализация метода печати.</span><span class="sxs-lookup"><span data-stu-id="51e38-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="51e38-109">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="51e38-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="51e38-110">Пример</span><span class="sxs-lookup"><span data-stu-id="51e38-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51e38-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="51e38-111">Description</span></span>  
 <span data-ttu-id="51e38-112">В следующем примере массив строк инициализируется и передается в качестве аргумента в метод `PrintArray` для строк.</span><span class="sxs-lookup"><span data-stu-id="51e38-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="51e38-113">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="51e38-113">The method displays the elements of the array.</span></span> <span data-ttu-id="51e38-114">Далее вызываются методы `ChangeArray` и `ChangeArrayElement`. Это позволяет продемонстрировать, что передача аргумента массива по значению не позволяет предотвратить изменение элементов массива.</span><span class="sxs-lookup"><span data-stu-id="51e38-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51e38-115">Код</span><span class="sxs-lookup"><span data-stu-id="51e38-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="51e38-116">Передача многомерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="51e38-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="51e38-117">Инициализированный многомерный массив можно передать в метод так же, как и одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="51e38-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="51e38-118">В следующем коде показано разделяемое объявление метода печати, который принимает в качестве аргумента двухмерный массив.</span><span class="sxs-lookup"><span data-stu-id="51e38-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="51e38-119">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="51e38-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="51e38-120">Пример</span><span class="sxs-lookup"><span data-stu-id="51e38-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51e38-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="51e38-121">Description</span></span>  
 <span data-ttu-id="51e38-122">В следующем примере инициализируется двухмерный массив целых чисел, который передается в метод `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="51e38-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="51e38-123">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="51e38-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51e38-124">Код</span><span class="sxs-lookup"><span data-stu-id="51e38-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="51e38-125">См. также</span><span class="sxs-lookup"><span data-stu-id="51e38-125">See Also</span></span>  
 [<span data-ttu-id="51e38-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="51e38-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="51e38-127">Массивы</span><span class="sxs-lookup"><span data-stu-id="51e38-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="51e38-128">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="51e38-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="51e38-129">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="51e38-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="51e38-130">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="51e38-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
