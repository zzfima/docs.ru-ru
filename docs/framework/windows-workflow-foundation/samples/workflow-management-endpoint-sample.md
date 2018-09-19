---
title: Образец конечной точки управления рабочим процессом
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 3d99cbef20895381f5e40ee939e1d94a409f1391
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46287573"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="4d789-102">Образец конечной точки управления рабочим процессом</span><span class="sxs-lookup"><span data-stu-id="4d789-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="4d789-103">Этот образец показывает, как можно использовать конечную точку управления рабочего процесса для создания и запуска рабочих процессов как локально, так и удаленно.</span><span class="sxs-lookup"><span data-stu-id="4d789-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="4d789-104">В следующем образце показано создание узла конечной точки управления, и клиентов, вызывающих конечную точку управления для создания и запуска экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4d789-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="4d789-105">Рабочий процесс не является службой.</span><span class="sxs-lookup"><span data-stu-id="4d789-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="4d789-106">На стороне службы образца рабочий процесс размещен с помощью WorkflowServiceHost, а также добавлен WorkflowControlEndpoint, что позволяет клиентам выполнять операции управления (приостановка, запуск и т. д.).</span><span class="sxs-lookup"><span data-stu-id="4d789-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="4d789-107">Добавлено также определяемое пользователем создание конечной точки CreationEndpoint, что позволяет создать рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="4d789-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="4d789-108">Затем служба использует эти конечные точки для запуска рабочего процесса в приостановленном состоянии, а после этого возобновляет рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="4d789-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="4d789-109">Клиент выполняет те же операции, но в коде клиента.</span><span class="sxs-lookup"><span data-stu-id="4d789-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="4d789-110">Для Дополнительные сведения об этих интерфейсов, см. в разделе [конечная точка управления рабочим процессом](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) и [как: размещение не являющегося службой рабочего процесса в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="4d789-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="4d789-111">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4d789-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="4d789-112">Запустите среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4d789-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="4d789-113">Откройте решение ManagementEndpoint.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d789-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="4d789-114">Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="4d789-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="4d789-115">Запустите приложение ManagementEndpoint.exe.</span><span class="sxs-lookup"><span data-stu-id="4d789-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="4d789-116">Запустите приложение Client.exe.</span><span class="sxs-lookup"><span data-stu-id="4d789-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d789-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4d789-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4d789-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4d789-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4d789-119">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="4d789-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4d789-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4d789-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`