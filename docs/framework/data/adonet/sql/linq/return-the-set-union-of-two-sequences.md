---
title: Возврат объединения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: c7d7a267df13cfa54d682ab9b65953f2c0a85a27
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347550"
---
# <a name="return-the-set-union-of-two-sequences"></a>Возврат объединения наборов двух последовательностей.
Оператор <xref:System.Linq.Queryable.Union%2A> используется для возвращения объединения наборов двух последовательностей.  
  
## <a name="example"></a>Пример  
 В данном примере для возвращения последовательности всех стран, где находятся <xref:System.Linq.Queryable.Union%2A> или`Customers`, используется `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> оператор определен для мультинаборов как неупорядоченное объединение мультинаборов (фактически результат [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) предложение в SQL).  
  
## <a name="see-also"></a>См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
