---
title: "Повторное размещение конструктора рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5ca7eec49dec0e9b8896b31147a3cd40ffeef5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="3fa08-102">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3fa08-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="3fa08-103">Для создания, изменения и наблюдения за рабочими процессами [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] может быть повторно размещен в среде вне [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fa08-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="3fa08-104">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="3fa08-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="3fa08-105">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> внутри приложения [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] - это очень распространенный сценарий повторного размещения для [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fa08-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fa08-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="3fa08-106">In This Section</span></span>  
 [<span data-ttu-id="3fa08-107">Задача 1. Создание приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="3fa08-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="3fa08-108">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3fa08-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="3fa08-109">Задача 3. Создание панели элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="3fa08-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="3fa08-110">Поддержка новых возможностей Workflow Foundation 4.5 в отдельно размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3fa08-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fa08-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3fa08-111">See Also</span></span>  
 [<span data-ttu-id="3fa08-112">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3fa08-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
