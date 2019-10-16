---
title: Массивы
description: Узнайте, как создавать и использовать массивы на F# языке программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 8470e01087e417635bcd5c528df9b9e089cbf59f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320493"
---
# <a name="arrays"></a>Массивы

> [!NOTE]
> Ссылка на справочник по API ведет на сайт MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

Массивы — это изменяемые коллекции последовательных элементов данных с фиксированным размером (от нуля), которые имеют один и тот же тип.

## <a name="creating-arrays"></a>Создание массивов

Массивы можно создавать несколькими способами. Можно создать небольшой массив, перечисляя последовательные значения между `[|` и `|]` и разделив их точкой с запятой, как показано в следующих примерах.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

Можно также разместить каждый элемент на отдельной строке, в этом случае разделитель точкой с запятой является необязательным.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

Тип элементов массива выводится из используемых литералов и должен быть единообразным. Следующий код вызывает ошибку, поскольку 1,0 является числом с плавающей запятой и 2, а 3 — целыми числами.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

Для создания массивов также можно использовать выражения последовательности. Ниже приведен пример, создающий массив квадратов целых чисел от 1 до 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

Чтобы создать массив, в котором все элементы инициализируются нулем, используйте `Array.zeroCreate`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a>Доступ к элементам

Доступ к элементам массива можно получить с помощью оператора с точкой (`.`) и квадратных скобок (`[` и `]`).

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

Индексы массива начинаются с 0.

Можно также получить доступ к элементам массива с помощью нотации среза, что позволяет указать поддиапазон массива. Ниже приведены примеры нотаций среза.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

При использовании нотации среза создается новая копия массива.

## <a name="array-types-and-modules"></a>Типы массивов и модули

Тип всех F# массивов является типом .NET Framework <xref:System.Array?displayProperty=nameWithType>. Поэтому F# массивы поддерживают все функциональные возможности, доступные в <xref:System.Array?displayProperty=nameWithType>.

Модуль библиотеки [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) поддерживает операции с одномерным массивами. Модули `Array2D`, `Array3D` и `Array4D` содержат функции, поддерживающие операции с массивами из двух, трех и четырех измерений соответственно. Массивы с рангом, равным четырем, можно создать с помощью <xref:System.Array?displayProperty=nameWithType>.

### <a name="simple-functions"></a>Простые функции

[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Возвращает элемент. [`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) задает длину массива. [`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) задает для элемента указанное значение. В следующем примере кода показано использование этих функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

Выходные данные выглядят следующим образом.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Функции, создающие массивы

Несколько функций создают массивы, не требуя наличия существующего массива. [`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) создает новый массив, который не содержит элементов. [`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) создает массив указанного размера и задает для всех элементов указанные значения. [`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) создает массив с учетом измерения и функции для создания элементов. [`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) создает массив, в котором все элементы инициализируются значением нулевого значения для типа массива. Эти функции показаны в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

Выходные данные выглядят следующим образом.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) создает новый массив, содержащий элементы, скопированные из существующего массива. Обратите внимание, что копия является неполной копией, что означает, что если тип элемента является ссылочным, копируется только ссылка, а не базовый объект. Это показано в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

Результат выполнения приведенного выше кода выглядит следующим образом:

```console
[|Test1; Test2; |]
[|; Test2; |]
```

Строка `Test1` отображается только в первом массиве, так как операция создания нового элемента перезаписывает ссылку в `firstArray`, но не влияет на исходную ссылку на пустую строку, которая все еще присутствует в `secondArray`. Строка `Test2` отображается в обоих массивах, так как операция `Insert` для типа <xref:System.Text.StringBuilder?displayProperty=nameWithType> влияет на базовый объект <xref:System.Text.StringBuilder?displayProperty=nameWithType>, на который имеется ссылка в обоих массивах.

[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) создает новый массив из поддиапазона массива. Укажите поддиапазон, указав начальный индекс и длину. В следующем коде показано использование функции `Array.sub`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

Выходные данные показывают, что подмассив начинается в элементе 5 и содержит 10 элементов.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) создает новый массив, объединяя два существующих массива.

В следующем примере кода демонстрируется **массив. append**.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) выбирает элементы массива для включения в новый массив. Следующий код демонстрирует `Array.choose`. Обратите внимание, что тип элемента массива не обязательно должен совпадать с типом значения, возвращаемого в типе параметра. В этом примере тип элемента — `int`, а параметр — результат функции полинома, `elem*elem - 1` в качестве числа с плавающей запятой.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) выполняет указанную функцию для каждого элемента массива существующего массива, а затем собирает элементы, созданные функцией, и объединяет их в новый массив. Следующий код демонстрирует `Array.collect`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) принимает последовательность массивов и объединяет их в один массив. Следующий код демонстрирует `Array.concat`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) принимает логическую функцию Condition и создает новый массив, содержащий только те элементы из входного массива, для которых условие истинно. Следующий код демонстрирует `Array.filter`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) создает новый массив, переменяя порядок существующего массива на другой. Следующий код демонстрирует `Array.rev`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
"Hello world!"
```

В модуле массива можно легко сочетать функции, которые преобразуют массивы с помощью конвейерного оператора (`|>`), как показано в следующем примере.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

Выходные данные:

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Многомерные массивы

Можно создать многомерный массив, но для записи литерала многомерного массива нет синтаксиса. Используйте оператор [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) , чтобы создать массив из последовательности последовательностей элементов массива. Последовательности могут быть литералами массива или списка. Например, следующий код создает двумерный массив.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

Можно также использовать функцию [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) для инициализации массивов двух измерений, и аналогичные функции доступны для массивов из трех и четырех измерений. Эти функции принимают функцию, которая используется для создания элементов. Чтобы создать двумерный массив, содержащий элементы, для которых задано начальное значение вместо указания функции, используйте функцию [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) , которая также доступна для массивов размером до четырех. В следующем примере кода сначала показано, как создать массив массивов, содержащих нужные элементы, а затем использовать `Array2D.init` для создания нужного двумерного массива.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

Синтаксис индексирования и среза массива поддерживается для массивов вплоть до ранга 4. При указании индекса в нескольких измерениях для разделения индексов используются запятые, как показано в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

Тип двумерного массива записывается как `<type>[,]` (например, `int[,]`, `double[,]`), а тип трехмерного массива записывается как `<type>[,,]` и т. д. для массивов с большими размерами.

Для многомерных массивов также доступен только подмножество функций, доступных для одномерных массивов. Дополнительные сведения см. в разделе [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d)и [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).

### <a name="array-slicing-and-multidimensional-arrays"></a>Создание срезов массива и многомерных массивов

В двухмерном массиве (матрице) можно извлечь подматрицу, указав диапазоны и используя символ шаблона (`*`) для указания целых строк или столбцов.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

Начиная с F# 3,1 можно разбивать многомерный массив на подмассивы того же или более низкого измерения. Например, можно получить вектор из матрицы, указав одну строку или столбец.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

Этот синтаксис среза можно использовать для типов, реализующих операторы доступа к элементам и перегруженные методы `GetSlice`. Например, следующий код создает тип матрицы, который заключает в F# оболочку 2D-массив, реализует свойство Item для обеспечения поддержки индексирования массива и реализует три версии `GetSlice`. Если этот код можно использовать в качестве шаблона для типов матриц, можно использовать все операции по фрагментированию, описанные в этом разделе.

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

### <a name="boolean-functions-on-arrays"></a>Логические функции в массивах

Функции [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) и [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) проверяют элементы либо в одном, либо в двух массивах соответственно. Эти функции принимают тестовую функцию и возвращают `true`, если существует элемент (или пара элементов для `Array.exists2`), удовлетворяющий условию.

В следующем коде демонстрируется использование `Array.exists` и `Array.exists2`. В этих примерах новые функции создаются путем применения только одного из аргументов, в таких случаях аргумент функции.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

Результат приведенного выше кода выглядит следующим образом.

```console
true
false
false
true
```

Аналогичным образом функция [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) проверяет массив, чтобы определить, удовлетворяет ли каждый элемент логическому условию. Вариант [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) выполняет одно и то же действие с помощью логической функции, включающей элементы двух массивов с одинаковой длиной. В следующем коде показано использование этих функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

Выходные данные для этих примеров выглядят следующим образом.

```console
false
true
true
false
```

### <a name="searching-arrays"></a>Поиск массивов

[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) принимает логическую функцию и возвращает первый элемент, для которого функция возвращает `true`, или вызывает <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType>, если не найдено ни одного элемента, удовлетворяющего условию. [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) аналогичен `Array.find`, за исключением того, что он возвращает индекс элемента, а не сам элемент.

В следующем коде используется `Array.find` и `Array.findIndex`, чтобы узнать число, которое является как идеальным квадратом, так и идеальным кубом.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

Выходные данные выглядят следующим образом.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) аналогичен `Array.find`, за исключением того, что его результат является типом параметра и возвращает `None`, если элемент не найден. `Array.tryFind` следует использовать вместо `Array.find`, если неизвестно, находится ли соответствующий элемент в массиве. Аналогичным образом [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) аналогичен [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) , за исключением того, что тип параметра является возвращаемым значением. Если элемент не найден, параметр имеет значение `None`.

В следующем коде показано использование функции `Array.tryFind`. Этот код зависит от предыдущего кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

Выходные данные выглядят следующим образом.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

Используйте [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) , если необходимо преобразовать элемент в дополнение к его поиску. Результатом является первый элемент, для которого функция возвращает преобразованный элемент в виде значения параметра, или значение `None`, если такой элемент не найден.

В следующем коде показано использование `Array.tryPick`. В этом случае вместо лямбда-выражения для упрощения кода определены несколько локальных вспомогательных функций.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

Выходные данные выглядят следующим образом.

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="performing-computations-on-arrays"></a>Выполнение вычислений с массивами

Функция [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) Возвращает среднее значение каждого элемента в массиве. Ограничены типами элементов, которые поддерживают точное деление на целое число, которое включает типы с плавающей запятой, но не целочисленные типы. Функция [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) Возвращает среднее значение результатов вызова функции для каждого элемента. Для массива целочисленного типа можно использовать `Array.averageBy`, чтобы функция могла преобразовать каждый элемент в тип с плавающей запятой для вычисления.

Используйте [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) или [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) , чтобы получить максимальный или минимальный элемент, если тип элемента поддерживает его. Аналогичным образом [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) и [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) позволяют сначала выполнить функцию, возможно, для преобразования в тип, поддерживающий сравнение.

[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) добавляет элементы массива, а [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) вызывает функцию для каждого элемента и добавляет результаты вместе.

Чтобы выполнить функцию для каждого элемента в массиве без сохранения возвращаемых значений, используйте [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516). Для функции, включающей два массива одинаковой длины, используйте [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc). Если необходимо также удержать массив результатов функции, используйте [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) или [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), который работает с двумя массивами за раз.

Варианты [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) и [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) позволяют использовать индекс элемента в вычислениях; то же самое относится к [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) и [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).

Функции [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0)и [1](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) выполняют алгоритмы выполнения, использующие все элементы массива. Аналогичным образом, варианты [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) и [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) выполняют вычисления с двумя массивами.

Эти функции для выполнения вычислений соответствуют функциям с одинаковыми именами в [модуле List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788). Примеры использования см. в разделе [списки](lists.md).

### <a name="modifying-arrays"></a>Изменение массивов

[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) задает для элемента указанное значение. [`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) задает указанное значение для диапазона элементов в массиве. В следующем коде приведен пример `Array.fill`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

Выходные данные выглядят следующим образом.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Для копирования подраздела одного массива в другой массив можно использовать [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) .

### <a name="converting-to-and-from-other-types"></a>Преобразование в другие типы и из них

[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) создает массив из списка. [`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) создает массив из последовательности. [`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) и [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) преобразуют в другие типы коллекций из типа массива.

### <a name="sorting-arrays"></a>Сортировка массивов

Используйте [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) для сортировки массива с помощью универсальной функции сравнения. Используйте [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) , чтобы указать функцию, которая создает значение, называемое *ключом*, для сортировки с помощью универсальной функции сравнения для ключа. Если вы хотите предоставить пользовательскую функцию сравнения, используйте [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) . `Array.sort`, `Array.sortBy` и `Array.sortWith` все возвращают отсортированный массив как новый массив. Варианты [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f)и [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) изменяют существующий массив вместо того, чтобы возвращать новый.

### <a name="arrays-and-tuples"></a>Массивы и кортежи

Функции [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) и [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) преобразуют массивы пар кортежей в кортежи массивов и наоборот. [`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) и [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) похожи, за исключением того, что они работают с кортежами трех элементов или кортежей из трех массивов.

## <a name="parallel-computations-on-arrays"></a>Параллельные вычисления на массивах

Модуль [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) содержит функции для выполнения параллельных вычислений с массивами. Этот модуль недоступен в приложениях, предназначенных для версий .NET Framework до версии 4.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Типы языка F#](fsharp-types.md)
