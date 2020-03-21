---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142905"
---
# <a name="activity-library"></a><span data-ttu-id="ccdd2-102">Библиотека действий</span><span class="sxs-lookup"><span data-stu-id="ccdd2-102">Activity Library</span></span>
<span data-ttu-id="ccdd2-103">Этот раздел содержит образцы, демонстрирующие передовые пользовательские действия в Фонде рабочего процесса Windows (WF).</span><span class="sxs-lookup"><span data-stu-id="ccdd2-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccdd2-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ccdd2-104">In This Section</span></span>

 [<span data-ttu-id="ccdd2-105">Настраиваемое действие SendMail</span><span class="sxs-lookup"><span data-stu-id="ccdd2-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="ccdd2-106">В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="ccdd2-107">Параллельное действие ForEach с ограничением</span><span class="sxs-lookup"><span data-stu-id="ccdd2-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="ccdd2-108">Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="ccdd2-109">Действия доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="ccdd2-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="ccdd2-110">Демонстрирует, как создавать действия, позволяющие получить доступ к базам данных для получения или изменения информации и использования [ADO.NET](../../data/adonet/index.md) для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>  
  
 [<span data-ttu-id="ccdd2-111">Реализованное действие политики в .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ccdd2-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="ccdd2-112">Демонстрирует, как деятельность ExternalizedPolicy4 позволяет выполнять существующие объекты Windows Workflow Foundation в .NET <xref:System.Workflow.Activities.Rules.RuleSet> Framework 3.5 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 3.5) в Фонде рабочего процесса Windows в (WF 4.5) непосредственно с помощью движка правил, поставляемого в WF 3.5.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in .NET Framework 3.5 (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span>
  
 [<span data-ttu-id="ccdd2-113">Неуниверсальное действие ForEach</span><span class="sxs-lookup"><span data-stu-id="ccdd2-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="ccdd2-114">Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="ccdd2-115">Неуниверсальное действие ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="ccdd2-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="ccdd2-116">Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="ccdd2-117">Получение WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ccdd2-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="ccdd2-118">Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ccdd2-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
