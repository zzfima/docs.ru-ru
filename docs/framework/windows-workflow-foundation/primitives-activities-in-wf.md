---
title: "Базовые действия в WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e9009d1-236e-4d8e-86fc-e43132bf6dfc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Базовые действия в WF
В [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] предусмотрено несколько предоставляемых системой действий, которые представляют собой удобный механизм выполнения общих задач.  
  
|Действие|Описание|  
|--------------|--------------|  
|<xref:System.Activities.Statements.Assign>|Назначает значение переменной в текущей области.|  
|<xref:System.Activities.Statements.Delay>|Переводит один путь выполнения в состояние бездействия, что может позволить выгрузить рабочий процесс.|  
|<xref:System.Activities.Statements.InvokeDelegate>|Выполняет делегат, который является производным от <xref:System.Activities.ActivityDelegate> и доступен как свойство.|  
|<xref:System.Activities.Statements.InvokeMethod>|Выполняет открытый метод объекта CLR.|  
|<xref:System.Activities.Statements.WriteLine>|Отображает указанную строку на консоли или записывает в указанный объект <xref:System.IO.TextWriter>.|