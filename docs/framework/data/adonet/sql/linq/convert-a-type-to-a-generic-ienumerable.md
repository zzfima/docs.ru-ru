---
title: Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d1f4c1c4a561c893b5846e6ae0b08b2d78c3589d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509601"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Практическое руководство. Преобразование типа в универсальный интерфейс IEnumerable
Для возвращения аргумента с типом универсальный <xref:System.Linq.Enumerable.AsEnumerable%2A> используется `IEnumerable`.  
  
## <a name="example"></a>Пример  
 В этом примере [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (с помощью заданного по умолчанию универсального `Query`) предпримет попытку преобразовать запрос в SQL и выполнить его на сервере. Однако предложение `where` ссылается на пользовательский метод на стороне клиента (`isValidProduct`), который не может быть преобразован в SQL.  
  
 Решением является задание клиентской универсальной реализации <xref:System.Collections.Generic.IEnumerable%601> предложения `where` для замены универсального <xref:System.Linq.IQueryable%601>. Для этого следует вызвать оператор <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>См. также
- [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
