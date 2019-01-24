---
title: Операции, использующие квантификаторы (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0f732cdb51ed4e26039fc8c1d02b95ad32f901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551934"
---
# <a name="quantifier-operations-visual-basic"></a>Операции, использующие квантификаторы (Visual Basic)
Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.  
  
 На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям. Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`. Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.  
  
 ![Операции, использующие квантификаторы LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание:|Синтаксис выражений запросов Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Все|Определяет, все ли элементы последовательности удовлетворяют условию.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Любой|Определяет, удовлетворяют ли условию какие-либо элементы последовательности.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Содержит|Определяет, содержит ли последовательность указанный элемент.|Неприменимо.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов  
 В этих примерах используется `Aggregate` предложение в Visual Basic как часть условия фильтрации в запросе LINQ.  
  
 В следующем примере используется `Aggregate` предложение и <xref:System.Linq.Enumerable.All%2A> метод расширения, чтобы вернуть из коллекции тем пользователям, которых животные все старее, чем определенный период времени.  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 В следующем примере используется `Aggregate` предложение и <xref:System.Linq.Enumerable.Any%2A> метод расширения для возврата из коллекции, пользователи, имеющие хотя бы одну pet, старше, чем определенный период времени.  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
