---
title: Действия конечного автомата в WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 64af2698c878066464e2ca3f32d4522d99999aec
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378050"
---
# <a name="state-machine-activities-in-wf"></a>Действия конечного автомата в WF
.NET framework 4.5 предоставляет несколько предоставляемых системой действий и конструкторов действий для создания рабочих процессов конечного автомата состояния.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Выполняет включенные действия на основе известной парадигмы конечного автомата.|  
|<xref:System.Activities.Statements.State>|Представляет состояние в конечном компьютере.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Представляет завершающее состояние в конечном автомате. <xref:System.Activities.Core.Presentation.FinalState> - конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние. Дополнительные сведения см. в разделе [конструктора действий FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Представляет переход между двумя состояниями. Существует не **элементов** элемент <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов с помощью перетаскивания линию между двумя состояниями или путем сброса состояния в треугольниках, отображаемых при наведении одного состояния на другое . Дополнительные сведения см. в разделе [конструктор действий переходов](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>См. также

- [Руководство по началу работы](getting-started-tutorial.md)
