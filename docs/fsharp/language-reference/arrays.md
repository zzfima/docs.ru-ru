---
title: Массивы (F#)
description: 'Узнайте, как создать и использовать массивы в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 27b73efc900ac2efc813fe66f81baa2e9ae1e843
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46007352"
---
# <a name="arrays"></a><span data-ttu-id="5b5d8-103">Массивы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-103">Arrays</span></span>

> [!NOTE]
<span data-ttu-id="5b5d8-104">Ссылка на справочник по API ведет на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="5b5d8-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="5b5d8-106">Массивы являются фиксированного размера, начинающийся с нуля, изменяемые коллекции элементов данных, имеющих тот же тип.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="5b5d8-107">Создание массивов</span><span class="sxs-lookup"><span data-stu-id="5b5d8-107">Creating Arrays</span></span>

<span data-ttu-id="5b5d8-108">Массивы можно создавать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-108">You can create arrays in several ways.</span></span> <span data-ttu-id="5b5d8-109">Небольшой массив можно создать, указав последовательные значения между `[|` и `|]` и разделяются точкой с запятой, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="5b5d8-110">Можно также указать каждый элемент в отдельной строке, в котором регистр точку с запятой является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="5b5d8-111">Тип элементов массива определяется по указанным литералам и должны быть согласованы.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="5b5d8-112">Следующий код вызывает ошибку, поскольку 1.0 — это значение с плавающей запятой, а 2 и 3 — целые числа.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="5b5d8-113">Можно также использовать выражения последовательности для создания массивов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="5b5d8-114">Ниже приведен пример, в котором создается массив квадратов целых чисел от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="5b5d8-115">Для создания массива, в которой все элементы инициализируются значением 0, используйте `Array.zeroCreate`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="5b5d8-116">Доступ к элементам</span><span class="sxs-lookup"><span data-stu-id="5b5d8-116">Accessing Elements</span></span>

<span data-ttu-id="5b5d8-117">Доступа к элементам массива, используя оператор точки (`.`) и квадратные скобки (`[` и `]`).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="5b5d8-118">Индексы массивов начинаются с 0.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-118">Array indexes start at 0.</span></span>

<span data-ttu-id="5b5d8-119">Для доступа к элементам массива можно также с помощью диапазонного представления, который позволяет указать поддиапазон массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="5b5d8-120">Примеры диапазонного представления.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="5b5d8-121">При использовании диапазонного представления создается новая копия массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="5b5d8-122">Типы массивов и модули</span><span class="sxs-lookup"><span data-stu-id="5b5d8-122">Array Types and Modules</span></span>

<span data-ttu-id="5b5d8-123">Тип всех массивов F # является типом .NET Framework <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5b5d8-124">Поэтому массивы в F # поддерживают все функциональные возможности, доступные в <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5b5d8-125">Модуль библиотеки [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) поддерживает операции над одномерными массивами.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="5b5d8-126">Модули `Array2D`, `Array3D`, и `Array4D` содержат функции, поддерживающие операции над массивами двух, трех и четырех измерений, соответственно.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="5b5d8-127">Можно создать массивы с размерностью более 4 с помощью <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="5b5d8-128">Простые функции</span><span class="sxs-lookup"><span data-stu-id="5b5d8-128">Simple Functions</span></span>

<span data-ttu-id="5b5d8-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Возвращает элемент.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="5b5d8-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) Возвращает длину массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="5b5d8-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Задает элемент с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="5b5d8-132">В следующем примере кода показано использование этих функций.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="5b5d8-133">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-133">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="5b5d8-134">Функции, создающие массивы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-134">Functions That Create Arrays</span></span>

<span data-ttu-id="5b5d8-135">Несколько функций создают массивы, не требуя существующего массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="5b5d8-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) Создает новый массив, который не содержит какие-либо элементы.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="5b5d8-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) Создает массив указанного размера и задает для всех элементов указанные значения.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="5b5d8-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) Создает массив заданного размера, функция для создания элементов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="5b5d8-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) Создает массив, в котором все элементы в нулевое значение для типа массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="5b5d8-140">Следующий код демонстрирует эти функции.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="5b5d8-141">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-141">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="5b5d8-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) Создает новый массив, содержащий элементы, скопированные из существующего массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="5b5d8-143">Обратите внимание, что копия является неполной, это означает, что если тип элемента является ссылочным типом, копируется только ссылка, не базовый объект.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="5b5d8-144">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="5b5d8-145">Выходные данные приведенного выше кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b5d8-145">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="5b5d8-146">Строка `Test1` отображается только в первом массиве, так как операция создания нового элемента перезаписывает ссылку в `firstArray` , но не влияет на исходную ссылку на пустую строку, которая по-прежнему присутствует в `secondArray`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="5b5d8-147">Строка `Test2` отображается в обоих массивах, так как `Insert` операции на <xref:System.Text.StringBuilder?displayProperty=nameWithType> тип влияет на базовый <xref:System.Text.StringBuilder?displayProperty=nameWithType> объект, который упоминается в обоих массивах.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="5b5d8-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) Создает новый массив из массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="5b5d8-149">Поддиапазон задается указанием начального индекса и длины.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="5b5d8-150">В следующем коде показано использование функции `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="5b5d8-151">Выходные данные показывают, что подмассив начинается с элемента 5 и содержит 10 элементов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
<span data-ttu-id="5b5d8-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) Создает новый массив, объединяя два существующих массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="5b5d8-153">В следующем коде показано **Array.append**.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="5b5d8-154">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-154">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="5b5d8-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) выбирает элементы массива, включаемых в новый массив.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="5b5d8-156">В следующем коде показано `Array.choose`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="5b5d8-157">Обратите внимание, что тип элемента массива в соответствии с типом значения, возвращаемого в типе option.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="5b5d8-158">В этом примере тип элемента — это `int` и option является результатом выполнения полиномиальной функции `elem*elem - 1`, как число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="5b5d8-159">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-159">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="5b5d8-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) применяет указанную функцию к каждому элементу существующего массива и затем собирает элементы, созданные этой функцией и объединяет их в новый массив.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="5b5d8-161">В следующем коде показано `Array.collect`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="5b5d8-162">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-162">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="5b5d8-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) принимает последовательность массивов и объединяет их в один массив.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="5b5d8-164">В следующем коде показано `Array.concat`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="5b5d8-165">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-165">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="5b5d8-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) принимает функцию логического условия и создает новый массив, содержащий только те элементы входного массива, для которого условие имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="5b5d8-167">В следующем коде показано `Array.filter`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="5b5d8-168">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-168">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="5b5d8-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) Создает новый массив, изменяя порядок элементов существующего массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="5b5d8-170">В следующем коде показано `Array.rev`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

<span data-ttu-id="5b5d8-171">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-171">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="5b5d8-172">Его можно легко объединить функции модуля array, преобразующие массивы, с помощью оператора конвейера (`|>`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="5b5d8-173">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="5b5d8-173">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="5b5d8-174">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-174">Multidimensional Arrays</span></span>

<span data-ttu-id="5b5d8-175">Многомерный массив можно создать, но не существует синтаксис для написания литералов таких массивов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="5b5d8-176">Используйте оператор [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) для создания массива из последовательности последовательностей элементов массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="5b5d8-177">Последовательности могут быть литералами массивов или списков.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="5b5d8-178">Например следующий код создает двумерный массив.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="5b5d8-179">Можно также использовать функцию [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) инициализации массивов двух измерений и аналогичные функции доступны для массивов тремя и четырьмя измерений.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="5b5d8-180">Эти функции принимают функцию, которая используется для создания элементов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="5b5d8-181">Чтобы создать двумерный массив, содержащий элементы, задать начальное значение вместо функции, используйте [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) функцию, которая также доступна для массивов размерностью вплоть до 4.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="5b5d8-182">В следующем примере кода показано создание массива массивов с нужными элементами, а затем использует `Array2D.init` создание нужного двумерного массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="5b5d8-183">Массив, индексирования и указания диапазонов синтаксис поддерживается для массивов не выше 4 ранга.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="5b5d8-184">При указании индекса в нескольких измерениях, как показано в следующем примере кода вы используйте запятые для разделения индексов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="5b5d8-185">Тип двумерного массива обозначается как `<type>[,]` (например, `int[,]`, `double[,]`), и тип трехмерного массива записывается как `<type>[,,]`, и так далее для многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="5b5d8-186">Только подмножество функций, предусмотренных для одномерных также доступна для многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="5b5d8-187">Дополнительные сведения см. в разделе [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), и [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="5b5d8-188">Указание диапазонов массивов и многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="5b5d8-189">В двумерном массиве (матрице), можно извлечь подматрицу, указав диапазоны и используя подстановочный знак (`*`) символ для задания целых строк или столбцов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
/ Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="5b5d8-190">Что касается F # 3.1 можно разложить многомерный массив на подмассивы с тем же или более низким измерением.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="5b5d8-191">Например можно получить вектор из матрицы, указав одну строку или столбец.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="5b5d8-192">Можно использовать это многоуровневый синтаксис для типов, реализующих операторы доступа к элементам и перегруженные `GetSlice` методы.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="5b5d8-193">Например, следующий код создает тип Matrix, который создает оболочку для двумерного массива F #, реализует свойство Item для обеспечения поддержки индексации массива, а также реализует три версии `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="5b5d8-194">Если этот код можно использовать в качестве шаблона для матричных типов, можно использовать все операции указания диапазонов, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart = 
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart = 
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish = 
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart = 
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish = 
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart = 
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish = 
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="5b5d8-195">Логические функции для массивов</span><span class="sxs-lookup"><span data-stu-id="5b5d8-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="5b5d8-196">Функции [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) и [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) проверяют элементы в одной или двух массивов, соответственно.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="5b5d8-197">Эти функции принимают функцию проверки и возвращают `true` Если имеется элемент (или любая из пар элементов `Array.exists2`) отвечает условию.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="5b5d8-198">В следующем коде показано использование `Array.exists` и `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="5b5d8-199">В этих примерах новые функции создаются путем использования только одного из аргументов, в этом случае аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="5b5d8-200">Выходные данные приведенного выше кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-200">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="5b5d8-201">Аналогичным образом, функция [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) проверяет массив, чтобы определить, удовлетворяет ли каждый элемент является логическое условие.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="5b5d8-202">Вариант [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) делает то же самое с помощью логической функции, принимающей элементы двух массивов одинаковой длины.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="5b5d8-203">Следующий код иллюстрирует использование этих функций.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="5b5d8-204">Выходные данные для этих примеров выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-204">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="5b5d8-205">Поиск в массивах</span><span class="sxs-lookup"><span data-stu-id="5b5d8-205">Searching Arrays</span></span>

<span data-ttu-id="5b5d8-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) принимает логическую функцию и возвращает первый элемент, для которого функция возвращает `true`, или вызывает <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> Если найден элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="5b5d8-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) Подобно `Array.find`, за исключением того, что она возвращает индекс элемента, а не сам элемент.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="5b5d8-208">В следующем коде используется `Array.find` и `Array.findIndex` для поиска числа, которое является точным квадратом и точным кубом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="5b5d8-209">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-209">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="5b5d8-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) Подобно `Array.find`, за исключением того, что ее результат имеет тип option, и возвращает `None` Если элемент не найден.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="5b5d8-211">`Array.tryFind` следует использовать вместо `Array.find` Если вы не знаете ли соответствующий элемент в массиве.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="5b5d8-212">Аналогичным образом [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) аналогичен [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) за исключением того, что тип параметра является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="5b5d8-213">Если элемент не найден, параметр — `None`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="5b5d8-214">В следующем коде показано использование функции `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="5b5d8-215">Этот код зависит от предыдущего кода.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="5b5d8-216">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-216">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="5b5d8-217">Используйте [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) при необходимости преобразования элемент, но его.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="5b5d8-218">Результат является первым элементом, для которого функция возвращает преобразованный элемент как значение параметра или `None` Если такой элемент не найден.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="5b5d8-219">В следующем коде показано использование `Array.tryPick`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="5b5d8-220">В этом случае вместо лямбда-выражение, для упрощения кода определяются несколько локальных вспомогательных функций.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="5b5d8-221">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-221">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="5b5d8-222">Вычисления с массивами</span><span class="sxs-lookup"><span data-stu-id="5b5d8-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="5b5d8-223">[ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) Функция возвращает среднее значение каждого элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="5b5d8-224">Она ограничена типами элементов, поддерживающими точное деление на целое число, включая типы с плавающей запятой, но не целочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="5b5d8-225">[ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) Функция возвращает среднее значение результатов вызова функции для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="5b5d8-226">Массив целочисленных типов, можно использовать `Array.averageBy` и с помощью функции преобразовать каждый элемент в число с плавающей запятой для вычисления.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="5b5d8-227">Используйте [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) или [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) получить максимальный и минимальный элемент, если ее поддерживает тип элемента.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="5b5d8-228">Аналогичным образом [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) и [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) разрешить функцию выполняться в первую очередь, например для преобразования в тип, поддерживающий сравнение.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="5b5d8-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) Добавляет элементы массива, и [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) вызывает функцию для каждого элемента и складывает результаты.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="5b5d8-230">Чтобы выполнить функцию для каждого элемента массива без сохранения возвращаемого значения, используйте [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="5b5d8-231">Функция, двумя массивами одинаковой длины, [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="5b5d8-232">Если необходимо также сохранить массив результатов функции, используйте [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) или [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), которая работает одновременно два массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="5b5d8-233">Варианты [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) и [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) индекс элемента, который участвует в вычислении; в то же самое касается [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) и [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="5b5d8-234">Функции [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), и [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) выполняют алгоритмы, работающие со всеми элементами массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="5b5d8-235">Аналогичным образом функции [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) и [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) выполнения вычислений над двумя массивами.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="5b5d8-236">Эти функции для выполнения вычислений соответствуют функциям с тем же именем в [модуль списка](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="5b5d8-237">Примеры использования см. в разделе [перечислены](lists.md).</span><span class="sxs-lookup"><span data-stu-id="5b5d8-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="5b5d8-238">Изменение массивов</span><span class="sxs-lookup"><span data-stu-id="5b5d8-238">Modifying Arrays</span></span>

<span data-ttu-id="5b5d8-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Задает элемент с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="5b5d8-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) Задает диапазон элементов массива заданным значением.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="5b5d8-241">Приведенный ниже пример `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="5b5d8-242">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-242">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="5b5d8-243">Можно использовать [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) можно скопировать часть массива в другой массив.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="5b5d8-244">Преобразование в другие типы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-244">Converting to and from Other Types</span></span>

<span data-ttu-id="5b5d8-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) Создает массив из списка.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="5b5d8-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) Создает массив из последовательности.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="5b5d8-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) и [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) преобразовать в типы этих других коллекций из типа массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="5b5d8-248">Сортировка массивов</span><span class="sxs-lookup"><span data-stu-id="5b5d8-248">Sorting Arrays</span></span>

<span data-ttu-id="5b5d8-249">Используйте [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) для сортировки массива с помощью универсальной функции сравнения.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="5b5d8-250">Используйте [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) для указания функция, которая создает значение, называется *ключ*, для сортировки с помощью универсальной функции сравнения по ключу.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="5b5d8-251">Используйте [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) Если вы хотите предоставить пользовательскую функцию сравнения.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="5b5d8-252">`Array.sort`, `Array.sortBy`, и `Array.sortWith` возвращают упорядоченный массив в виде нового массива.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="5b5d8-253">Варианты [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), и [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) изменить существующий массив вместо возвращения нового.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="5b5d8-254">Массивы и кортежи</span><span class="sxs-lookup"><span data-stu-id="5b5d8-254">Arrays and Tuples</span></span>

<span data-ttu-id="5b5d8-255">Функции [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) и [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) преобразуют массивы пар кортежей в кортежи массивов и наоборот.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="5b5d8-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) и [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) похожи, за исключением того, что они работают с кортежей из трех элементов или трех массивов.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="5b5d8-257">Параллельные вычисления с массивами</span><span class="sxs-lookup"><span data-stu-id="5b5d8-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="5b5d8-258">Модуль [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) содержит функции для выполнения параллельных вычислений с массивами.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="5b5d8-259">Этот модуль не доступен для приложений, предназначенных для версий платформы .NET Framework, предшествующих версии 4.</span><span class="sxs-lookup"><span data-stu-id="5b5d8-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b5d8-260">См. также</span><span class="sxs-lookup"><span data-stu-id="5b5d8-260">See also</span></span>

- [<span data-ttu-id="5b5d8-261">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="5b5d8-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5b5d8-262">F #; Типы</span><span class="sxs-lookup"><span data-stu-id="5b5d8-262">F#; Types</span></span>](fsharp-types.md)
