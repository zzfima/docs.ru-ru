---
title: Секционирование данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 17e929d3c95e079a0a73b8e8cadf51d3ece6f5f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645916"
---
# <a name="partitioning-data-visual-basic"></a>Секционирование данных (Visual Basic)
Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.  
  
 На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов. Первая операция возвращает первые три элемента в последовательности. Вторая операция пропускает первые три элемента и возвращает остальные элементы. Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.  
  
 ![Операции секционирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.  
  
## <a name="operators"></a>Операторы  
  
|Имя оператора|Описание|Синтаксис выражения запроса Visual Basic|Дополнительные сведения|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Пропускает элементы до указанной позиции в последовательности.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Пропускает элементы, пока элемент не удовлетворит условию функции предиката.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Возвращает элементы на указанную позицию в последовательности.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Принимает элементы, пока элемент не удовлетворит условию функции предиката.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
  
### <a name="skip"></a>Skip  
 Следующий пример кода использует `Skip` предложение в Visual Basic для пропуска первых четырех строк в массиве строк перед возвращением оставшихся строк в массиве.  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 Следующий пример кода использует `Skip While` предложения в Visual Basic для пропуска строк в массиве во время первой буквой строки «». Возвращаются оставшиеся строки в массиве.  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 Следующий пример кода использует `Take` предложение в Visual Basic для возврата первых двух строк в массиве строк.  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 Следующий пример кода использует `Take While` предложение в Visual Basic для получения строк из массива, тогда как длина строки меньше пяти.  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>  
 [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Предложение Skip](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Предложение Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Предложение Take](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [Предложение Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)
