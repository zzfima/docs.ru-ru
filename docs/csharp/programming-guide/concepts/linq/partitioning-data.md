---
title: Секционирование данных (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: b857c8c6e6b56a7263e6725a747e98ccfe4ff4fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832467"
---
# <a name="partitioning-data-c"></a>Секционирование данных (C#)
Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.  
  
 На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов. Первая операция возвращает первые три элемента в последовательности. Вторая операция пропускает первые три элемента и возвращает остальные элементы. Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.  
  
 ![Рисунок иллюстрирующий три операции секционирования LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.  
  
## <a name="operators"></a>Операторы  
  
|Имя оператора|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|Пропускает элементы до указанной позиции в последовательности.|Неприменимо.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Пропускает элементы, пока элемент не удовлетворит условию функции предиката.|Неприменимо.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Возвращает элементы на указанную позицию в последовательности.|Неприменимо.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Принимает элементы, пока элемент не удовлетворит условию функции предиката.|Неприменимо.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
