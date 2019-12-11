---
title: Операции над множествами (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 22079b1d41533803f694af210f98bc9fb8a5b322
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711871"
---
# <a name="set-operations-c"></a>Операции над множествами (C#)
Операции над множествами в LINQ — это операции запросов, результирующие наборы которых основываются на наличии или отсутствии эквивалентных элементов в одной или другой коллекции (или наборе).  
  
 Методы стандартных операторов запросов, которые выполняют операции над множествами, перечислены в следующем разделе.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|ОПИСАНИЕ|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Distinct|Удаляет повторяющиеся значения из коллекции.|Неприменимо.|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Исключения|Возвращает разность множеств, т. е. элементы одной коллекции, которые отсутствуют во второй.|Неприменимо.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|Пересечение|Возвращает пересечение множеств, т. е. элементы, присутствующие в каждой из двух коллекций.|Неприменимо.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Объединение|Возвращает объединение множеств, т. е. уникальные элементы, присутствующие в одной из двух коллекций.|Неприменимо.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Сравнение операций над множествами  
  
### <a name="distinct"></a>Distinct  
 В следующем примере показано поведение метода <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> применительно к последовательности символов. Возвращаемая последовательность содержит уникальные элементы из входной последовательности.  
  
 ![График, демонстрирующий поведение Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a>Исключения  
 В следующем примере показано поведение <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Возвращаемая последовательность содержит только те элементы из первой входной последовательности, которых нет во второй.  
  
 ![График, отображающий действие Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Демонстрирует поведение Except.")  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a>Пересечение  
 В следующем примере показано поведение <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Возвращаемая последовательность содержит элементы, общие для обеих входных последовательностей.  
  
 ![График, отображающий пересечение двух последовательностей.](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a>Объединение  
 В следующем примере показана операция объединения двух последовательностей символов. Возвращаемая последовательность содержит уникальные элементы из обеих входных последовательностей.  
  
 ![График, показывающий объединение двух последовательностей.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (C#)](./standard-query-operators-overview.md)
- [Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md)
- [Практическое руководство. Нахождение разности множеств между двумя списками (LINQ) (C#)](./how-to-find-the-set-difference-between-two-lists-linq.md)
