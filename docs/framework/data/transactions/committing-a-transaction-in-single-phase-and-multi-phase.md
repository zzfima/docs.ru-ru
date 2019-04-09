---
title: Однофазная и многофазная фиксация транзакции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: cbe00fb792ab5f2a7586a958ddbe5bdf004656dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089566"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a>Однофазная и многофазная фиксация транзакции
Каждым используемым в транзакции ресурсом управляет диспетчер ресурсов, действия которого координируются диспетчером транзакций. [Ресурсы прикрепление в транзакции, в качестве участников](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) разделе рассматривается, как можно прикрепить ресурс (или несколько ресурсов) в транзакции. В этом разделе также описывается порядок координации процесса фиксации транзакции между зачисленными ресурсами.  
  
 При завершении транзакции приложение формирует запрос на фиксацию или откат транзакции. Диспетчер транзакций должен исключить ситуации, в которых один из диспетчеров ресурсов голосует за фиксацию, а другие - за откат транзакции.  
  
 Если транзакция включает несколько ресурсов, необходимо выполнить двухфазную фиксацию (2PC). Протокол двухфазной фиксации (фаза подготовки и фаза фиксации) гарантирует, что при завершении транзакции все изменения, произведенные над всеми ресурсами, либо полностью фиксируются, либо полностью откатываются. После завершения транзакции результат сообщается всем участникам. Подробное описание протокола двухфазной фиксации, см. в книге «*обработки транзакций: Основные понятия и методы (серия Morgan kaufmann по системам управления данными) ISBN: 1558601902*«, Джим Грей.  
  
 Кроме того, оптимизировать производительность транзакции можно путем участия в протоколе однофазной фиксации. Дополнительные сведения см. в разделе [оптимизация производительности с помощью однофазной фиксации и повышаемого однофазного уведомления](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 Если требуется только получение информации о результате транзакции без участия в голосовании, необходимо подписаться на событие <xref:System.Transactions.Transaction.TransactionCompleted>.  
  
## <a name="two-phase-commit-2pc"></a>Двухфазная фиксация (2PC)  
 В первой фазе транзакции диспетчер транзакций опрашивает каждый ресурс, чтобы определить, следует ли выполнить фиксацию или откат транзакции. Во второй фазе транзакции диспетчер транзакций уведомляет каждый ресурс о результате опроса, позволяя ресурсам выполнить необходимые операции очистки.  
  
 Для участия в такой транзакции диспетчеру ресурсов необходимо реализовать интерфейс <xref:System.Transactions.IEnlistmentNotification>, который предоставляет методы, вызываемые диспетчером транзакций как уведомления при двухфазной фиксации.  Ниже представлен пример такой реализации.  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a>Фаза подготовки (фаза 1)  
 При получении запроса <xref:System.Transactions.CommittableTransaction.Commit%2A> от приложения диспетчер транзакций приступает к фазе подготовки всех зачисленных участников путем вызова метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> для каждого зачисленного ресурса с целью получения голосов за результат транзакции.  
  
 Диспетчеру ресурсов, реализующему интерфейс <xref:System.Transactions.IEnlistmentNotification>, сначала необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>, как показано в следующем простом примере.  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 После получения этого вызова диспетчеру устойчивых ресурсов необходимо записать в журнал данные для восстановления транзакции (доступ к которым осуществляется путем извлечения свойства <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>) и всю необходимую информацию для завершения транзакции фиксацией. Запись этой информации в рамках метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> не требуется, поскольку диспетчер ресурсов может сделать это в рабочем потоке.  
  
 После того, как диспетчер ресурсов завершил свои операции подготовки, ему необходимо проголосовать за фиксацию или откат путем вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> или <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>. Обратите внимание, что класс <xref:System.Transactions.PreparingEnlistment> наследует метод <xref:System.Transactions.Enlistment.Done%2A> от класса <xref:System.Transactions.Enlistment>. Если вызвать этот метод для обратного вызова <xref:System.Transactions.PreparingEnlistment> в фазе подготовки, он сообщает диспетчеру транзакций, что зачисленный ресурс доступен в режиме "только чтение" (т. е. диспетчеры ресурсов могут читать, но не могут изменять защищенные транзакцией данные), и диспетчер ресурсов не получает дальнейших уведомлений от диспетчера транзакций относительно результата транзакции в фазе 2.  
  
 Приложение получает сведения об успешной подготовке к фиксации транзакции после того, как все диспетчеры ресурсов проголосуют с помощью метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.  
  
### <a name="commit-phase-phase-2"></a>Фаза фиксации (фаза 2)  
 Если во второй фазе транзакции диспетчер транзакций получает сведения об успешной подготовке от всех диспетчеров ресурсов (все диспетчеры ресурсов вызвали метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> в конце фазы 1), он вызывает метод <xref:System.Transactions.IEnlistmentNotification.Commit%2A> для каждого диспетчера ресурсов. После этого диспетчеры ресурсов могут зафиксировать изменения.  
  
 Если в фазе 1 хотя бы от одного диспетчера ресурсов получено сообщение о том, что подготовку выполнить не удалось, диспетчер транзакций вызывает метод <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> для каждого диспетчера ресурсов и сообщает приложению о сбое фиксации.  
  
 Таким образом, используемому диспетчеру ресурсов необходимо реализовать следующие методы.  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment    
     enlistment.Done();    
}  
```  
  
 Диспетчер ресурсов должен выполнить любые действия, необходимые для завершения транзакции в соответствии с типом уведомления, и затем информировать диспетчер транзакций о завершении транзакции, вызвав метод <xref:System.Transactions.Enlistment.Done%2A> для параметра <xref:System.Transactions.Enlistment>. Это может быть выполнено в рабочем потоке. Заметьте, что уведомления второго этапа могут быть встроены в тот же поток, который вызвал метод <xref:System.Transactions.PreparingEnlistment.Prepared%2A> на первой фазе. Таким образом, после вызова метода <xref:System.Transactions.PreparingEnlistment.Prepared%2A> не нужно выполнять никаких действий (например, снимать блокировки), которые должны были быть выполнены перед получением уведомлений второго этапа.  
  
### <a name="implementing-indoubt"></a>Реализация метода InDoubt  
 Наконец, необходимо реализовать метод <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> для диспетчера неустойчивых ресурсов. Этот метод вызывается при потере контакта диспетчера транзакций с одним или несколькими участниками, в результате чего их состояние становится неизвестным. В этом случае необходимо сделать соответствующую запись в журнале, чтобы можно было позднее выяснить, остался ли кто-либо из участников транзакции в несогласованном состоянии.  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a>Оптимизация однофазной фиксации  
 Протокол однофазной фиксации наиболее эффективен при использовании во время выполнения, поскольку все изменения производятся без какой-либо явной координации. Дополнительные сведения об этом протоколе см. в разделе [оптимизация производительности с помощью однофазной фиксации и повышаемого однофазного уведомления](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
## <a name="see-also"></a>См. также

- [Оптимизация производительности с помощью механизмов уведомления об однофазной фиксации и повышаемого однофазного присоединения](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)
- [Зачисление ресурсов в транзакцию в качестве участников](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)
