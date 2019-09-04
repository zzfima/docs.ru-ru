---
title: Преобразование последовательности в универсальный список
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 43960d100cde7f746a56c023d305795e13bc04e7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247871"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Преобразование последовательности в универсальный список
Для создания универсального списка из последовательности используется <xref:System.Linq.Enumerable.ToList%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Linq.Enumerable.ToList%2A> для непосредственного преобразования запроса в универсальный <xref:System.Collections.Generic.List%601>.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>См. также

- [Примеры запросов](query-examples.md)
