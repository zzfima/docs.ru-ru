---
title: Статистические запросы
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: b7b38306903313825056c02fc3c3fb8c98e07e17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964121"
---
# <a name="aggregate-queries"></a>Статистические запросы
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает агрегатные операторы `Average`, `Count`, `Max`, `Min` и `Sum`. Обратите внимание на следующие характеристики агрегатных операторов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Агрегатные запросы выполняются немедленно.  
  
     Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
- Агрегатные запросы обычно возвращают число, а не коллекцию.  
  
     Дополнительные сведения см. в разделе [операции агрегирования](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).  
  
- В анонимном типе вызвать агрегаты нельзя.  
  
 В следующих разделах используются примеры из учебной базы данных Northwind. Дополнительные сведения см. в статье [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Возврат среднего значения из числовой последовательности](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 Демонстрируется использование оператора <xref:System.Linq.Enumerable.Average%2A>.  
  
 [Подсчет количества элементов в последовательности](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 Демонстрируется использование оператора <xref:System.Linq.Enumerable.Count%2A>.  
  
 [Нахождение наибольшего значения в числовой последовательности](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 Демонстрируется использование оператора <xref:System.Linq.Enumerable.Max%2A>.  
  
 [Нахождение наименьшего значения в числовой последовательности](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 Демонстрируется использование оператора <xref:System.Linq.Enumerable.Min%2A>.  
  
 [Вычисление суммы значений числовой последовательности](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 Демонстрируется использование оператора <xref:System.Linq.Enumerable.Sum%2A>.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Содержит ссылки на запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в Visual Basic и C#.  
  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Содержит ссылки на разделы, в которых объясняются принципы разработки запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 Содержит описание принципов работы запросов в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].
