---
title: "Исключения, транзакции и компенсация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7fab7247540ba4e098a793adebab54ca4219e503
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="exceptions-transactions-and-compensation"></a>Исключения, транзакции и компенсация
[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах. Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.  
  
## <a name="in-this-section"></a>Содержание  
 [Исключения](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.  
  
 [Транзакции](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.  
  
 [Компенсация](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.  
  
 [Отмена](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.  
  
 [Отладка рабочих процессов](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 Содержит описание способов отладки рабочих процессов.
