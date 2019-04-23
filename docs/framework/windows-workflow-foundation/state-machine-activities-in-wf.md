---
title: Действия конечного автомата в WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120917"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="25044-102">Действия конечного автомата в WF</span><span class="sxs-lookup"><span data-stu-id="25044-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="25044-103">предусматривает несколько системных действий и конструкторов действий для создания рабочих процессов конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="25044-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="25044-104">Выполняет включенные действия на основе известной парадигмы конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="25044-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="25044-105">Представляет состояние в конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="25044-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="25044-106">Представляет завершающее состояние в конечном автомате.</span><span class="sxs-lookup"><span data-stu-id="25044-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="25044-107"><xref:System.Activities.Core.Presentation.FinalState> - конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние.</span><span class="sxs-lookup"><span data-stu-id="25044-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="25044-108">Дополнительные сведения см. в разделе [конструктора действий FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="25044-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="25044-109">Представляет переход между двумя состояниями.</span><span class="sxs-lookup"><span data-stu-id="25044-109">Represents the transition between two states.</span></span> <span data-ttu-id="25044-110">Существует не **элементов** элемент <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов с помощью перетаскивания линию между двумя состояниями или путем сброса состояния в треугольниках, отображаемых при наведении одного состояния на другое .</span><span class="sxs-lookup"><span data-stu-id="25044-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="25044-111">Дополнительные сведения см. в разделе [конструктор действий переходов](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="25044-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25044-112">См. также</span><span class="sxs-lookup"><span data-stu-id="25044-112">See also</span></span>

- [<span data-ttu-id="25044-113">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="25044-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
