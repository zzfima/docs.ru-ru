---
title: "Устранение рисков: вызовы метода EventSource.WriteEvent | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cde809989d89c10caeb97ec853c8649a108cd72d
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a>Устранение рисков: вызовы метода EventSource.WriteEvent
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] принудительно применяет контракт между методом событий ETW в классе, являющемся производным от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, и методом <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> его базового класса. Метод событий ETW должен передавать методу <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> идентификатор события с теми же аргументами, которые были переданы в метод событий.  
  
## <a name="impact"></a>Последствия  
 Метод событий ETW, определенный следующим образом, нарушает контракт.  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
  
```  
  
 При нарушении этого контракта, если объект <xref:System.Diagnostics.Tracing.EventListener> считывает данные <xref:System.Diagnostics.Tracing.EventSource> в процессе, во время выполнения вызывается исключение <xref:System.IndexOutOfRangeException>.  
  
 Определение этого метода событий ETW должно иметь следующий вид.  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
  
```  
  
## <a name="mitigation"></a>Уменьшение  
 Для соответствия требуемому виду необходимо изменить существующий код.  
  
 Можно минимизировать объем кода, который необходимо изменить, указав два метода для вызова метода <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> следующим образом:  
  
```  
  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
  
```  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
