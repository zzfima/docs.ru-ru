---
title: "Исключения, транзакции и компенсация | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "программирование [WF], обработка ошибок"
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Исключения, транзакции и компенсация
[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах.Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.  
  
## В этом подразделе  
 [Исключения](../../../docs/framework/windows-workflow-foundation//exceptions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.  
  
 [Транзакции](../../../docs/framework/windows-workflow-foundation//workflow-transactions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.  
  
 [Компенсация](../../../docs/framework/windows-workflow-foundation//compensation.md)  
 Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.  
  
 [Отмена](../../../docs/framework/windows-workflow-foundation//modeling-cancellation-behavior-in-workflows.md)  
 Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.  
  
 [Отладка рабочих процессов](../../../docs/framework/windows-workflow-foundation//debugging-workflows.md)  
 Содержит описание способов отладки рабочих процессов.