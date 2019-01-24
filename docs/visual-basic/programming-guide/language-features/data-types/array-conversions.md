---
title: Преобразование массивов (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 4170ca53252fef3afda026393300e34b99e9d018
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583088"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="4dc50-102">Преобразование массивов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dc50-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="4dc50-103">Тип массива можно преобразовать в другой тип массива при соблюдении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="4dc50-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="4dc50-104">**Равенство ранга.**</span><span class="sxs-lookup"><span data-stu-id="4dc50-104">**Equal Rank.**</span></span> <span data-ttu-id="4dc50-105">Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое количество измерений.</span><span class="sxs-lookup"><span data-stu-id="4dc50-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="4dc50-106">Однако длины соответствующих измерений не обязательно должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="4dc50-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="4dc50-107">**Тип данных элемента.**</span><span class="sxs-lookup"><span data-stu-id="4dc50-107">**Element Data Type.**</span></span> <span data-ttu-id="4dc50-108">Типы данных элементов обоих массивов должны быть ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="4dc50-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="4dc50-109">Не удается преобразовать `Integer` массив `Long` или даже для `Object` массива, так как тип по крайней мере одно значение.</span><span class="sxs-lookup"><span data-stu-id="4dc50-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="4dc50-110">Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="4dc50-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="4dc50-111">**Возможность преобразования.**</span><span class="sxs-lookup"><span data-stu-id="4dc50-111">**Convertibility.**</span></span> <span data-ttu-id="4dc50-112">Расширяющее или сужающее преобразование должно быть возможно между типами элементов двух массивов.</span><span class="sxs-lookup"><span data-stu-id="4dc50-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="4dc50-113">Например, не соответствует этим требованиям, попытка преобразования между `String` массива, а также массив класс производным от <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4dc50-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4dc50-114">Эти два типа не имеют ничего общего и преобразование любого типа не существует между ними.</span><span class="sxs-lookup"><span data-stu-id="4dc50-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="4dc50-115">Это преобразование одного типа массива в другой расширяющего или сужающего в зависимости от ли расширяющее или сужающее преобразование соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="4dc50-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="4dc50-116">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="4dc50-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="4dc50-117">Преобразование в массив объектов</span><span class="sxs-lookup"><span data-stu-id="4dc50-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="4dc50-118">При объявлении `Object` массива без инициализации, его тип элемента — `Object` до тех пор, пока он не будет инициализирован.</span><span class="sxs-lookup"><span data-stu-id="4dc50-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="4dc50-119">При установке его на массив определенного класса, он принимает тип этого класса.</span><span class="sxs-lookup"><span data-stu-id="4dc50-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="4dc50-120">Тем не менее, его базовым типом является по-прежнему `Object`, и можно впоследствии разместить его в другой массив несвязанного класса.</span><span class="sxs-lookup"><span data-stu-id="4dc50-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="4dc50-121">Так как все классы являются производными от `Object`, можно изменить тип элемента массива из любого класса к любому другому классу.</span><span class="sxs-lookup"><span data-stu-id="4dc50-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="4dc50-122">В следующем примере, не существует преобразования между типами `student` и `String`, но оба являются производными от `Object`, поэтому все назначения являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="4dc50-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
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
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="4dc50-123">Базовый тип массива</span><span class="sxs-lookup"><span data-stu-id="4dc50-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="4dc50-124">Если изначально объявляется массив с определенным классом, его базовый тип элемента является этот класс.</span><span class="sxs-lookup"><span data-stu-id="4dc50-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="4dc50-125">Если в дальнейшем массив другого класса, необходимо выполнить преобразование между двумя классами.</span><span class="sxs-lookup"><span data-stu-id="4dc50-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="4dc50-126">В следующем примере `students` является `student` массива.</span><span class="sxs-lookup"><span data-stu-id="4dc50-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="4dc50-127">Так как не существует преобразования между `String` и `student`, последняя инструкция завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="4dc50-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="4dc50-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4dc50-128">See also</span></span>
- [<span data-ttu-id="4dc50-129">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4dc50-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="4dc50-130">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4dc50-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="4dc50-131">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="4dc50-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="4dc50-132">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="4dc50-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="4dc50-133">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4dc50-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="4dc50-134">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4dc50-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4dc50-135">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="4dc50-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="4dc50-136">Массивы</span><span class="sxs-lookup"><span data-stu-id="4dc50-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
