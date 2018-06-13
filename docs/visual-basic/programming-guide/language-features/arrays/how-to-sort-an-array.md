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
ms.locfileid: "33646318"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Практическое руководство. Сортировка массива в Visual Basic
В этом примере объявляется массив `String` объектов с именем `zooAnimals`, заполняет ее и сортируется по алфавиту.  
  
## <a name="example"></a>Пример  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Доступ к библиотеке Mscorlib.dll и <xref:System> пространства имен.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Массив является пустым (<xref:System.ArgumentNullException> класс)  
  
-   Массив является многомерным (<xref:System.RankException> класс)  
  
-   Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейса (<xref:System.InvalidOperationException> класс)  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Устранение неполадок, связанных с массивами](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Коллекции](../../concepts/collections.md)  
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
