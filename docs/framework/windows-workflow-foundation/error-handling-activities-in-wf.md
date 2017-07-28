---
title: "Действия по обработке ошибок в WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Действия по обработке ошибок в WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит несколько предоставляемых системой действий для реализации обработки ошибок и восстановления.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Исключения](../../../docs/framework/windows-workflow-foundation//exceptions.md).  
  
## Действия по обработке ошибок  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|Повторно формирует последнее исключение из действия `TryCatch`.|  
|<xref:System.Activities.Statements.Throw>|Создает исключение.|  
|<xref:System.Activities.Statements.TryCatch>|Реализует обработку исключений.|