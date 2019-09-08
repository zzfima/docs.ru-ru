---
title: Практическое руководство. Как получить несколько объектов одновременно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 48cdb47bec35b5315e03629d3a01657136bf7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781687"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Практическое руководство. Как получить несколько объектов одновременно
Для извлечения нескольких объектов из одного запроса используется <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Пример  
 В следующем коде для извлечения объекта <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> и `Customer` используется метод `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
