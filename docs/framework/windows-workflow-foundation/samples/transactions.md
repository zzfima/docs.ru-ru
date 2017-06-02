---
title: "Транзакции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Транзакции
В этом разделе содержатся образцы, демонстрирующие сценарии, использующие транзакции рабочего процесса в [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## В этом подразделе  
 [Выполнение рабочего процесса в императивном коде TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/execute-a-workflow-in-an-imperative-transactionscope.md)  
 Демонстрируется, как выполнить рабочий процесс с использованием <xref:System.Activities.WorkflowInvoker> при <xref:System.Transactions.Transaction> из императивного кода C\#.  
  
 [Область сопровождения транзакции](../../../../docs/framework/windows-workflow-foundation/samples/transaction-convoy-scope.md)  
 Демонстрируется создание шаблона обмена сообщениями Parallel Convoy совместно с <xref:System.ServiceModel.Activities.TransactedReceiveScope> для моделирования протокола, при котором несколько операций могут выполняться в любом порядке в рамках одной транзакции.  
  
 [Откат транзакции](../../../../docs/framework/windows-workflow-foundation/samples/transaction-rollback.md)  
 Демонстрируется, как создавать пользовательское действие <xref:System.Activities.NativeActivity>, которое обращается к внешнему обработчику <xref:System.Activities.RuntimeTransactionHandle> для получения внешней транзакции и выполнения ее явного отката.  
  
 [Область подавления транзакции](../../../../docs/framework/windows-workflow-foundation/samples/suppress-transaction-scope.md)  
 Демонстрируется, как создавать авторское пользовательское действие `SuppressTransactionScope`, блокирующее внешнюю транзакцию среды выполнения при ее появлении.  
  
 [Транзакционные очереди](../../../../docs/framework/windows-workflow-foundation/samples/transacted-queues.md)  
 Показано, как объединить очереди и транзакции в [!INCLUDE[wf1](../../../../includes/wf1-md.md)], чтобы создать надежные и масштабируемые службы.