---
title: "PiiLoggingNotAllowed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# PiiLoggingNotAllowed
Идентификатор: 108  
  
 Важность: ошибка  
  
 Категория: Tracing  
  
## Описание  
 Это событие указывает на то, что никакие известные PII не регистрируются.  Ведение журнала известных PII запрещено.  Чтобы разрешить ведение журнала известных PII, задайте параметру «enableLoggingKnownPii» значение `true` в файле Machine.config.  В событии указаны имя и ИД процесса.  
  
## См. также  
 [Ведение журнала событий](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Общие справочные сведения о событиях](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)