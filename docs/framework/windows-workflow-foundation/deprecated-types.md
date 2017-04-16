---
title: "Deprecated types in Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Deprecated types in Windows Workflow Foundation
В .NET 4 группа разработки по рабочим процессам представила полностью новую подсистему рабочих процессов в пространстве имен <xref:System.Activities>.  С выходом бета\-версии .NET 4.5 мы отмечаем большинство типов в пространствах имен «WF 3» <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel> и <xref:System.Workflow.Runtime> как устаревшие.  
  
## Устаревшие пространства имен и средства  
 Следующие сборки содержат один и более открытых типов, которые станут устаревшими.  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 В результате этого клиенты, использующие устаревшие API WF 3, увидят предупреждения при сборке с сообщением следующего вида:  
  
  **Предупреждение BC40000. X устарело: типы WF 3 устарели.  Взамен рекомендуется использовать WF 4.**  В одном из последующих выпусков \(не в 4.5\) типы будут удалены из .NET Framework, но временной промежуток до этого еще не определен.  Текущий шаг позволяет донести наши планы до клиентов и дает им достаточно времени для перехода на новую модель WF4.  Безусловно, эти типы WF 3 будут поддерживаться в рамках [политики жизненного цикла поддержки Майкрософт](http://aka.ms/MicrosoftSupportLifecycle).  Существующие приложения WF3 будут запускаться в .NET 4.5 без проблем; [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] будет поддерживать новые и существующие решения на основе WF3.  
  
 Основанные на правилах типы в пространстве имен <xref:System.Workflow.Activities.Rules>, не имеющие замены в WF 4.5, не устарели.  
  
 Справку для клиентов, которым требуется миграция в WF 4, см. в статьях [руководства по миграции рабочего процесса 4](http://aka.ms/WF4MigrationGuidance) на сайте MSDN и в разделе [Комплект миграции WF 4](http://aka.ms/WF4MigrationKit) на сайте [WF Codeplex](http://aka.ms/WFCodeplex).