---
title: Примеры синтаксиса запросов на основе методов. Группирование
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 7ade24ecee5a69403f3264a62fbdffdcd9decd3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634484"
---
# <a name="method-based-query-syntax-examples-grouping"></a>Примеры синтаксиса запросов на основе методов. Группирование
Примеры в этом разделе демонстрируется использование `GroupBy` метод для запроса [модели AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) с использованием синтаксиса запросов на основе методов. Модель AdventureWorks Sales, которая используется в этих примерах, построена на основе таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail в образце базы данных AdventureWorks.  
  
 В примерах в этом разделе используются следующие `using` / `Imports` инструкции:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Пример  
 В следующем примере метод `GroupBy` возвращает объекты `Address`, сгруппированные по почтовому индексу. Результаты проецируются в анонимный тип.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a>Пример  
 В следующем примере метод `GroupBy` возвращает объекты `Contact`, сгруппированные по первой букве фамилии контактного лица. Кроме того, результаты сортируются по первой букве фамилии и проецируются на анонимный тип.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a>Пример  
 В следующем примере метод `GroupBy` возвращает объекты `SalesOrderHeader`, сгруппированные по идентификаторам клиентов. Также возвращается число продаж для каждого клиента.  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a>См. также
- [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
