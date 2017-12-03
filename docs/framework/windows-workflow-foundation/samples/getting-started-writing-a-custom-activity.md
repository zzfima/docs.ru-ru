---
title: "Приступая к написанию настраиваемого действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0cf8bd0368977b665f2ea412e4debbc1f681e5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="81e50-102">Приступая к написанию настраиваемого действия</span><span class="sxs-lookup"><span data-stu-id="81e50-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="81e50-103">В этом образце показано, как определить простое пользовательское действие в XAML.</span><span class="sxs-lookup"><span data-stu-id="81e50-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="81e50-104">Действию присваивается имя `Rhyme`, а его логика представляет собой последовательность из трех действий <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="81e50-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="81e50-105">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="81e50-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="81e50-106">Откройте **Simple.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81e50-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="81e50-107">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="81e50-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81e50-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="81e50-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="81e50-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="81e50-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="81e50-110">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81e50-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="81e50-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="81e50-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`