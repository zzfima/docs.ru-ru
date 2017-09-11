---
title: "Передача массивов в качестве аргументов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
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
ms.openlocfilehash: 5e83c0c119bc1448be76f83416098158c7f5d684
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="a3709-102">Передача массивов в качестве аргументов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a3709-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="a3709-103">Массивы можно передавать в качестве аргументов в параметры метода.</span><span class="sxs-lookup"><span data-stu-id="a3709-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="a3709-104">Поскольку массивы представляют собой ссылочные типы, метод может изменять значения элементов.</span><span class="sxs-lookup"><span data-stu-id="a3709-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="a3709-105">Передача одномерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="a3709-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="a3709-106">Инициализированный одномерный массив можно передать в метод.</span><span class="sxs-lookup"><span data-stu-id="a3709-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="a3709-107">Например, следующий оператор передает массив в метод печати.</span><span class="sxs-lookup"><span data-stu-id="a3709-107">For example, the following statement sends an array to a print method.</span></span>  
  
 <span data-ttu-id="a3709-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span></span>  
  
 <span data-ttu-id="a3709-109">В следующем примере кода показана разделяемая реализация метода печати.</span><span class="sxs-lookup"><span data-stu-id="a3709-109">The following code shows a partial implementation of the print method.</span></span>  
  
 <span data-ttu-id="a3709-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="a3709-111">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a3709-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="a3709-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3709-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a3709-113">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a3709-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a3709-114">Description</span></span>  
 <span data-ttu-id="a3709-115">В следующем примере массив строк инициализируется и передается в качестве аргумента в метод `PrintArray` для строк.</span><span class="sxs-lookup"><span data-stu-id="a3709-115">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="a3709-116">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="a3709-116">The method displays the elements of the array.</span></span> <span data-ttu-id="a3709-117">Далее вызываются методы `ChangeArray` и `ChangeArrayElement`. Это позволяет продемонстрировать, что передача аргумента массива по значению не позволяет предотвратить изменение элементов массива.</span><span class="sxs-lookup"><span data-stu-id="a3709-117">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3709-118">Код</span><span class="sxs-lookup"><span data-stu-id="a3709-118">Code</span></span>  
 <span data-ttu-id="a3709-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span></span>  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="a3709-120">Передача многомерных массивов в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="a3709-120">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="a3709-121">Инициализированный многомерный массив можно передать в метод так же, как и одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="a3709-121">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 <span data-ttu-id="a3709-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="a3709-123">В следующем коде показано разделяемое объявление метода печати, который принимает в качестве аргумента двухмерный массив.</span><span class="sxs-lookup"><span data-stu-id="a3709-123">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 <span data-ttu-id="a3709-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span></span>  
  
 <span data-ttu-id="a3709-125">Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a3709-125">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="a3709-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3709-127">Пример</span><span class="sxs-lookup"><span data-stu-id="a3709-127">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a3709-128">Описание</span><span class="sxs-lookup"><span data-stu-id="a3709-128">Description</span></span>  
 <span data-ttu-id="a3709-129">В следующем примере инициализируется двухмерный массив целых чисел, который передается в метод `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="a3709-129">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="a3709-130">Этот метод отображает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="a3709-130">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3709-131">Код</span><span class="sxs-lookup"><span data-stu-id="a3709-131">Code</span></span>  
 <span data-ttu-id="a3709-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="a3709-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3709-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a3709-133">See Also</span></span>  
 <span data-ttu-id="a3709-134">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3709-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a3709-135">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3709-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="a3709-136">[Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="a3709-136">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="a3709-137">[Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="a3709-137">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="a3709-138">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="a3709-138">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

