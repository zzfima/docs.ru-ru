---
title: "Действия времени выполнения в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3aca3fcdd4fa8d73bf3412d7c20697847d0a699
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-activities-in-wf"></a>Действия времени выполнения в WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] содержит несколько предоставляемых системой действий для доступа к функциям среды выполнения рабочих процессов, например к функциям сохраняемости и завершения рабочих процессов.  
  
|Действие|Описание|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Явно запрашивает сохранение состояния рабочего процесса.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Завершает выполнение экземпляра рабочего процесса.|  
|<xref:System.Activities.Statements.NoPersistScope>|Действие контейнера, препятствующее сохранению дочерних действий.|
