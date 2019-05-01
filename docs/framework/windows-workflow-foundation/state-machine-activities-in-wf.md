---
title: Действия конечного автомата в WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004605"
---
# <a name="state-machine-activities-in-wf"></a>Действия конечного автомата в WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусматривает несколько системных действий и конструкторов действий для создания рабочих процессов конечного автомата.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Выполняет включенные действия на основе известной парадигмы конечного автомата.|  
|<xref:System.Activities.Statements.State>|Представляет состояние в конечном компьютере.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Представляет завершающее состояние в конечном автомате. <xref:System.Activities.Core.Presentation.FinalState> - конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние. Дополнительные сведения см. в разделе [конструктора действий FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Представляет переход между двумя состояниями. Существует не **элементов** элемент <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов с помощью перетаскивания линию между двумя состояниями или путем сброса состояния в треугольниках, отображаемых при наведении одного состояния на другое . Дополнительные сведения см. в разделе [конструктор действий переходов](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>См. также

- [Руководство по началу работы](getting-started-tutorial.md)
