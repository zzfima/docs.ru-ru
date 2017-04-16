---
title: "ETW Events in the Common Language Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW events"
  - "ETW, common language runtime"
  - "ETW, CLR events"
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# ETW Events in the Common Language Runtime
Среда CLR предоставляет полезные диагностические данные трассировки событий для Windows \(ETW\) благодаря большому количеству событий отладки и профилирования.  События ETW среды CLR используют систему трассировки Windows ETW, чтобы дополнить существующую поддержку профилирования и отладки, поддерживаемую средой CLR.  
  
 Дополнительные сведения о ETW см. в статье об [улучшении отладки и настройки быстродействия с помощью ETW \(на английском языке\)](http://go.microsoft.com/fwlink/?LinkID=161142) библиотеки MSDN.  Сведения о программе Xperf можно найти в записи [Windows Performance Toolkit \- Xperf \(на английском языке\)](http://go.microsoft.com/fwlink/?LinkID=161144) блога NTDebugging.  
  
 Дополнительные инструменты среды CLR для трассировки событий Windows будут представлены в [CodePlex](http://go.microsoft.com/fwlink/?LinkID=111138), как только станут доступны.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] или более поздней версии необходим для всех событий, описанных в статьях про события.  Операционная система Windows Vista \- минимальный поддерживаемый клиент, а Windows Server 2008 \- минимальный поддерживаемый сервер.  
  
## В этом подразделе  
 [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md)  
 Описание средств и команд захвата и просмотра событий ETW.  
  
 [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)  
 Сведения о поставщиках среды выполнения и очистки и способах их использования для сбора данных ETW.  
  
 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 Описание ключевых слов для поставщиков среды выполнения и очистки, включающих фильтрацию событий по категории.  
  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)  
 Подробные сведения о событиях ETW среды CLR, их ключевых словах, уровнях и сведения о событиях.  
  
## См. также  
 [ETW Events in the .NET Framework](../../../docs/framework/performance/etw-events.md)