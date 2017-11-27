---
title: "Практическое руководство. Сортировка массива в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 310c2dacb384de49c80073840c6c58d37f3937d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="7527b-102">Практическое руководство. Сортировка массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7527b-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="7527b-103">В этом примере объявляется массив `String` объектов с именем `zooAnimals`, заполняет ее и сортируется по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="7527b-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7527b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7527b-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7527b-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7527b-105">Compiling the Code</span></span>  
 <span data-ttu-id="7527b-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7527b-106">This example requires:</span></span>  
  
-   <span data-ttu-id="7527b-107">Доступ к библиотеке Mscorlib.dll и <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7527b-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7527b-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="7527b-108">Robust Programming</span></span>  
 <span data-ttu-id="7527b-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="7527b-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7527b-110">Массив является пустым (<xref:System.ArgumentNullException> класс)</span><span class="sxs-lookup"><span data-stu-id="7527b-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="7527b-111">Массив является многомерным (<xref:System.RankException> класс)</span><span class="sxs-lookup"><span data-stu-id="7527b-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="7527b-112">Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейса (<xref:System.InvalidOperationException> класс)</span><span class="sxs-lookup"><span data-stu-id="7527b-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7527b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7527b-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7527b-114">Массивы</span><span class="sxs-lookup"><span data-stu-id="7527b-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="7527b-115">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="7527b-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="7527b-116">Коллекции</span><span class="sxs-lookup"><span data-stu-id="7527b-116">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [<span data-ttu-id="7527b-117">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="7527b-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
