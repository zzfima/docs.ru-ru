---
title: Пример отложенного выполнения (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
ms.openlocfilehash: e0bb7f3d125cc48607a534e2c24cbf7083353945
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583321"
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="b607b-102">Пример отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b607b-102">Deferred Execution Example (Visual Basic)</span></span>

<span data-ttu-id="b607b-103">В данном разделе показано влияние отложенного выполнения и отложенного вычисления на запросы LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="b607b-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>

## <a name="example"></a><span data-ttu-id="b607b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b607b-104">Example</span></span>

<span data-ttu-id="b607b-105">В следующем примере демонстрируется порядок выполнения при использовании метода расширения, в котором применяется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="b607b-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="b607b-106">В этом примере объявляется массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="b607b-106">The example declares an array of three strings.</span></span> <span data-ttu-id="b607b-107">Затем в нем производится итерация по коллекции, возвращенной `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="b607b-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module Module1

    <Extension()>
    Private Iterator Function ConvertCollectionToUpperCase(
    ByVal source As IEnumerable(Of String)) _
    As IEnumerable(Of String)
        For Each str As String In source
            Console.WriteLine("ToUpper: source {0}", str)
            Yield str.ToUpper()
        Next
    End Function

    Sub Main()
        Dim stringArray = New String() {"abc", "def", "ghi"}

        Dim q = From str In stringArray.ConvertCollectionToUpperCase()
                Select str

        For Each Str As String In q
            Console.WriteLine("Main: str {0}", Str)
        Next
    End Sub

End Module
```

<span data-ttu-id="b607b-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b607b-108">This example produces the following output:</span></span>

```console
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

<span data-ttu-id="b607b-109">Обратите внимание, что во время итерации по коллекции, возвращенной `ConvertCollectionToUpperCase`, происходит получение каждого элемента из исходного массива строк и преобразование символов в верхний регистр до получения следующего элемента из исходного массива строк.</span><span class="sxs-lookup"><span data-stu-id="b607b-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>

<span data-ttu-id="b607b-110">Видно, что весь массив строк не преобразуется в символы верхнего регистра, пока каждый элемент возвращенной коллекции не будет обработан циклом `foreach` в `Main`.</span><span class="sxs-lookup"><span data-stu-id="b607b-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b607b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b607b-111">See also</span></span>

- [<span data-ttu-id="b607b-112">Учебник. отложенное выполнение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b607b-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
