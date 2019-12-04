---
title: Повторное размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 4b89c84d6761fa1e16bc17794885f64086a920f8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716726"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="76be4-102">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="76be4-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="76be4-103">Конструктор рабочих процессов Windows можно повторно разместить в средах, находящихся за пределами Visual Studio 2012, в целях создания, изменения и мониторинга рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="76be4-103">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="76be4-104">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="76be4-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="76be4-105">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> в приложении Windows Presentation Foundation (WPF) — это распространенный сценарий повторного размещения для конструктор рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="76be4-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="76be4-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="76be4-106">In This Section</span></span>
 [<span data-ttu-id="76be4-107">Задача 1. Создание приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="76be4-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="76be4-108">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="76be4-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="76be4-109">Задача 3. Создание панели элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="76be4-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="76be4-110">Поддержка новых возможностей Workflow Foundation 4.5 в отдельно размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="76be4-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="76be4-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="76be4-111">See also</span></span>

- [<span data-ttu-id="76be4-112">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="76be4-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
