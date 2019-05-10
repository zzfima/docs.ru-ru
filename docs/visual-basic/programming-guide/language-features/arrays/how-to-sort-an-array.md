---
title: Практическое руководство. Сортировка массива в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3c701d1b65d31315ba931cca729e465ba7d766b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620873"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Практическое руководство. Сортировка массива в Visual Basic
В этом примере объявляется массив `String` объектов с именем `zooAnimals`, заполняет его и сортировка по алфавиту.  
  
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
  
- Доступ к библиотеке Mscorlib.dll и <xref:System> пространства имен.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- Массив пуст (<xref:System.ArgumentNullException> класса)  
  
- Массив является многомерным (<xref:System.RankException> класса)  
  
- Один или несколько элементов массива не реализуют <xref:System.IComparable> интерфейс (<xref:System.InvalidOperationException> класса)  
  
## <a name="see-also"></a>См. также

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Устранение неполадок, связанных с массивами](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Коллекции](../../concepts/collections.md)
- [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
