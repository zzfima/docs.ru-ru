---
title: "Преобразование массивов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40dc9805157dd0bc991ca2375c3436aa6b6e09a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="6cce3-102">Преобразование массивов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cce3-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="6cce3-103">Тип массива можно преобразовать в другой тип массива при соблюдении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="6cce3-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="6cce3-104">**Равенство ранга.**</span><span class="sxs-lookup"><span data-stu-id="6cce3-104">**Equal Rank.**</span></span> <span data-ttu-id="6cce3-105">Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое число измерений.</span><span class="sxs-lookup"><span data-stu-id="6cce3-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="6cce3-106">Однако длины соответствующих измерений не обязательно должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="6cce3-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="6cce3-107">**Тип данных элемента.**</span><span class="sxs-lookup"><span data-stu-id="6cce3-107">**Element Data Type.**</span></span> <span data-ttu-id="6cce3-108">Типы данных элементов обоих массивов должны быть ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="6cce3-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="6cce3-109">Не удается преобразовать `Integer` массив `Long` или даже к `Object` массива, так как тип по крайней мере одно значение.</span><span class="sxs-lookup"><span data-stu-id="6cce3-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="6cce3-110">Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="6cce3-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="6cce3-111">**Возможность преобразования.**</span><span class="sxs-lookup"><span data-stu-id="6cce3-111">**Convertibility.**</span></span> <span data-ttu-id="6cce3-112">Необходимо, расширяющее или сужающее преобразование между типами элементов двух массивов.</span><span class="sxs-lookup"><span data-stu-id="6cce3-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="6cce3-113">Пример, который не соответствует этим требованиям — попытка преобразования между `String` массива и массив класса, производного от <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cce3-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6cce3-114">Эти два типа не имеют ничего общего, и преобразование любого типа, не существует между ними.</span><span class="sxs-lookup"><span data-stu-id="6cce3-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="6cce3-115">Преобразование одного типа массива в другой расширяющее или сужающее в зависимости от ли расширяющее или сужающее преобразование соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="6cce3-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="6cce3-116">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="6cce3-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="6cce3-117">Преобразование в массив объектов</span><span class="sxs-lookup"><span data-stu-id="6cce3-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="6cce3-118">При объявлении `Object` массив без инициализации, его тип элемента — `Object` до тех пор, пока он не будет инициализирован.</span><span class="sxs-lookup"><span data-stu-id="6cce3-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="6cce3-119">При установке в массив определенного класса, он принимает тип этого класса.</span><span class="sxs-lookup"><span data-stu-id="6cce3-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="6cce3-120">Однако его базовому типу по-прежнему `Object`, и можно позднее задать для него значение массива несвязанного класса.</span><span class="sxs-lookup"><span data-stu-id="6cce3-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="6cce3-121">Поскольку все классы являются производными от `Object`, можно изменить тип элемента массива из любого класса для любого другого класса.</span><span class="sxs-lookup"><span data-stu-id="6cce3-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="6cce3-122">В следующем примере, не существует преобразования между типами `student` и `String`, но оба является производным от `Object`, поэтому все присвоения являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="6cce3-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="6cce3-123">Базовый тип массива</span><span class="sxs-lookup"><span data-stu-id="6cce3-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="6cce3-124">Если изначально объявить массив с определенным классом, что класс является его базовый тип элемента.</span><span class="sxs-lookup"><span data-stu-id="6cce3-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="6cce3-125">Если в дальнейшем массив другого класса, необходимо выполнить преобразование между двумя классами.</span><span class="sxs-lookup"><span data-stu-id="6cce3-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="6cce3-126">В следующем примере `students` — `student` массива.</span><span class="sxs-lookup"><span data-stu-id="6cce3-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="6cce3-127">Так как не существует преобразования между `String` и `student`, последний оператор завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6cce3-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cce3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6cce3-128">See Also</span></span>  
 [<span data-ttu-id="6cce3-129">Типы данных</span><span class="sxs-lookup"><span data-stu-id="6cce3-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="6cce3-130">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cce3-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="6cce3-131">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="6cce3-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="6cce3-132">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="6cce3-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="6cce3-133">Как: преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cce3-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="6cce3-134">Типы данных</span><span class="sxs-lookup"><span data-stu-id="6cce3-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="6cce3-135">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="6cce3-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="6cce3-136">Массивы</span><span class="sxs-lookup"><span data-stu-id="6cce3-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
