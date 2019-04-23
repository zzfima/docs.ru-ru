---
title: Поддержка транзакций
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 519ddab069cf3c4ca1ccfa7b203769b8102db844
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196168"
---
# <a name="transaction-support"></a>Поддержка транзакций
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает три различные модели транзакций. Далее представлен список этих моделей в порядке выполненных проверок.  
  
## <a name="explicit-local-transaction"></a>Явные локальные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, если свойству <xref:System.Data.Linq.DataContext.Transaction%2A> задана транзакция (`IDbTransaction`), вызов <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в контексте этой же транзакции.  
  
 Вашей обязанностью является выполнение фиксации или отката транзакции после ее успешного выполнения. Подключение, соответствующее транзакции, должно совпадать с подключением, используемым для создания <xref:System.Data.Linq.DataContext>. При использовании разных подключений создается исключение.  
  
## <a name="explicit-distributable-transaction"></a>Явные распределяемые транзакции  
 Можно вызвать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API-интерфейсы (включая, но не ограничиваясь <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) в области действия активного <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обнаруживает, что вызов находится в области транзакции и не создает новую транзакцию. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] также позволяет избежать в этом случае закрытия соединения. В контексте данной транзакции можно осуществить запрос и выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Неявные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проверяет, является ли вызов в рамках <xref:System.Transactions.Transaction> или, если `Transaction` свойство (`IDbTransaction`) имеет значение запускаемая пользователем локальная транзакция. Если транзакции не [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запускает локальную транзакцию (`IDbTransaction`) и использовать ее для выполнения сгенерированных команд SQL. После успешного завершения всех команд SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] фиксирует локальную транзакцию и возвращается.  
  
## <a name="see-also"></a>См. также

- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Практическое руководство. Объединить в пакеты отправку данных с помощью транзакций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
