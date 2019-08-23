---
title: Арбитр закладок для конечной точки WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 017c5f959ed109ffe9b5e5c4bf2b9de9d04fdcdb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964943"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a><span data-ttu-id="bcbed-102">Арбитр закладок для конечной точки WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="bcbed-102">Bookmark Resolver for WorkflowHostingEndpoint</span></span>
<span data-ttu-id="bcbed-103">В этом образце показано использование <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> с <xref:System.ServiceModel.Activities.WorkflowServiceHost> для создания экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcbed-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bcbed-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="bcbed-104">Demonstrates</span></span>  
 <span data-ttu-id="bcbed-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="bcbed-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bcbed-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="bcbed-106">Discussion</span></span>  
 <span data-ttu-id="bcbed-107">Этот образец использует <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для создания экземпляров рабочих процессов, размещенных с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="bcbed-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create workflow instances hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="bcbed-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> - точка расширения для <xref:System.ServiceModel.Activities.WorkflowServiceHost>, которую можно использовать в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="bcbed-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="bcbed-109">Создание новых экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcbed-109">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="bcbed-110">Возобновление закладок в экземпляре рабочего процесса, размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="bcbed-110">Resuming bookmarks on workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="bcbed-111">В приведенном образце точки расширения представлен контракт на выполнение операций, создающих рабочий процесс и возвращающих идентификатор экземпляра или создающих экземпляр с конкретным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="bcbed-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and returns the instance ID or creates an instance with a specific ID.</span></span> <span data-ttu-id="bcbed-112">В приведенном образце консольного приложения создается экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost>, определяющий рабочий процесс, и к узлу добавляется `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="bcbed-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a workflow definition and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="bcbed-113">Затем в конечной точке вызывается операция `Create`, чтобы создать новый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcbed-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bcbed-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="bcbed-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bcbed-115">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="bcbed-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="bcbed-116">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="bcbed-116">Run the application.</span></span> <span data-ttu-id="bcbed-117">При создании экземпляра рабочего процесса на консоли `CreationEndpoint` выводится сообщение, содержащее идентификатор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bcbed-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="bcbed-118">Сообщение "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="bcbed-118">The message "Hello World!"</span></span> <span data-ttu-id="bcbed-119">распечатывается экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bcbed-119">is printed by the workflow instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bcbed-120">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bcbed-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bcbed-121">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bcbed-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bcbed-122">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры.</span><span class="sxs-lookup"><span data-stu-id="bcbed-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bcbed-123">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="bcbed-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
