---
title: "Exception Thrown_V1 ETW Event | Microsoft Docs"
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
  - "ExceptionThrown_V1 event [.NET Framework]"
  - "ETW, ExceptionThrown_V1 event (CLR)"
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Exception Thrown_V1 ETW Event
Это событие захватывает сведения, связанные с созданными исключениями.  
  
 В следующей таблице показано ключевое слово, при котором вызывается событие, а также уровень события. \(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Ключевое слово для вызова события|Уровень|  
|---------------------------------------|-------------|  
|`ExceptionKeyword` \(0x8000\)|Предупреждение \(2\)|  
  
 В следующей таблице приведены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-------------|---------------------------|--------------------|  
|`ExceptionThrown_V1`|80|Создается управляемое исключение.|  
  
 В следующей таблице приведены сведения о событии.  
  
|Имя поля|Тип данных|Описание|  
|--------------|----------------|--------------|  
|Тип исключения|win:UnicodeString|Тип исключения, например `System.NullReferenceException`.|  
|Сообщение об исключении|win:UnicodeString|Фактическое сообщение об исключении.|  
|EIPCodeThrow|win:Pointer|Указатель оператора, в котором возникло исключение.|  
|ExceptionHR|win:UInt32|Исключение [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException \(см. раздел [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) в документации Visual Basic\).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException \(показывает, что процесс поврежден, см. раздел [Обработка исключений поврежденного состояния](http://go.microsoft.com/fwlink/?LinkId=179681) в библиотеке MSDN\).<br /><br /> 0x10: IsCLSCompliant \(исключение, унаследованное от <xref:System.Exception>, является CLS\-совместимым, в противном случае исключение не является CLS\-совместимым\).|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра среды CLR или CoreCLR.|  
  
## См. также  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)