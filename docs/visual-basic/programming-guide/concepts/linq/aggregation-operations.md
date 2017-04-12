---
title: "Операции статистической обработки (Visual Basic) | Документы Microsoft"
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
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
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
ms.openlocfilehash: 17d1f18f9acc2f3a62c106f7cff2cf68f8f58a07
ms.lasthandoff: 03/13/2017

---
# <a name="aggregation-operations-visual-basic"></a>Операции статистической обработки (Visual Basic)
Статистическая операция вычисляет одно значение по коллекции значений. Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.  
  
 На следующем рисунке результаты двух различных статистических операций в последовательности чисел. Первая операция суммирует числа. Вторая операция возвращает максимальное значение в последовательности.  
  
 ![Операции статистической обработки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, выполняющие операции статистической обработки.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Статистическое выражение|Выполняет операцию нестандартного статистического выражения для значения коллекции.|Неприменимо.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|Среднее значение|Вычисляет среднее значение коллекции значений.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName></xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|Счетчик|Подсчитывает число элементов в коллекции, при необходимости только те элементы, которые удовлетворяют функции предиката.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName></xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|LongCount|Подсчитывает число элементов в большой коллекции, при необходимости только те элементы, которые удовлетворяют функции предиката.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|Макс.|Определяет максимальное значение в коллекции.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName></xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|Мин.|Определяет минимальное значение в коллекции.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName></xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|Sum|Вычисляет сумму значений в коллекции.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName></xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="average"></a>Метод Average  
 В следующем примере кода `Aggregate Into Average` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для вычисления средней температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a>Счетчик  
 В следующем примере кода `Aggregate Into Count` предложения в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для подсчета числа значений в массиве, которые больше или равен 80.  
  
 [!code-vb[CsLINQAggregating&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a>LongCount  
 В следующем примере кода `Aggregate Into LongCount` предложение для подсчета числа значений в массиве.  
  
 [!code-vb[CsLINQAggregating&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a>Макс.  
 В следующем примере кода `Aggregate Into Max` предложение для вычисления самой высокой температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a>Мин.  
 В следующем примере кода `Aggregate Into Min` предложение для вычисления минимального температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a>Sum  
 В следующем примере кода `Aggregate Into Sum` предложение для расчета общего расхода на основании массива значений, представляющих расходы.  
  
 [!code-vb[CsLINQAggregating №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate-предложение](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Практическое руководство: вычисление значений столбцов в файле CSV (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)   
 [Практическое руководство: число, суммы или среднего значения данных](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)   
 [Практическое руководство: поиск минимального или максимального значения в результатах запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)   
 [Практическое руководство: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)   
 [Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
