---
title: "Фильтрация данных (Visual Basic) | Документы Microsoft"
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3751164b7697b63937611c77d9fda0e2873625d8
ms.lasthandoff: 03/13/2017

---
# <a name="filtering-data-visual-basic"></a>Фильтрация данных (Visual Basic)
Фильтрация — это операция по ограничению значений в результирующем наборе содержат только те элементы, которые удовлетворяют указанному условию. Это также называется выбора.  
  
 Ниже показаны результаты фильтрации последовательности символов. Предикат для операции фильтрации указывает, что символ должен быть «A».  
  
 ![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, выполняющие выбора.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|OfType|Выбирает значения в зависимости от их возможности приведения к указанному типу.|Неприменимо.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|Where|Выбирает значения, основанные на функции предиката.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса  
 В следующем примере используется `Where` для выбора из массива строк, имеющих определенную длину.  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Где предложения](../../../../visual-basic/language-reference/queries/where-clause.md)   
 [Практическое руководство: фильтрацию результатов запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)   
 [Практическое руководство: запрос сборки метаданных с помощью отражения (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)   
 [Практическое руководство: запрос файлов с указанными атрибутами или именем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)   
 [Практическое руководство: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
