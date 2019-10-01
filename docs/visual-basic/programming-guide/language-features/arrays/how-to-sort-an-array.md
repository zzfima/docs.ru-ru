---
title: Практическое руководство. Сортировка массива в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700978"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Как сортировать массив в Visual Basic

В этой статье показан пример сортировки массива строк в Visual Basic.

## <a name="example"></a>Пример

В этом примере объявляется массив объектов `String` с именем `zooAnimals`, который заполняется, а затем сортируется по алфавиту:
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a>Отказоустойчивость

При следующих условиях возможно возникновение исключения:

- Массив пуст (класс <xref:System.ArgumentNullException>).
- Массив является многомерным (класс <xref:System.RankException>).
- Один или несколько элементов массива не реализуют интерфейс <xref:System.IComparable> (класс <xref:System.InvalidOperationException>).

## <a name="see-also"></a>См. также

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Массивы](index.md)
- [Устранение неполадок, связанных с массивами](troubleshooting-arrays.md)
- [Коллекции](../../concepts/collections.md)
- [Оператор For Each...Next](../../../language-reference/statements/for-each-next-statement.md)
