---
title: Bookmarks2
ms.date: 03/30/2017
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
ms.openlocfilehash: 6bcc4e27566b9c8553e0792558c281a6b1f1caf4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528994"
---
# <a name="bookmarks"></a><span data-ttu-id="7e19a-102">Закладки</span><span class="sxs-lookup"><span data-stu-id="7e19a-102">Bookmarks</span></span>
<span data-ttu-id="7e19a-103">В этом образце показано, как разработать настраиваемое действие, которое создает закладку для получения внешних входных данных.</span><span class="sxs-lookup"><span data-stu-id="7e19a-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="7e19a-104">В образец также входит простое консольное приложение, которое использует настраиваемое действие в рабочем процессе и показывает, как обнаруживать и возобновлять закладки, связанные с выполняющимся экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7e19a-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> <span data-ttu-id="7e19a-105">Дополнительные сведения о закладках см. в разделе [закладки](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="7e19a-105">For more information about bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7e19a-106">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="7e19a-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7e19a-107">Откройте образец решения Bookmarks.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e19a-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e19a-108">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="7e19a-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7e19a-109">Чтобы запустить образец, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="7e19a-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7e19a-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e19a-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7e19a-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7e19a-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7e19a-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="7e19a-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e19a-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7e19a-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`