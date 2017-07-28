---
title: "Действия конечного автомата в WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Действия конечного автомата в WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предоставляет несколько системных действий и конструкторов действий для создания рабочих процессов конечного автомата.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Выполняет включенные действия на основе известной парадигмы конечного автомата.|  
|<xref:System.Activities.Statements.State>|Представляет состояние в конечном автомате.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Представляет завершающее состояние в конечном автомате.<xref:System.Activities.Core.Presentation.FinalState> — конструктор действий, который при использовании создает <xref:System.Activities.Statements.State>, предварительно настроенное как завершающие состояние.Дополнительные сведения см. в разделе [Конструктор FinalState Activity](../Topic/FinalState%20Activity%20Designer.md).|  
|<xref:System.Activities.Statements.Transition>|Представляет переход между двумя состояниями.Не существует элемента **Область элементов** для <xref:System.Activities.Statements.Transition>; переходы создаются в конструкторе рабочих процессов путем перетаскивания линии между двумя состояниями или путем размещения состояния на треугольниках, отображаемых при наведении одного состояния на другое.Дополнительные сведения см. в разделе [Конструктор действий переходов](../Topic/Transition%20Activity%20Designer.md).|  
  
## См. также  
 [Учебник по началу работы](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)