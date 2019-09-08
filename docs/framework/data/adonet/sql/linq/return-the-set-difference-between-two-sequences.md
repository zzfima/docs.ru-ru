---
title: Возврат разности наборов между двумя последовательностями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781144"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Возврат разности наборов между двумя последовательностями
Оператор <xref:System.Linq.Queryable.Except%2A> используется для возвращения разности наборов между двумя последовательностями.  
  
## <a name="example"></a>Пример  
 В этом примере <xref:System.Linq.Queryable.Except%2A> используется для возврата последовательности всех стран или регионов, `Customers` в которых динамический, но не `Employees` в режиме реального времени.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Except%2A> правильно определен только в наборах. Семантика для мультинаборов не определена.  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
- [Преобразование стандартных операторов запросов](standard-query-operator-translation.md)
