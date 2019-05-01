---
title: Вычисление суммы значений в числовой последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 2f66b996a0e688205d61f5fca476c0335616ee38
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032946"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Вычисление суммы значений в числовой последовательности
Для вычисления суммы значений в последовательности чисел используется оператор <xref:System.Linq.Enumerable.Sum%2A>.  
  
 Обратите внимание на следующие характеристики оператора `Sum` в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Для пустой последовательности или последовательности, содержащей только значения NULL, значением агрегатного оператора стандартного оператора запроса `Sum` является ноль. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] семантики SQL остаются неизменными. Поэтому для пустой последовательности или последовательности, содержащей только значения NULL, значением`Sum` является NULL.  
  
- Ограничения SQL для промежуточных результатов применяются к агрегатным выражениям в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Сумма 32-разрядных целых чисел не вычисляется с помощью 64-разрядных вычислений и может произойти переполнение для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] перевод `Sum`. Такая возможность существует, даже если реализация стандартного оператора запроса не вызывает переполнения для соответствующей последовательности в памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере вычисляется общая стоимость доставки всех заказов в таблице `Order`.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `64942.6900`.  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Пример  
 В следующем примере вычисляется общее число заказанных элементов для всех продуктов.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `780`.  
  
 Обратите внимание на необходимость приведения типов `short` (например, `UnitsOnOrder`), поскольку `Sum` не имеет перегрузки для коротких типов.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>См. также

- [Статистические запросы](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
