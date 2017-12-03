---
title: "Использование AsyncOperationContext в образце действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5fce0160f98b5af5476b5e647763d79e94fb4e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="05ea2-102">Использование AsyncOperationContext в образце действия</span><span class="sxs-lookup"><span data-stu-id="05ea2-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="05ea2-103">В этом образце показано, как разработать настраиваемое действие <xref:System.Activities.CodeActivity>, которое использует <xref:System.Activities.AsyncCodeActivityContext> для асинхронного выполнения работы вне рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05ea2-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="05ea2-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="05ea2-104">Sample Details</span></span>  
 <span data-ttu-id="05ea2-105">В данном образце действия используются методы <xref:System.IO.FileStream.BeginWrite%2A> и <xref:System.IO.FileStream.EndWrite%2A> в классе <xref:System.IO.FileStream> для асинхронной записи данных в файл.</span><span class="sxs-lookup"><span data-stu-id="05ea2-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="05ea2-106">Предлагаемый здесь шаблон может быть адаптирован для использования с другими асинхронными методами.</span><span class="sxs-lookup"><span data-stu-id="05ea2-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="05ea2-107">Во время выполнения асинхронной операции могут выполняться другие действия рабочего процесса, но сам рабочий процесс не может быть сохранен.</span><span class="sxs-lookup"><span data-stu-id="05ea2-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05ea2-108">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="05ea2-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="05ea2-109">Откройте образец решения Async.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05ea2-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="05ea2-110">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="05ea2-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05ea2-111">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="05ea2-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="05ea2-112">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="05ea2-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="05ea2-113">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05ea2-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05ea2-114">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="05ea2-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`