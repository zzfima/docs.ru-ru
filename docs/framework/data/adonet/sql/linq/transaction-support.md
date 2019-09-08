---
title: Поддержка транзакций
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 9c7128ef432fa609b8d628bc74caebe790058ede
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792277"
---
# <a name="transaction-support"></a>Поддержка транзакций
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]поддерживает три различные модели транзакций. Далее представлен список этих моделей в порядке выполненных проверок.  
  
## <a name="explicit-local-transaction"></a>Явные локальные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, если свойству <xref:System.Data.Linq.DataContext.Transaction%2A> задана транзакция (`IDbTransaction`), вызов <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в контексте этой же транзакции.  
  
 Вашей обязанностью является выполнение фиксации или отката транзакции после ее успешного выполнения. Подключение, соответствующее транзакции, должно совпадать с подключением, используемым для создания <xref:System.Data.Linq.DataContext>. При использовании разных подключений создается исключение.  
  
## <a name="explicit-distributable-transaction"></a>Явные распределяемые транзакции  
 Вы можете вызывать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (включая, <xref:System.Data.Linq.DataContext.SubmitChanges%2A>но не ограниченные) в области активного <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Определяет, что вызов находится в области транзакции и не создает новую транзакцию. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Кроме того, не следует закрывать соединение в этом случае. В контексте данной транзакции можно осуществить запрос и выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="implicit-transaction"></a>Неявные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>метод [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проверяет, находится ли вызов <xref:System.Transactions.Transaction> в области действия или если `Transaction` свойство (`IDbTransaction`) установлено в качестве пользовательской локальной транзакции. Если она не находит ни одной [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] транзакции, запускает локальную`IDbTransaction`транзакцию () и использует ее для выполнения созданных команд SQL. После успешного завершения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] всех команд SQL фиксирует локальную транзакцию и возвращает.  
  
## <a name="see-also"></a>См. также

- [Основные сведения](background-information.md)
- [Практическое руководство. Скобки для отправки данных с помощью транзакций](how-to-bracket-data-submissions-by-using-transactions.md)
