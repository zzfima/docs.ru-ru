---
title: Практическое руководство. Сортировка массива в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3f4dbd6dce0957de3451b1f29c3a67ccd6791045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053669"
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
