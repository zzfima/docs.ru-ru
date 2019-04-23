---
title: Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 3e58c6f2849ed9714b3356662dae313ab9d11696
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134008"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Практическое руководство. Как объединить в пакеты отправку данных с помощью транзакций
Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>. Дополнительные сведения см. в разделе [поддержки транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## <a name="example"></a>Пример  
 В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [Поддержка транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
