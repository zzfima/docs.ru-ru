---
title: "Пример отложенного выполнения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a4d2146901d9282b0df706b483afef79f714f660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="73898-102">Пример отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73898-102">Deferred Execution Example (Visual Basic)</span></span>
<span data-ttu-id="73898-103">В данном разделе показано влияние отложенного выполнения и отложенного вычисления на запросы LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="73898-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73898-104">Пример</span><span class="sxs-lookup"><span data-stu-id="73898-104">Example</span></span>  
 <span data-ttu-id="73898-105">В следующем примере демонстрируется порядок выполнения при использовании метода расширения, в котором применяется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="73898-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="73898-106">В этом примере объявляется массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="73898-106">The example declares an array of three strings.</span></span> <span data-ttu-id="73898-107">Затем в нем производится итерация по коллекции, возвращенной `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="73898-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
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
  
 <span data-ttu-id="73898-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="73898-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="73898-109">Обратите внимание, что во время итерации по коллекции, возвращенной `ConvertCollectionToUpperCase`, происходит получение каждого элемента из исходного массива строк и преобразование символов в верхний регистр до получения следующего элемента из исходного массива строк.</span><span class="sxs-lookup"><span data-stu-id="73898-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="73898-110">Видно, что весь массив строк не преобразуется в символы верхнего регистра, пока каждый элемент возвращенной коллекции не будет обработан циклом `foreach` в `Main`.</span><span class="sxs-lookup"><span data-stu-id="73898-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73898-111">См. также</span><span class="sxs-lookup"><span data-stu-id="73898-111">See Also</span></span>  
 [<span data-ttu-id="73898-112">Учебник: Отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73898-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
