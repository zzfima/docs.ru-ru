---
title: Преобразование последовательности в универсальный список
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 2c83a744e26fabb6f3e6ddd0a31c7cdd0c7139a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032823"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Преобразование последовательности в универсальный список
Для создания универсального списка из последовательности используется <xref:System.Linq.Enumerable.ToList%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Linq.Enumerable.ToList%2A> для непосредственного преобразования запроса в универсальный <xref:System.Collections.Generic.List%601>.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
