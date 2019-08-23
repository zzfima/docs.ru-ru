---
title: Группировка элементов последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: 50887acefdd5d0feaf9d0885e9ee842f44f0ef65
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915052"
---
# <a name="group-elements-in-a-sequence"></a>Группировка элементов последовательности
Оператор <xref:System.Linq.Enumerable.GroupBy%2A> группирует элементы последовательности. В следующем примере используется база данных Northwind.  
  
> [!NOTE]
> Иногда значения NULL в столбцах в запросах <xref:System.Linq.Enumerable.GroupBy%2A> могут вызывать исключение <xref:System.InvalidOperationException>. Дополнительные сведения см. в разделе "GroupBy InvalidOperationException" раздела [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
## <a name="example"></a>Пример  
 Следующий пример разделяет `Products` по `CategoryID`.  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a>Пример  
 В следующем примере для нахождения максимальной цены за единицу для каждого <xref:System.Linq.Enumerable.Max%2A> используется `CategoryID`.  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a>Пример  
 В следующем примере для нахождения среднего значения `UnitPrice` для каждого `CategoryID` используется функция Average.  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a>Пример  
 В следующем примере для нахождения общего значения <xref:System.Linq.Queryable.Sum%2A> для каждого `UnitPrice` используется `CategoryID`.  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a>Пример  
 В следующем примере для нахождения в каждом <xref:System.Linq.Queryable.Count%2A> числа `Products`, производство которых прекращено, используется `CategoryID`.  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a>Пример  
 В следующем примере для нахождения всех категорий, включающих как минимум 10 продуктов, используется предложение `where`.  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a>Пример  
 В следующем примере продукты сгруппированы по `CategoryID` и `SupplierID`.  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a>Пример  
 В следующем примере возвращается две последовательности продуктов. В первой последовательности находятся продукты, цена за единицу которых меньше или равна 10. Во второй последовательности содержатся продукты, цена за единицу которых больше 10.  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a>Пример  
 Оператор <xref:System.Linq.Queryable.GroupBy%2A> может принимает только один основной аргумент. Если требуется выполнить группировку по нескольким признакам, следует создать анонимный тип, как показано в следующем примере.  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
