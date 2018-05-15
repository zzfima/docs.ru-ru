---
title: Практическое руководство. Сортировка массива в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: a067c40e1dd0e881516cbc7769cb9afb879d1b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="eab13-102">Практическое руководство. Сортировка массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eab13-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="eab13-103">В этом примере объявляется массив `String` объектов с именем `zooAnimals`, заполняет ее и сортируется по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="eab13-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eab13-104">Пример</span><span class="sxs-lookup"><span data-stu-id="eab13-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eab13-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="eab13-105">Compiling the Code</span></span>  
 <span data-ttu-id="eab13-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="eab13-106">This example requires:</span></span>  
  
-   <span data-ttu-id="eab13-107">Доступ к библиотеке Mscorlib.dll и <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="eab13-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="eab13-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="eab13-108">Robust Programming</span></span>  
 <span data-ttu-id="eab13-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="eab13-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="eab13-110">Массив является пустым (<xref:System.ArgumentNullException> класс)</span><span class="sxs-lookup"><span data-stu-id="eab13-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="eab13-111">Массив является многомерным (<xref:System.RankException> класс)</span><span class="sxs-lookup"><span data-stu-id="eab13-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="eab13-112">Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейса (<xref:System.InvalidOperationException> класс)</span><span class="sxs-lookup"><span data-stu-id="eab13-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab13-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eab13-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="eab13-114">Массивы</span><span class="sxs-lookup"><span data-stu-id="eab13-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="eab13-115">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="eab13-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="eab13-116">Коллекции</span><span class="sxs-lookup"><span data-stu-id="eab13-116">Collections</span></span>](../../concepts/collections.md)  
 [<span data-ttu-id="eab13-117">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="eab13-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
