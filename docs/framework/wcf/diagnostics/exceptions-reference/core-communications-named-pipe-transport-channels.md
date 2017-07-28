---
title: "Основное взаимодействие: именованные каналы конвейерной передачи | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14ab8f84-ab3e-47cd-8ac5-dd68af940175
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Основное взаимодействие: именованные каналы конвейерной передачи
В этом разделе перечислены все исключения, создаваемые транспортными каналами именованных каналов.  
  
## Список исключений  
  
|Код ресурса|Строка ресурса|  
|-----------------|--------------------|  
|PipeCantCloseWithPendingWrite|Невозможно закрыть канал, пока ожидается завершение операции записи в канал.|  
|PipeReadPending|Выполняется операция чтения из канала.|  
|PipeShutdownReadError|Сбой операции чтения индикатора "shutdown" канала.|  
|PipeShutdownWriteError|Сбой операции записи индикатора "shutdown" канала.|  
|PipeWritePending|Выполняется операция записи в канал.|