---
title: Операции, использующие квантификаторы (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 24c8f9a6b589592c26c8a514bc44ff9623a82d2f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523109"
---
# <a name="quantifier-operations-c"></a>Операции, использующие квантификаторы (C#)
Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.  
  
 На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям. Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`. Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.  
  
 ![Операции, использующие квантификаторы LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание:|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Все|Определяет, все ли элементы последовательности удовлетворяют условию.|Неприменимо.|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Любой|Определяет, удовлетворяют ли условию какие-либо элементы последовательности.|Неприменимо.|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Содержит|Определяет, содержит ли последовательность указанный элемент.|Неприменимо.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq>  
- [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [Практическое руководство. Динамическое определение фильтров предикатов во время выполнения](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
