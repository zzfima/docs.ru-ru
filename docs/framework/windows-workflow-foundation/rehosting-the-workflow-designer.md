---
title: Повторное размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 29b3a205e97ad84ef8d0ef878b41c02058a8e5dc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703742"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="967a9-102">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="967a9-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="967a9-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Может быть повторно размещен в средах за пределами Visual Studio 2012 в рамках создание, изменение и рабочие процессы наблюдения.</span><span class="sxs-lookup"><span data-stu-id="967a9-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="967a9-104">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="967a9-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="967a9-105">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> приложения в Windows Presentation Foundation (WPF) — Это распространенный сценарий повторного размещения для [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="967a9-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="967a9-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="967a9-106">In This Section</span></span>
 [<span data-ttu-id="967a9-107">Упражнение 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="967a9-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="967a9-108">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="967a9-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="967a9-109">Задача 3. Создание элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="967a9-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="967a9-110">Поддержка новых возможностей Workflow Foundation 4.5 в отдельно размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="967a9-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="967a9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="967a9-111">See also</span></span>
- [<span data-ttu-id="967a9-112">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="967a9-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
