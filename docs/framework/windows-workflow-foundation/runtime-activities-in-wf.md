---
title: "Действия времени выполнения в WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Действия времени выполнения в WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] содержит несколько предоставляемых системой действий для доступа к функциям среды выполнения рабочих процессов, например к функциям сохраняемости и завершения рабочих процессов.  
  
|Действие|Описание|  
|--------------|--------------|  
|<xref:System.Activities.Statements.Persist>|Явно запрашивает сохранение состояния рабочего процесса.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Завершает выполнение экземпляра рабочего процесса.|  
|<xref:System.Activities.Statements.NoPersistScope>|Действие контейнера, препятствующее сохранению дочерних действий.|