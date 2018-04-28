---
title: Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64c0e4b6e84f442b6e34f0cbd442ae04e2a9d0b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="52a1b-102">Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="52a1b-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="52a1b-103"><xref:System.Activities.Statements.Interop> Действия позволяет выполнять действие .NET Framework 3.0 Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="52a1b-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="52a1b-104">В этом образце показано, как использовать действие <xref:System.Activities.Statements.Interop> для передачи строки в качестве аргумента для пользовательского действия [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52a1b-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="52a1b-105">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="52a1b-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="52a1b-106">Используя [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], откройте файл решения SimpleInterop.sln.</span><span class="sxs-lookup"><span data-stu-id="52a1b-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="52a1b-107">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="52a1b-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="52a1b-108">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="52a1b-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52a1b-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="52a1b-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="52a1b-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="52a1b-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="52a1b-111">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="52a1b-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="52a1b-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="52a1b-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="52a1b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="52a1b-113">See Also</span></span>
