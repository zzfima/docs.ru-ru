---
title: Поддержка транзакций
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: ff4d65c37e2d7f76c8c9f0de1de9717c8dca7b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-support"></a>Поддержка транзакций
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает три различные модели транзакций. Далее представлен список этих моделей в порядке выполненных проверок.  
  
## <a name="explicit-local-transaction"></a>Явные локальные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, если свойству <xref:System.Data.Linq.DataContext.Transaction%2A> задана транзакция (`IDbTransaction`), вызов <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в контексте этой же транзакции.  
  
 Вашей обязанностью является выполнение фиксации или отката транзакции после ее успешного выполнения. Подключение, соответствующее транзакции, должно совпадать с подключением, используемым для создания <xref:System.Data.Linq.DataContext>. При использовании разных подключений создается исключение.  
  
## <a name="explicit-distributable-transaction"></a>Явные распределяемые транзакции  
 Можно вызвать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API-интерфейсы (включая, но не ограничиваясь <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) в области действия активного <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обнаруживает, что вызов находится в области транзакции и не создает новую транзакцию. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] также позволяет избежать в этом случае закрытия соединения. В контексте данной транзакции можно осуществить запрос и выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Неявные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проверяет, выполняется ли вызов в области <xref:System.Transactions.Transaction> или если `Transaction` свойство (`IDbTransaction`) имеет значение пользователем локальная транзакция. Если транзакции не [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запускает локальную транзакцию (`IDbTransaction`) и использует ее для выполнения сгенерированных команд SQL. После успешного выполнения всех команд SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] фиксирует локальную транзакцию и возвращается.  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Практическое руководство. Группировка отправок данных с использованием транзакций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
