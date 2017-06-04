---
title: "Contention ETW Events | Microsoft Docs"
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
  - "contention events [.NET Framework]"
  - "ETW, contention events (CLR)"
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Contention ETW Events
События конфликтов вызываются каждый раз, когда возникает конфликт для блокировок <xref:System.Threading.Monitor?displayProperty=fullName> или для блокировок машинного кода, используемого средой выполнения.  Конфликт возникает, пока поток ожидает освобождения блокировки, занятой другим потоком.  
  
 В следующей таблице показано ключевое слово, при котором вызываются события конфликтов, а также уровень событий. \(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Ключевое слово для вызова события|Уровень|  
|---------------------------------------|-------------|  
|`ContentionKeyword` \(0x4000\)|Информационный \(4\)|  
  
 В следующей таблице приведены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-------------|---------------------------|--------------------|  
|`ContentionStart_V1`|81|Конфликт начинается.  Это событие не содержит длительности цикла до ожидания потоком получения блокировки, оно создается, только когда поток ожидает получения блокировки.|  
|`ContentionStop`|81|Конфликт завершается.|  
  
 В следующей таблице приведены сведения о событии.  
  
|Имя поля|Тип данных|Описание|  
|--------------|----------------|--------------|  
|Флаги|win:UInt8|0 для управляемого, 1 для машинного кода.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра среды CLR.|  
  
## См. также  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)