---
title: "Группирование данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d89ae6d155ab901b03cf92a7508261fb147b97b7
ms.lasthandoff: 03/13/2017

---
# <a name="grouping-data-visual-basic"></a>Группирование данных (Visual Basic)
Группирование — это операция размещения данных по группам, чтобы элементы в каждой группе имеют общий атрибут.  
  
 Ниже показаны результаты группировки последовательности символов. Ключ для каждой группы — это символ.  
  
 ![Операции группировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, сгруппировать элементы данных.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|GroupBy|Группирует элементы с общим атрибутом. Каждая группа представлена <xref:System.Linq.IGrouping%602>объекта.</xref:System.Linq.IGrouping%602>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|ToLookup|Добавляет элементы в <xref:System.Linq.Lookup%602>(словарь "один ко многим") на основании функции выбора ключа.</xref:System.Linq.Lookup%602>|Неприменимо.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса  
 В следующем примере кода `Group By` предложение для группировки целых чисел из списка на основании, являются ли они четным или нечетным.  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)   
 [Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)   
 [Практическое руководство: Разделение файла на несколько файлов с помощью групп (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
