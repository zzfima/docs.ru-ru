---
title: Получение GetWorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: f8bd3205f5b7a4b3bae5203dc90a3c393cedcbdd
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989374"
---
# <a name="get-workflowinstanceid"></a><span data-ttu-id="d02fd-102">Получение GetWorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d02fd-102">Get WorkflowInstanceId</span></span>
<span data-ttu-id="d02fd-103">В этом образце показывается, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d02fd-103">This sample demonstrates how to use the custom activity, `GetWorkflowInstanceId` to return the workflow instance ID.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d02fd-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="d02fd-104">Demonstrates</span></span>  
 <span data-ttu-id="d02fd-105">Разработка пользовательского действия, метод доступа к экземпляру рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d02fd-105">Custom activity development, how to access the workflow instance.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d02fd-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="d02fd-106">Discussion</span></span>  
 <span data-ttu-id="d02fd-107">Для получения идентификатора экземпляра выполняющегося рабочего процесса необходимо написать код.</span><span class="sxs-lookup"><span data-stu-id="d02fd-107">Getting the instance ID of a running workflow requires writing code.</span></span> <span data-ttu-id="d02fd-108">Если необходимо написать полностью декларативный рабочий процесс, то требуется действие, возвращающее идентификатор экземпляра рабочего процесса, что позволит ссылаться на это действие в рабочем процессе в полностью декларативной манере.</span><span class="sxs-lookup"><span data-stu-id="d02fd-108">If you want to write a fully-declarative workflow, then you need an activity that can return the workflow instance ID so that the activity can be referenced in the workflow to provide a fully-declarative workflow authoring experience.</span></span> <span data-ttu-id="d02fd-109">Доступ к идентификатору экземпляра требуется во многих случаях, например при ведении журнала с целью аудита или при осуществлении корреляции на уровне приложения с предоставлением идентификатора экземпляра клиенту для последующего создания ассоциации (например, при использовании этого действия в действии SendReply).</span><span class="sxs-lookup"><span data-stu-id="d02fd-109">Many scenarios require access to the instance ID: a few examples are for logging or auditing purposes or for doing application-level correlation by providing the instance ID back to a client for future association (for example, by using this activity inside a SendReply activity).</span></span>  
  
 <span data-ttu-id="d02fd-110">Действие `GetWorkflowInstanceId` реализуется как <xref:System.Activities.CodeActivity%601>, поскольку оно должно возвращать значение типа <xref:System.Guid> и должно иметь доступ к контексту <xref:System.Activities.CodeActivityContext> для получения идентификатора экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d02fd-110">`GetWorkflowInstanceId` is implemented as a <xref:System.Activities.CodeActivity%601> because it must return a value of type <xref:System.Guid>, and it must have access to the <xref:System.Activities.CodeActivityContext> for getting the workflow’s instance ID.</span></span> <span data-ttu-id="d02fd-111">Его реализация производится достаточно просто.</span><span class="sxs-lookup"><span data-stu-id="d02fd-111">Its implementation is fairly basic.</span></span>  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> <span data-ttu-id="d02fd-112">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d02fd-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d02fd-113">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d02fd-113">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="d02fd-114">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры.</span><span class="sxs-lookup"><span data-stu-id="d02fd-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d02fd-115">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d02fd-115">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
