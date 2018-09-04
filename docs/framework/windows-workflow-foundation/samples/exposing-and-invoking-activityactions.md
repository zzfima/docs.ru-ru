---
title: Предоставление и вызов действий ActivityActions
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: f36d88fc54e5150927113ed8825fbccad84129d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520127"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="0259e-102">Предоставление и вызов действий ActivityActions</span><span class="sxs-lookup"><span data-stu-id="0259e-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="0259e-103">В этом образце показано, как разработать настраиваемое действие, имеющее <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="0259e-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="0259e-104">Также демонстрируется, как использовать данное действие, обеспечив реализацию <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="0259e-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="0259e-105"><xref:System.Activities.ActivityAction> Позволяет создателям действий предоставлять «дыры» с определенными сигнатурами которых пользователи действия могут подключить пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="0259e-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="0259e-106">Например <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` действия (совершающее коллекцию элементов), имеет <xref:System.Activities.ActivityAction> , позволяет пользователю действия подключить поведение, работающее с текущим элементом итерации.</span><span class="sxs-lookup"><span data-stu-id="0259e-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0259e-107">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0259e-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0259e-108">Откройте **ActivityAction.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0259e-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0259e-109">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="0259e-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0259e-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0259e-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0259e-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0259e-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0259e-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="0259e-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0259e-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0259e-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`