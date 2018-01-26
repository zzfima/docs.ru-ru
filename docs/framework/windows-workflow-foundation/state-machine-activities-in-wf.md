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
ms.workload: dotnet
ms.openlocfilehash: 62a211b51f37b306ffcc6b3b9a1ac65ccadd9db5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="state-machine-activities-in-wf"></a>Действия конечного автомата в WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусматривает несколько системных действий и конструкторов действий для создания рабочих процессов конечного автомата.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Выполняет включенные действия на основе известной парадигмы конечного автомата.|  
|<xref:System.Activities.Statements.State>|Представляет состояние в конечном компьютере.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Представляет завершающее состояние в конечном автомате. <xref:System.Activities.Core.Presentation.FinalState> - конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние. Дополнительные сведения см. в разделе [конструктора действий FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Представляет переход между двумя состояниями. Имеется не **элементов** элемент <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов путем перетаскивания линии между двумя состояниями или путем сброса состояния на треугольники, появляющиеся при установке одного состояния прохождении курсора над другой . Дополнительные сведения см. в разделе [конструктор действий переходов](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>См. также  
 [Руководство по началу работы](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
