---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73bfef97de5c6622a6dda4edb2e4ff0b829df7e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="transactions"></a>Транзакции
Образцы в этом разделе демонстрируют транзакции рабочих процессов в [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## <a name="in-this-section"></a>Содержание  
 [Простой класс TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Этот раздел состоит из четырех сценариев, показывающих, как вкладывать экземпляры <xref:System.Activities.Statements.TransactionScope>.  
  
 [Использование TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Показывается передача транзакции от клиента к серверу с использованием <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции у клиента и <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения сообщения с передаваемой транзакцией и определения времени ее существования на сервере.  
  
 [Вложенные объекты TransactionScope в службе](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 Представлено два сценария, показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе.
