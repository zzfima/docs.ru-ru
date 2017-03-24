---
title: "Секционирование данных (Visual Basic) | Документы Microsoft"
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
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
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
ms.openlocfilehash: a746ce3e24812d1df6b6e221cca0364bf2cc7f1c
ms.lasthandoff: 03/13/2017

---
# <a name="partitioning-data-visual-basic"></a>Секционирование данных (Visual Basic)
Секционирование в LINQ — это операция разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.  
  
 Ниже показаны результаты трех различных операций секционирования в последовательности символов. Первая операция возвращает первые три элемента в последовательности. Вторая операция пропускает первые три элемента и возвращает остальные элементы. Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.  
  
 ![Операции секционирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, выполняют секционирование.  
  
## <a name="operators"></a>Операторы  
  
|Имя оператора|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Пропустить|Пропускает элементы до указанной позиции в последовательности.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|SkipWhile|Пропускает элементы, пока элемент не удовлетворит условию функции предиката.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|Take|Возвращает элементы указанной позиции в последовательности.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|TakeWhile|Принимает элементы, пока элемент не удовлетворит условию функции предиката.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="skip"></a>Пропустить  
 В следующем примере кода `Skip` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для пропуска первых четырех строк в массиве строк перед возвращением оставшихся строк в массиве.  
  
 [!code-vb[CsLINQPartitioning&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 В следующем примере кода `Skip While` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для пропуска строк в массиве, начинающихся с буквы «». Оставшиеся строки массива возвращаются.  
  
 [!code-vb[CsLINQPartitioning&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 В следующем примере кода `Take` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для возврата первых двух строк в массиве строк.  
  
 [!code-vb[CsLINQPartitioning&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 В следующем примере кода `Take While` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для возврата из массива строк, тогда как длина строки меньше пяти.  
  
 [!code-vb[CsLINQPartitioning&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение SKIP](../../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Предложение Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Предложение Take](../../../../visual-basic/language-reference/queries/take-clause.md)   
 [Предложение Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)
