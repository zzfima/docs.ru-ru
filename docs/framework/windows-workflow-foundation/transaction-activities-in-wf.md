---
title: "Действия транзакций в WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Действия транзакций в WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит несколько предоставляемых системой действий для моделирования транзакций, компенсации и отмены.Эти модели программирования позволяют рабочему процессу продолжаться при возникновении изменений в бизнес\-логике и обработке ошибок.[!INCLUDE[crabout](../../../includes/crabout-md.md)]транзакциях, компенсации и отмене см. в разделах [Транзакции](../../../docs/framework/windows-workflow-foundation//workflow-transactions.md), [Компенсация](../../../docs/framework/windows-workflow-foundation//compensation.md) и [Отмена](../../../docs/framework/windows-workflow-foundation//modeling-cancellation-behavior-in-workflows.md).  
  
## Действия транзакций  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Связывает логику отмены в виде действия с главным путем выполнения, который тоже выражен в виде действия.|  
|<xref:System.Activities.Statements.CompensableActivity>|Поддерживает компенсацию своих дочерних действий.|  
|<xref:System.Activities.Statements.Compensate>|Явно вызывает обработчика компенсации объекта <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Явно вызывает обработчика подтверждения объекта <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Указывает границу транзакции.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Область совпадает со временем существования транзакции, инициированной при получении сообщения.Транзакция может быть введена в рабочий процесс с помощью инициирующего сообщения либо создана диспетчером при его получении. **Note:**  <xref:System.ServiceModel.Activities.TransactedReceiveScope> расположен в разделе **Обмен сообщениямиобласти элементов**.|