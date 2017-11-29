---
title: "Действия потока управления потока в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6892885b-f7c5-4aea-8f5e-28863fb4ae75
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 825f2487a89805365d3376986af0b0d098c20bca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="control-flow-activities-in-wf"></a>Действия потока управления потока в WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит несколько действий для управления потоком выполнения внутри рабочего процесса. Некоторые из этих действий (например, `Switch` и `If`) реализуют структуры управления потоком управления, аналогичные доступным в средах программирования, таких как [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]; другие (например, `Pick`) моделируют новые структуры программирования.  
  
 Следует отметить, что, хотя такие действия, как `Parallel` и `ParallelForEach`, планируют одновременное выполнение нескольких дочерних действий, в рабочем процессе применяется лишь один поток. Каждое дочернее действие данных действий выполняется последовательно; последующее действие не выполняется, пока не завершатся или не перейдут в состояние бездействия все предыдущие действия. В результате эти действия больше всего полезны в приложениях, в которых несколько потенциально блокирующих друг друга действий должны выполняться поочередно. Если дочерние действия этих действий не переходят в состояние бездействия, действие `Parallel` выполняется аналогично действию `Sequence`, а действие `ParallelForEach` выполняется аналогично действию `ForEach`. Однако, если применяются асинхронные действия (например, действия, производные от <xref:System.Activities.AsyncCodeActivity>) или действия обмена сообщениями, элемент управления передает управление следующей ветви, пока дочернее действие ожидает получения своего сообщения или завершения выполнения асинхронной операции.  
  
## <a name="flow-control-activities"></a>Действия управления потоком  
  
|Действие|Описание|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.DoWhile>|Выполняет содержащиеся в нем действия один раз, затем продолжает выполнять их, пока условие равно `true`.|  
|<xref:System.Activities.Statements.ForEach%601>|Последовательно выполняет внедренную инструкцию в последовательность для каждого из элементов коллекции. Объект <xref:System.Activities.Statements.ForEach%601> аналогичен ключевому слову `foreach`, но реализуется как действие, а не как инструкция языка.|  
|<xref:System.Activities.Statements.If>|Выполняет содержащиеся действия в случае, если условие равно `true`; может выполнять действия, содержащиеся в свойстве <xref:System.Activities.Statements.If.Else%2A>, если условие равно `false`.|  
|<xref:System.Activities.Statements.Parallel>|Параллельно выполняет содержащиеся действия.|  
|<xref:System.Activities.Statements.ParallelForEach%601>|Выполняет внедренную инструкцию параллельно для каждого из элементов коллекции.|  
|<xref:System.Activities.Statements.Pick>|Предоставляет моделирование потока управления на основе событий.|  
|<xref:System.Activities.Statements.PickBranch>|Представляет потенциальный путь выполнения в действии <xref:System.Activities.Statements.Pick>.|  
|<xref:System.Activities.Statements.Sequence>|Выполняет содержащиеся действия последовательно.|  
|<xref:System.Activities.Statements.Switch%601>|Выбирает для выполнения одно действие из нескольких в зависимости от значения указанного выражения.|  
|<xref:System.Activities.Statements.While>|Выполняет содержащиеся действия, если условие равно `true`.|
