---
title: "Практическое руководство. Сортировка массива в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Array.Sort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "массивы [Visual Basic], сортировка"
  - "примеры [Visual Basic], массивы"
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Сортировка массива в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере объявляется и заполняется массив объектов `String` с именем `zooAnimals`, затем он сортируется по алфавиту.  
  
## Пример  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Доступ к mscorlib.dll и пространству имен <xref:System>.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Массив пуст \(класс <xref:System.ArgumentNullException>\)  
  
-   Массив является многомерным \(класс <xref:System.RankException> \)  
  
-   Один или более элементов массива не реализуют интерфейс <xref:System.IComparable>\(класс <xref:System.InvalidOperationException>\).  
  
## См. также  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Устранение неполадок, связанных с массивами](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)