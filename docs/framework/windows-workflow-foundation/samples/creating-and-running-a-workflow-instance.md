---
title: "Создание и запуск экземпляра рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d6dd2f27a6db9770231a5c947c98614d4f6f175
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="00557-102">Создание и запуск экземпляра рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="00557-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="00557-103">В этом образце показано, как выполнить экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="00557-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="00557-104">Здесь показано синхронное и асинхронное выполнение.</span><span class="sxs-lookup"><span data-stu-id="00557-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="00557-105">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="00557-105">Demonstrates</span></span>  
 <span data-ttu-id="00557-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="00557-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="00557-107">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="00557-107">Discussion</span></span>  
 <span data-ttu-id="00557-108">В первой части образца используется метод <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="00557-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="00557-109">Это основной способ выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="00557-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="00557-110">Рабочие процессы, запускаемые методом <xref:System.Activities.WorkflowInvoker.Invoke%2A>, выполняются синхронно.</span><span class="sxs-lookup"><span data-stu-id="00557-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="00557-111">Во второй части образца используется класс <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="00557-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="00557-112">Класс <xref:System.Activities.WorkflowApplication> предоставляет дополнительные возможности управления каждым экземпляром, включая возможность взаимодействия с выполняющимся рабочим процессом и возможность асинхронного выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="00557-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00557-113">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="00557-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="00557-114">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="00557-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="00557-115">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00557-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="00557-116">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="00557-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="00557-117">См. также</span><span class="sxs-lookup"><span data-stu-id="00557-117">See Also</span></span>  
 [<span data-ttu-id="00557-118">Использование WorkflowInvoker и WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="00557-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
