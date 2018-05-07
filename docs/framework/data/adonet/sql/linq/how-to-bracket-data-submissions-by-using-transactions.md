---
title: Практическое руководство. Группировка отправок данных с использованием транзакций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: aa77d364d1ee4efc09386dd7e889914aeb2f3f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Практическое руководство. Группировка отправок данных с использованием транзакций
Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>. Дополнительные сведения см. в разделе [поддержку транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## <a name="example"></a>Пример  
 В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Поддержка транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
