---
title: Закладка возобновления для конечной точки WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 3c1a3421c87d18e695790cfb3a1f066600748ce9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619511"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="d36aa-102">Закладка возобновления для конечной точки WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="d36aa-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="d36aa-103">В этом образце показано использование <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> с <xref:System.ServiceModel.Activities.WorkflowServiceHost> для создания экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d36aa-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d36aa-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="d36aa-104">Demonstrates</span></span>  
 <span data-ttu-id="d36aa-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="d36aa-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d36aa-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="d36aa-106">Discussion</span></span>  
 <span data-ttu-id="d36aa-107">Этот образец использует <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для создания экземпляра рабочего процесса, размещенного с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d36aa-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="d36aa-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> - точка расширения для <xref:System.ServiceModel.Activities.WorkflowServiceHost>, которую можно использовать в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="d36aa-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="d36aa-109">Создание новых экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d36aa-109">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="d36aa-110">Возобновление закладок в экземпляре рабочего процесса, размещенного на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d36aa-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="d36aa-111">Включенный образец конечной точки предоставляет контракт на выполнение операций, которые создают рабочий процесс и возвращают идентификатор экземпляра или создают экземпляр с конкретным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="d36aa-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="d36aa-112">В приведенном образце консольного приложения создается экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost> с базовым определением рабочего процесса, и к узлу добавляется конечная точка `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d36aa-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="d36aa-113">Затем в конечной точке вызывается операция `Create`, чтобы создать новый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d36aa-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d36aa-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d36aa-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d36aa-115">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="d36aa-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="d36aa-116">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="d36aa-116">Run the application.</span></span> <span data-ttu-id="d36aa-117">При создании экземпляра рабочего процесса на консоли `CreationEndpoint` выводится сообщение, содержащее идентификатор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d36aa-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="d36aa-118">Сообщение «Hello World!»</span><span class="sxs-lookup"><span data-stu-id="d36aa-118">The message "Hello World!"</span></span> <span data-ttu-id="d36aa-119">выводится после успешного возобновления закладки рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="d36aa-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d36aa-120">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d36aa-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d36aa-121">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d36aa-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d36aa-122">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="d36aa-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d36aa-123">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d36aa-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
