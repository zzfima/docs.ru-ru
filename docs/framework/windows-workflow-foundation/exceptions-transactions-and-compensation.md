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
ms.workload: dotnet
ms.openlocfilehash: e83661ba66ca6a71f26c11172902d5bc602a2f6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exceptions-transactions-and-compensation"></a>Исключения, транзакции и компенсация
[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах. Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.  
  
## <a name="in-this-section"></a>В этом разделе  
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
