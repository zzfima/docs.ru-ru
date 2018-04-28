---
title: Образец компенсируемого действия
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba81d0eb32305e8ea099a291bef612639915292f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="47e03-102">Образец компенсируемого действия</span><span class="sxs-lookup"><span data-stu-id="47e03-102">Compensable Activity Sample</span></span>
<span data-ttu-id="47e03-103">В этом образце демонстрируется использование действия `CompensableActivity` для определения задания, необходимого для выполнения в ходе этого действия при нормальном течении процесса, и задания, необходимого для выполнения компенсации этого действия, если это потребуется позднее.</span><span class="sxs-lookup"><span data-stu-id="47e03-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="47e03-104">В первой части примера показано, как единицы подлежащего компенсации задания можно определить в Windows Workflow Foundation (WF) с помощью `CompensableActivity` действия и способ их исполнения при успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="47e03-104">The first part of the sample shows how units of compensable work can be defined in Windows Workflow Foundation (WF) using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="47e03-105">Во второй части образца показано, как те же единицы подлежащего компенсации задания автоматически проводят компенсацию при возникновении неожиданного события и при отмене экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="47e03-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="47e03-106">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="47e03-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="47e03-107">Откройте в среде Visual Studio 2010 решение CompensableActivity.sln.</span><span class="sxs-lookup"><span data-stu-id="47e03-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="47e03-108">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="47e03-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="47e03-109">Запустите приложение, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="47e03-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47e03-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="47e03-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47e03-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="47e03-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47e03-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="47e03-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47e03-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="47e03-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`