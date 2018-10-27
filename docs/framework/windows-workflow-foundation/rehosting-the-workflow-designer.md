---
title: Повторное размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: f5964b5c150dbe2a4132d072672a621315270fd5
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452944"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="1cd93-102">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1cd93-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="1cd93-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Может быть повторно размещен в средах за пределами Visual Studio 2012 в рамках создание, изменение и рабочие процессы наблюдения.</span><span class="sxs-lookup"><span data-stu-id="1cd93-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="1cd93-104">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="1cd93-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="1cd93-105">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> приложения в Windows Presentation Foundation (WPF) — Это распространенный сценарий повторного размещения для [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd93-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1cd93-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1cd93-106">In This Section</span></span>
 [<span data-ttu-id="1cd93-107">Задача 1. Создание приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="1cd93-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="1cd93-108">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1cd93-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="1cd93-109">Задача 3. Создание панели элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="1cd93-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="1cd93-110">Поддержка новых возможностей Workflow Foundation 4.5 в отдельно размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1cd93-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="1cd93-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1cd93-111">See Also</span></span>
 [<span data-ttu-id="1cd93-112">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1cd93-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
