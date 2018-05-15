---
title: Повторное размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: e4e061c078626a90641f84b5ea0875f63bb42f9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="2bd94-102">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2bd94-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="2bd94-103">Для создания, изменения и наблюдения за рабочими процессами [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] может быть повторно размещен в среде вне [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd94-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="2bd94-104">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="2bd94-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="2bd94-105">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> внутри Windows Presentation Foundation (WPF) приложение является распространенный сценарий повторного размещения для [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd94-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bd94-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2bd94-106">In This Section</span></span>  
 [<span data-ttu-id="2bd94-107">Задача 1. Создание приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="2bd94-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="2bd94-108">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2bd94-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="2bd94-109">Задача 3. Создание панели элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="2bd94-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="2bd94-110">Поддержка новых возможностей Workflow Foundation 4.5 в отдельно размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2bd94-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="2bd94-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2bd94-111">See Also</span></span>  
 [<span data-ttu-id="2bd94-112">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2bd94-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
