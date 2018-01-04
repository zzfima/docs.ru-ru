---
title: "Определение времени выполнения рабочего процесса с помощью трассировки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2687d045db28974e99b2f2b6a3222924a520720
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a><span data-ttu-id="1a245-102">Определение времени выполнения рабочего процесса с помощью трассировки</span><span class="sxs-lookup"><span data-stu-id="1a245-102">Determining Workflow Execution Duration Using Tracing</span></span>
<span data-ttu-id="1a245-103">В этом разделе демонстрируется, как определить время, которое требуется для выполнения успешно созданного резидентного рабочего процесса с помощью трассировки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1a245-103">This topic demonstrates how to determine the time it takes for a successfully completed, self-hosted workflow to execute by using workflow tracing.</span></span>  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a><span data-ttu-id="1a245-104">Определение продолжительности выполнения приложения рабочего процесса с помощью трассировки рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1a245-104">To determine workflow application execution duration by using workflow tracing</span></span>  
  
1.  <span data-ttu-id="1a245-105">Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a245-105">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  <span data-ttu-id="1a245-106">Выберите **файл**, **новый**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="1a245-106">Select **File**, **New**, **Project**.</span></span>  <span data-ttu-id="1a245-107">В разделе **C#**выберите **рабочего процесса** узла.</span><span class="sxs-lookup"><span data-stu-id="1a245-107">Under **C#**, select the **Workflow** node.</span></span>  <span data-ttu-id="1a245-108">Выберите **консольное приложение рабочего процесса** из списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1a245-108">Select **Workflow Console Application** from the list of templates.</span></span>  <span data-ttu-id="1a245-109">Имя для нового проекта `WorkflowDurationTracing` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a245-109">Name the new project `WorkflowDurationTracing` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="1a245-110">Откройте файл Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="1a245-110">Open Workflow1.xaml.</span></span>  <span data-ttu-id="1a245-111">Перетащите действие <xref:System.Activities.Statements.Delay> в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a245-111">Drag a <xref:System.Activities.Statements.Delay> activity onto the designer surface.</span></span> <span data-ttu-id="1a245-112">Свойству «Duration» действия присвойте значение 00:00:10 (десять секунд).</span><span class="sxs-lookup"><span data-stu-id="1a245-112">Assign the value 00:00:10 (ten seconds) to the Duration property of the activity.</span></span>  
  
3.  <span data-ttu-id="1a245-113">Откройте средство просмотра событий, щелкнув **запустить**, **запуска**и введя `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="1a245-113">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
4.  <span data-ttu-id="1a245-114">Если вы еще не включена трассировка рабочего процесса, разверните **журналы приложений и служб**, **Microsoft**, **Windows**, **сервер приложений-приложения** .</span><span class="sxs-lookup"><span data-stu-id="1a245-114">If you haven’t enabled workflow tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="1a245-115">Выберите **представление**, **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="1a245-115">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="1a245-116">Щелкните правой кнопкой мыши **отладки** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="1a245-116">Right-click **Debug** and select **Enable Log**.</span></span> <span data-ttu-id="1a245-117">Оставьте окно просмотра событий открытым, чтобы можно было просмотреть трассировки после запуска рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1a245-117">Leave Event Viewer open so that traces can be viewed after the workflow is run.</span></span>  
  
5.  <span data-ttu-id="1a245-118">Выполните приложение рабочего процесса, нажав CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="1a245-118">Execute the workflow application by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="1a245-119">В окне просмотра событий найдите последнее событие с идентификатором 1009 и сообщение, похожее на следующее.</span><span class="sxs-lookup"><span data-stu-id="1a245-119">In Event Viewer, find a recent event with ID 1009 and a message similar to the following.</span></span> <span data-ttu-id="1a245-120">Запишите время регистрации сообщения.</span><span class="sxs-lookup"><span data-stu-id="1a245-120">Make a note of the time that the message was logged.</span></span>  
  
 <span data-ttu-id="1a245-121">**Родительское действие '', DisplayName: '', InstanceId: '' запланировало дочернее действие с ' WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: "1".**</span><span class="sxs-lookup"><span data-stu-id="1a245-121">**Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span></span>  
  
7.  <span data-ttu-id="1a245-122">Найдите еще одно последнее событие с идентификатором 1001 и сообщение, похожее на следующее.</span><span class="sxs-lookup"><span data-stu-id="1a245-122">Find another recent event with ID 1001 and a message similar to the following.</span></span>  <span data-ttu-id="1a245-123">Вычтите время предыдущего сообщения из времени регистрации данного сообщения, чтобы определить продолжительность выполнения рабочего процесса, которая должна составить приблизительно 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="1a245-123">Subtract the previous message time from this message’s Logged value to determine workflow execution duration, which should be around 10 seconds.</span></span>  
  
 <span data-ttu-id="1a245-124">**Элемент WorkflowInstance с идентификатором: '1bbac57b-3322-498e-9e27-8833fda3a5bf' завершил работу в состояние Closed.**</span><span class="sxs-lookup"><span data-stu-id="1a245-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' has completed in the Closed state.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a245-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1a245-125">See Also</span></span>  
 [<span data-ttu-id="1a245-126">Трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1a245-126">Workflow Tracing</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [<span data-ttu-id="1a245-127">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="1a245-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="1a245-128">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="1a245-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
