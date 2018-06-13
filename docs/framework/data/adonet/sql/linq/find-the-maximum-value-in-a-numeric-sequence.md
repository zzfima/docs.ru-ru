---
title: Нахождение максимального значения в числовой последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: c93b322c755036c8bf7150bb5c96b9c32b6dc9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353821"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a>Нахождение максимального значения в числовой последовательности
Используйте оператор <xref:System.Linq.Enumerable.Max%2A> для нахождения максимального значения в числовой последовательности.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется поиск самой последней даты приема сотрудника на работу.  
  
 Если этот запрос запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `11/15/1994 12:00:00 AM`.  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется максимальное количество единиц продукта на складе.  
  
 Если этот пример запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `125`.  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a>Пример  
 В следующем примере для поиска `Products`, имеющего максимальную цену за единицу в каждой категории используется функция Max. Результаты упорядочиваются по категории.  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a>См. также  
 [Статистические запросы](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
