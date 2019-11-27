---
title: Преобразования массивов
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345863"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="78e43-102">Преобразование массивов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78e43-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="78e43-103">Тип массива можно преобразовать в другой тип массива при условии соблюдения следующих условий.</span><span class="sxs-lookup"><span data-stu-id="78e43-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="78e43-104">**Равный ранг.**</span><span class="sxs-lookup"><span data-stu-id="78e43-104">**Equal Rank.**</span></span> <span data-ttu-id="78e43-105">Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое количество измерений.</span><span class="sxs-lookup"><span data-stu-id="78e43-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="78e43-106">Однако длины соответствующих измерений не обязательно должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="78e43-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="78e43-107">**Тип данных элемента.**</span><span class="sxs-lookup"><span data-stu-id="78e43-107">**Element Data Type.**</span></span> <span data-ttu-id="78e43-108">Типы данных элементов обоих массивов должны быть ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="78e43-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="78e43-109">Невозможно преобразовать массив `Integer` в массив `Long` или даже в массив `Object`, так как задействован хотя бы один тип значений.</span><span class="sxs-lookup"><span data-stu-id="78e43-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="78e43-110">Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="78e43-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="78e43-111">**Вариантное.**</span><span class="sxs-lookup"><span data-stu-id="78e43-111">**Convertibility.**</span></span> <span data-ttu-id="78e43-112">Преобразование (расширяющее или сужение) должно быть возможным между типами элементов двух массивов.</span><span class="sxs-lookup"><span data-stu-id="78e43-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="78e43-113">Пример, в котором не выполняется это требование — попытка преобразования между `String` массивом и массивом класса, производного от <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78e43-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="78e43-114">Эти два типа не имеют ничего общего, и между ними не существует каких либо преобразований.</span><span class="sxs-lookup"><span data-stu-id="78e43-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="78e43-115">Преобразование одного типа массива в другой может расширяться или уменьшаться в зависимости от того, является ли преобразование соответствующих элементов расширяющим или узким.</span><span class="sxs-lookup"><span data-stu-id="78e43-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="78e43-116">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="78e43-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="78e43-117">Преобразование в массив объектов</span><span class="sxs-lookup"><span data-stu-id="78e43-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="78e43-118">При объявлении массива `Object` без инициализации его тип элемента `Object`, пока он остается неинициализированным.</span><span class="sxs-lookup"><span data-stu-id="78e43-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="78e43-119">При присвоении значения массиву определенного класса он принимает тип этого класса.</span><span class="sxs-lookup"><span data-stu-id="78e43-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="78e43-120">Однако его базовый тип по-прежнему `Object`, и впоследствии его можно установить в другой массив несвязанного класса.</span><span class="sxs-lookup"><span data-stu-id="78e43-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="78e43-121">Поскольку все классы являются производными от `Object`, можно изменить тип элемента массива с любого класса на любой другой класс.</span><span class="sxs-lookup"><span data-stu-id="78e43-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="78e43-122">В следующем примере преобразование между типами `student` и `String`не существует, но оба типа являются производными от `Object`, поэтому все назначения являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="78e43-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="78e43-123">Базовый тип массива</span><span class="sxs-lookup"><span data-stu-id="78e43-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="78e43-124">Если изначально был объявлен массив с конкретным классом, его базовым типом элемента является этот класс.</span><span class="sxs-lookup"><span data-stu-id="78e43-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="78e43-125">Если впоследствии задать для него массив другого класса, необходимо выполнить преобразование между двумя классами.</span><span class="sxs-lookup"><span data-stu-id="78e43-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="78e43-126">В следующем примере `students` является массивом `student`.</span><span class="sxs-lookup"><span data-stu-id="78e43-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="78e43-127">Поскольку преобразование между `String` и `student`не существует, последняя инструкция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="78e43-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="78e43-128">См. также</span><span class="sxs-lookup"><span data-stu-id="78e43-128">See also</span></span>

- [<span data-ttu-id="78e43-129">Типы данных</span><span class="sxs-lookup"><span data-stu-id="78e43-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="78e43-130">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78e43-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="78e43-131">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="78e43-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="78e43-132">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="78e43-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="78e43-133">Как преобразовать объект в другой тип в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78e43-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="78e43-134">Типы данных</span><span class="sxs-lookup"><span data-stu-id="78e43-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="78e43-135">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="78e43-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="78e43-136">Массивы</span><span class="sxs-lookup"><span data-stu-id="78e43-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
