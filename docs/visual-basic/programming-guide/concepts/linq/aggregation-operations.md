---
title: "Операции статистической обработки (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d4b07eeb1d09d7db0f75d96629c816f66dbb128
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="aggregation-operations-visual-basic"></a>Операции статистической обработки (Visual Basic)
Статистическая операция вычисляет одно значение по коллекции значений. Например, статистической обработкой является вычисление средней дневной температуры с использованием значений дневной температуры за месяц.  
  
 На приведенном ниже рисунке показаны результаты двух различных операций агрегирования с последовательностью чисел. Первая операция суммирует числа. Вторая операция возвращает максимальное значение в последовательности.  
  
 ![Операции агрегирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции агрегирования.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Статистическое выражение|Выполняет пользовательскую операцию агрегирования со значениями коллекции.|Неприменимо.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Метод Average|Вычисляет среднее значение коллекции значений.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Счетчик|Подсчитывает число элементов в коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Подсчитывает число элементов в большой коллекции (при необходимости только те элементы, которые удовлетворяют функции предиката).|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Максимум|Определяет максимальное значение в коллекции.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Минимум|Определяет минимальное значение в коллекции.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Вычисляет сумму значений в коллекции.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="average"></a>Метод Average  
 Следующий пример кода использует `Aggregate Into Average` предложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для вычисления средней температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a>Счетчик  
 Следующий пример кода использует `Aggregate Into Count` предложения в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для подсчета количества значений в массиве, которые больше или равно 80.  
  
 [!code-vb[CsLINQAggregating#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a>LongCount  
 Следующий пример кода использует `Aggregate Into LongCount` предложение для подсчета количества значений в массиве.  
  
 [!code-vb[CsLINQAggregating#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a>Максимум  
 Следующий пример кода использует `Aggregate Into Max` предложение для вычисления самой высокой температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a>Минимум  
 Следующий пример кода использует `Aggregate Into Min` предложение для вычисления минимального температуры в массиве чисел, представляющих температуру.  
  
 [!code-vb[CsLINQAggregating#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a>Sum  
 Следующий пример кода использует `Aggregate Into Sum` предложения для расчета общего расхода на основании массива значений, представляющих расходы.  
  
 [!code-vb[CsLINQAggregating#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>  
 [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Как: вычисление значений столбцов в текстовом CSV-файле (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 [How to: Count, Sum, or Average Data](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md) (Практическое руководство. Выполнение функций Count, Sum и Average)  
 [How to: Find the Minimum or Maximum Value in a Query Result](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md) (Практическое руководство. Нахождение минимального или максимального значения в результатах запроса)  
 [Как: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 [Как: запрос общее число байтов в наборе папок (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
