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
 [Коллекции](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
