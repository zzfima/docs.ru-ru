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
ms.openlocfilehash: f24c0625058dbd960411d5981b4e98e0e9422b99
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="eceb6-102">Практическое руководство. Сортировка массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eceb6-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="eceb6-103">В этом примере объявляется массив `String` объектов с именем `zooAnimals`, заполняет ее и сортируется по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="eceb6-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eceb6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="eceb6-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eceb6-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="eceb6-105">Compiling the Code</span></span>  
 <span data-ttu-id="eceb6-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="eceb6-106">This example requires:</span></span>  
  
-   <span data-ttu-id="eceb6-107">Доступ к библиотеке Mscorlib.dll и <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="eceb6-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="eceb6-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="eceb6-108">Robust Programming</span></span>  
 <span data-ttu-id="eceb6-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="eceb6-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="eceb6-110">Массив является пустым (<xref:System.ArgumentNullException> класс)</span><span class="sxs-lookup"><span data-stu-id="eceb6-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="eceb6-111">Массив является многомерным (<xref:System.RankException> класс)</span><span class="sxs-lookup"><span data-stu-id="eceb6-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="eceb6-112">Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейса (<xref:System.InvalidOperationException> класс)</span><span class="sxs-lookup"><span data-stu-id="eceb6-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eceb6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eceb6-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="eceb6-114">Массивы</span><span class="sxs-lookup"><span data-stu-id="eceb6-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="eceb6-115">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="eceb6-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="eceb6-116">Коллекции</span><span class="sxs-lookup"><span data-stu-id="eceb6-116">Collections</span></span>](../../concepts/collections.md)  
 [<span data-ttu-id="eceb6-117">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="eceb6-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
