---
title: Возврат объединения наборов двух последовательностей.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 058856243b2a8daaecd653a9b5999013de5407a8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182523"
---
# <a name="return-the-set-union-of-two-sequences"></a>Возврат объединения наборов двух последовательностей.
Оператор <xref:System.Linq.Queryable.Union%2A> используется для возвращения объединения наборов двух последовательностей.  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.Linq.Queryable.Union%2A> используется для возврата последовательности всех стран или регионов, в которых есть `Customers` или `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]оператор определяется для множества наборов как неупорядоченное объединение множества наборов ( [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) фактически результат предложения в SQL). <xref:System.Linq.Queryable.Union%2A>

Дополнительные сведения и примеры см. в <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>разделе.
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Преобразование стандартных операторов запросов](standard-query-operator-translation.md)
