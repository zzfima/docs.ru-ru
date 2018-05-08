---
title: Действия транзакций в WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: f2709601fc4fd88a1c5223a5a3e97e139ceca954
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-activities-in-wf"></a>Действия транзакций в WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит несколько предоставляемых системой действий для моделирования транзакций, компенсации и отмены. Эти модели программирования позволяют рабочему процессу продолжаться при возникновении изменений в бизнес-логике и обработке ошибок. Дополнительные сведения о транзакциях, компенсации и отмены см. в разделе [транзакции](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [компенсации](../../../docs/framework/windows-workflow-foundation/compensation.md), и [отмены](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Действия транзакций  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Связывает логику отмены в виде действия с главным путем выполнения, который тоже выражен в виде действия.|  
|<xref:System.Activities.Statements.CompensableActivity>|Поддерживает компенсацию своих дочерних действий.|  
|<xref:System.Activities.Statements.Compensate>|Явно вызывает обработчика компенсации объекта <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Явно вызывает обработчика подтверждения объекта <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Указывает границу транзакции.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Область совпадает со временем существования транзакции, инициированной при получении сообщения. Транзакция может быть введена в рабочий процесс с помощью инициирующего сообщения либо создана диспетчером при его получении. **Примечание:** <xref:System.ServiceModel.Activities.TransactedReceiveScope> находится в папке **обмен сообщениями** раздел **элементов**.|
