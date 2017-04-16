---
title: "Транзакции | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
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
---
# Транзакции
Образцы в этом разделе демонстрируют транзакции рабочих процессов в [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## В этом подразделе  
 [Простой класс TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Этот раздел состоит из четырех сценариев, показывающих, как вкладывать экземпляры <xref:System.Activities.Statements.TransactionScope>.  
  
 [Использование TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Показывается передача транзакции от клиента к серверу с использованием <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции у клиента и <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения сообщения с передаваемой транзакцией и определения времени ее существования на сервере.  
  
 [Вложенные объекты TransactionScope в службе](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 Представлено два сценария, показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе.