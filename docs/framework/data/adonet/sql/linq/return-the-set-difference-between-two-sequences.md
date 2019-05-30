---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 5bb7d797ad2adc4374f7a10c11d66be69feeb7a1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380052"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Возврат разности наборов между двумя последовательностями
Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Linq.Queryable.Except%2A> для возвращения последовательности всех стран и регионов, в котором `Customers` активно, но в котором не `Employees` live.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах. Семантика для мультинаборов не определена.  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
