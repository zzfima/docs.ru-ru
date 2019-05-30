---
title: Возврат пересечения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 3458ebf8f5708496eef6246fa55cf528e8a32bc4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380058"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>Возврат пересечения наборов двух последовательностей.
Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Linq.Queryable.Intersect%2A> для возвращения последовательности всех стран и регионов, где `Customers` и `Employees` live.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах. Семантика для мультинаборов не определена.  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
