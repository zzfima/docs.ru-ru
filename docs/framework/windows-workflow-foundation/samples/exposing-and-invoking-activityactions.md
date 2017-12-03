---
title: "Предоставление и вызов действий ActivityActions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27b5ea6c4a4afea1bc3cb9f5a79d22850d2a4143
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="13296-102">Предоставление и вызов действий ActivityActions</span><span class="sxs-lookup"><span data-stu-id="13296-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="13296-103">В этом образце показано, как разработать настраиваемое действие, имеющее <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="13296-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="13296-104">Также демонстрируется, как использовать данное действие, обеспечив реализацию <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="13296-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="13296-105"><xref:System.Activities.ActivityAction> Позволяет создателям действий предоставлять «дыры» с определенными сигнатурами которых пользователи действия могут подключить пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="13296-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="13296-106">Например <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` действия (совершающее операции с коллекцией элементов) имеет <xref:System.Activities.ActivityAction> , позволяет пользователю действия подключить поведение, работающее с текущим элементом итерации.</span><span class="sxs-lookup"><span data-stu-id="13296-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="13296-107">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="13296-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="13296-108">Откройте **ActivityAction.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13296-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="13296-109">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="13296-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13296-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13296-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13296-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="13296-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="13296-112">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13296-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13296-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="13296-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`