---
title: Приступая к написанию настраиваемого действия
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 4d9c140ca230750ca1119b33252b1edb8796d458
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776662"
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="66ac9-102">Приступая к написанию настраиваемого действия</span><span class="sxs-lookup"><span data-stu-id="66ac9-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="66ac9-103">В этом образце показано, как определить простое пользовательское действие в XAML.</span><span class="sxs-lookup"><span data-stu-id="66ac9-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="66ac9-104">Действию присваивается имя `Rhyme`, а его логика представляет собой последовательность из трех действий <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="66ac9-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="66ac9-105">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="66ac9-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="66ac9-106">Откройте **Simple.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66ac9-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="66ac9-107">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="66ac9-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66ac9-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="66ac9-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="66ac9-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="66ac9-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="66ac9-110">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="66ac9-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="66ac9-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="66ac9-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`