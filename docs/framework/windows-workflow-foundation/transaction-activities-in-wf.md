---
title: "Действия транзакций в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6c72a54d596468e1ae6948ff9f177e026458628
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="05b3e-102">Действия транзакций в WF</span><span class="sxs-lookup"><span data-stu-id="05b3e-102">Transaction Activities in WF</span></span>
<span data-ttu-id="05b3e-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит несколько предоставляемых системой действий для моделирования транзакций, компенсации и отмены.</span><span class="sxs-lookup"><span data-stu-id="05b3e-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="05b3e-104">Эти модели программирования позволяют рабочему процессу продолжаться при возникновении изменений в бизнес-логике и обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="05b3e-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="05b3e-105">транзакций, компенсации и отмены, в разделе [транзакции](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [компенсации](../../../docs/framework/windows-workflow-foundation/compensation.md), и [отмены](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="05b3e-105"> transactions, compensation, and cancellation, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Compensation](../../../docs/framework/windows-workflow-foundation/compensation.md), and [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="05b3e-106">Действия транзакций</span><span class="sxs-lookup"><span data-stu-id="05b3e-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="05b3e-107">Связывает логику отмены в виде действия с главным путем выполнения, который тоже выражен в виде действия.</span><span class="sxs-lookup"><span data-stu-id="05b3e-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="05b3e-108">Поддерживает компенсацию своих дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="05b3e-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="05b3e-109">Явно вызывает обработчика компенсации объекта <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="05b3e-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="05b3e-110">Явно вызывает обработчика подтверждения объекта <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="05b3e-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="05b3e-111">Указывает границу транзакции.</span><span class="sxs-lookup"><span data-stu-id="05b3e-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="05b3e-112">Область совпадает со временем существования транзакции, инициированной при получении сообщения.</span><span class="sxs-lookup"><span data-stu-id="05b3e-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="05b3e-113">Транзакция может быть введена в рабочий процесс с помощью инициирующего сообщения либо создана диспетчером при его получении.</span><span class="sxs-lookup"><span data-stu-id="05b3e-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="05b3e-114">**Примечание:** <xref:System.ServiceModel.Activities.TransactedReceiveScope> находится в папке **обмен сообщениями** раздел **элементов**.</span><span class="sxs-lookup"><span data-stu-id="05b3e-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
