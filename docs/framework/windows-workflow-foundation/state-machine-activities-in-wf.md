---
title: "Действия конечного автомата в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed2b5ace499af3c050529e9f0f2cdd3634c247fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="ffc60-102">Действия конечного автомата в WF</span><span class="sxs-lookup"><span data-stu-id="ffc60-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="ffc60-103"> предусматривает несколько системных действий и конструкторов действий для создания рабочих процессов конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="ffc60-103"> provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="ffc60-104">Выполняет включенные действия на основе известной парадигмы конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="ffc60-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="ffc60-105">Представляет состояние в конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ffc60-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="ffc60-106">Представляет завершающее состояние в конечном автомате.</span><span class="sxs-lookup"><span data-stu-id="ffc60-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="ffc60-107"><xref:System.Activities.Core.Presentation.FinalState> - конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние.</span><span class="sxs-lookup"><span data-stu-id="ffc60-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="ffc60-108">Дополнительные сведения см. в разделе [конструктора действий FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="ffc60-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="ffc60-109">Представляет переход между двумя состояниями.</span><span class="sxs-lookup"><span data-stu-id="ffc60-109">Represents the transition between two states.</span></span> <span data-ttu-id="ffc60-110">Имеется не **элементов** элемент <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов путем перетаскивания линии между двумя состояниями или путем сброса состояния на треугольники, появляющиеся при установке одного состояния прохождении курсора над другой .</span><span class="sxs-lookup"><span data-stu-id="ffc60-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="ffc60-111">Дополнительные сведения см. в разделе [конструктор действий переходов](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="ffc60-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffc60-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc60-112">See Also</span></span>  
 [<span data-ttu-id="ffc60-113">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="ffc60-113">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
