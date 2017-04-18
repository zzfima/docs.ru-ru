---
title: "Операции, использующие кванторы (Visual Basic) | Документы Microsoft"
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
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7f69aed2e0e6791ca7f17c3420ff75a1ba220187
ms.lasthandoff: 03/13/2017

---
# <a name="quantifier-operations-visual-basic"></a>Операции, использующие кванторы (Visual Basic)
Квантификаторы возвращают <xref:System.Boolean>значение, указывающее, является ли некоторые или все элементы в последовательности, удовлетворяющих заданному условию.</xref:System.Boolean>  
  
 На следующем рисунке показано два различных квантификатора двух различных исходных последовательностей. Первая операция проверяет, если один или несколько элементов имеют символ «A», а результат — `true`. Вторая операция проверяет, если все элементы — символ «A», а результат — `true`.  
  
 ![Операции, использующие кванторы LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, выполняющие операции, использующие кванторы.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Все|Определяет, является ли элементы последовательности удовлетворяют условию.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|Любой|Определяет, является ли все элементы в последовательности удовлетворяют условию.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|Содержит|Определяет, содержит ли последовательность указанный элемент.|Неприменимо.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
 В этих примерах используются `Aggregate` предложение в Visual Basic как часть условия фильтрации в запросе LINQ.  
  
 В следующем примере используется `Aggregate` предложения и <xref:System.Linq.Enumerable.All%2A>метод расширения для возвращения из коллекции тех людей, чьи животными все старше указанного срока.</xref:System.Linq.Enumerable.All%2A>  
  
 [!code-vb[CsLINQAnyAll&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 В следующем примере используется `Aggregate` предложения и <xref:System.Linq.Enumerable.Any%2A>метод расширения для возвращения из коллекции тем, кто не менее одного pet, старше указанного срока.</xref:System.Linq.Enumerable.Any%2A>  
  
 [!code-vb[CsLINQAnyAll&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate-предложение](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Практическое руководство: запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
