---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e8777d0068e6cca9c9324a6fd2668e6ff9e9da7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778966"
---
# <a name="activity-library"></a><span data-ttu-id="37773-102">Библиотека действий</span><span class="sxs-lookup"><span data-stu-id="37773-102">Activity Library</span></span>
<span data-ttu-id="37773-103">Этот раздел содержит образцы, демонстрирующие дополнительные пользовательские действия в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="37773-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37773-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="37773-104">In This Section</span></span>

 [<span data-ttu-id="37773-105">Настраиваемое действие SendMail</span><span class="sxs-lookup"><span data-stu-id="37773-105">SendMail Custom Activity</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 <span data-ttu-id="37773-106">В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="37773-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="37773-107">Параллельное действие ForEach с ограничением</span><span class="sxs-lookup"><span data-stu-id="37773-107">Throttled Parallel ForEach</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 <span data-ttu-id="37773-108">Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.</span><span class="sxs-lookup"><span data-stu-id="37773-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="37773-109">Действия доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="37773-109">Database Access Activities</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 <span data-ttu-id="37773-110">Демонстрирует создание действия, которые позволяют получить доступ к базам данных, чтобы вернуть или изменить сведения, а также использовать [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="37773-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="37773-111">Реализованное действие политики в .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="37773-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="37773-112">Демонстрирует, как действия externalizedpolicy4 можно выполнять существующие Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил это в комплект поставки WF 3.5.</span><span class="sxs-lookup"><span data-stu-id="37773-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="37773-113">Неуниверсальное действие ForEach</span><span class="sxs-lookup"><span data-stu-id="37773-113">Non-Generic ForEach</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 <span data-ttu-id="37773-114">Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="37773-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="37773-115">Неуниверсальное действие ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="37773-115">Non-Generic ParallelForEach</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 <span data-ttu-id="37773-116">Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="37773-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="37773-117">Получение WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="37773-117">Get WorkflowInstanceId</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 <span data-ttu-id="37773-118">Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="37773-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
