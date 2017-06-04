---
title: "Выполнение восстановления  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Выполнение восстановления 
Диспетчер ресурсов обеспечивает разрешение зачислений устойчивых ресурсов в транзакции, повторно зачисляя участника транзакции после сбоя ресурса.  
  
## Процесс восстановления  
 Для зачисления устойчивого ресурса \(описываемого реализацией интерфейса <xref:System.Transactions.IEnlistmentNotification>\), который способен к восстановлению, необходимо вызвать метод <xref:System.Transactions.Transaction.EnlistDurable%2A>.Кроме того, необходимо предоставить метод <xref:System.Transactions.Transaction.EnlistDurable%2A> с идентификатором диспетчера ресурсов \(<xref:System.Guid>\), который используется для постоянной отметки участника транзакции в событии сбоя ресурса.По этой причине идентификатор <xref:System.Guid>, переданный исходному вызову Enlist, должен совпадать со значением параметра *resourceManagerIdentifier* в вызове метода <xref:System.Transactions.TransactionManager.Reenlist%2A> во время восстановления.В противном случае возникает исключение <xref:System.Transactions.TransactionException>.Дополнительные сведения о зачислении устойчивых ресурсов см. в разделе [Прикрепление ресурсов в качестве участников транзакции ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md).  
  
 Если в фазе подготовки \(фазе 1\) протокола двухфазной фиксации пользовательская реализация диспетчера ресурсов получает уведомление <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>, она должна создать запись о подготовке в журнале.Запись должна включать всю необходимую информацию для завершения транзакции фиксацией.Доступ к записи о подготовке может быть осуществлен во время восстановления путем извлечения свойства <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> обратного вызова *preparingEnlistment*.Создание этой записи в рамках метода <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> не требуется, поскольку диспетчер ресурсов может сделать это в рабочем потоке.  
  
 Процесс восстановления состоит из следующих двух шагов.  
  
### Шаг 1 — повторное зачисление  
 Диспетчер ресурсов проверяет запись о подготовке для каждого зачисления, которое находится под сомнением.Это выполняется путем проверки свойства <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> обратного вызова <xref:System.Transactions.PreparingEnlistment>, переданного диспетчеру ресурсов в уведомлении <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> в фазе 1.  
  
 Для каждого проверяемого зачисления диспетчер ресурсов вызывает метод <xref:System.Transactions.TransactionManager.Reenlist%2A> для диспетчера транзакций.Этот метод передает уникальный <xref:System.Guid>, идентифицирующий диспетчер ресурсов, а также данные перечисления в массиве байтов.Возвращается новый объект <xref:System.Transactions.Enlistment>.Если в результате повторного зачисления возникает исключение, диспетчеру необходимо повторить попытку через некоторое время.  
  
 Метод <xref:System.Transactions.TransactionManager.Reenlist%2A> следует вызывать только после перезапуска диспетчера ресурсов после сбоя.Кроме того, повторное зачисление следует выполнить только для неразрешенных транзакций, зарегистрированных диспетчером ресурсов в ходе начальной фазы подготовки двухфазной фиксации.Любая попытка вызова этого метода в недопустимое время может привести к ошибочным результатам.  
  
 При повторном зачислении участника с помощью этого метода в зависимости от результата транзакции вызывается соответствующий метод фазы 2 интерфейса <xref:System.Transactions.IEnlistmentNotification> \(<xref:System.Transactions.IEnlistmentNotification.Commit%2A>, <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> или <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>\).  
  
### Шаг 2 — завершение восстановления  
 После завершения всех повторных зачислений диспетчер транзакций вызывает метод <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>.Этот метод завершает восстановление и информирует диспетчер транзакций о том, что у диспетчера ресурсов больше нет проблемных транзакций.Это позволяет гарантировать, что диспетчер ресурсов не вызовет метод <xref:System.Transactions.TransactionManager.Reenlist%2A> повторно.  
  
 От диспетчера ресурсов не требуется разрешения всех проблемных транзакций, перед повторным зачислением в новые транзакции.Первый шаг может быть выполнен в любое время после установления связи диспетчера ресурсов с диспетчером транзакций, однако после вызова метода <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> \(шаг 2\) первый шаг нельзя выполнить повторно.Шаг 2 можно выполнить несколько раз без воздействия на результат транзакций.