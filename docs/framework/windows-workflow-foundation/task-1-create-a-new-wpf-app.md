---
title: "Задача 1. Создание нового приложения Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a207b09ff7124bb161678627f365a6fa4021a38d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="3e27e-102">Задача 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="3e27e-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="3e27e-103">В данной задаче необходимо создать пустое приложение [!INCLUDE[avalon1](../../../includes/avalon1-md.md)], используя шаблон WPF Application Visual Studio, и добавить ссылки на соответствующие сборки рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e27e-103">In this task, you will create an empty [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="3e27e-104">Создание проекта приложения WPF</span><span class="sxs-lookup"><span data-stu-id="3e27e-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="3e27e-105">Откройте [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] и на **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3e27e-106">В **новый проект** диалогового окна выберите либо **Visual C#** или **Visual Basic** из **установленные шаблоны** на левой стороне панели поле.</span><span class="sxs-lookup"><span data-stu-id="3e27e-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="3e27e-107">Если язык не отображается, разверните узел **другие языки**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="3e27e-108">Выберите **Windows** в **установленные шаблоны** области.</span><span class="sxs-lookup"><span data-stu-id="3e27e-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="3e27e-109">Убедитесь, что в верхней области (значение по умолчанию) **.NET Framework 4** был выбранного в раскрывающемся списке, а затем выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="3e27e-110">Задайте имя проекта для **HostingApplication** в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="3e27e-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="3e27e-111">Задайте имя решения **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="3e27e-112">Нажмите кнопку **ОК** Создание проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="3e27e-112">Click **OK** to create the application project.</span></span> [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]<span data-ttu-id="3e27e-113"> создает основной пользовательский интерфейс WPF для приложения и включает в него соответствующий XAML и файлы с фоновым кодом.</span><span class="sxs-lookup"><span data-stu-id="3e27e-113"> creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="3e27e-114">Добавьте ссылки на **WorkflowModel** сборки.</span><span class="sxs-lookup"><span data-stu-id="3e27e-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="3e27e-115">Для этого в **обозревателе решений**, щелкните правой кнопкой мыши **HostingApplication** проект и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="3e27e-116">В **добавить ссылку** диалоговое окно, нажмите кнопку **.NET** удерживайте нажатой клавишу CTRL, выберите следующие сборки и нажмите кнопку **ОК**:</span><span class="sxs-lookup"><span data-stu-id="3e27e-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="3e27e-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="3e27e-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="3e27e-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="3e27e-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="3e27e-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="3e27e-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="3e27e-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e27e-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="3e27e-121">В разделе [задача 2: размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) чтобы узнать, как разместить полотно конструктора в конструкторе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3e27e-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e27e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3e27e-122">See Also</span></span>  
 [<span data-ttu-id="3e27e-123">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3e27e-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="3e27e-124">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3e27e-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
