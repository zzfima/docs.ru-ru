---
title: "Runtime Information ETW Events | Microsoft Docs"
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
  - "runtime information events [.NET Framework]"
  - "ETW, runtime information events"
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Runtime Information ETW Events
Эти события ETW регистрируют сведения о среде выполнения, включая SKU, номер версии, способ активации среды выполнения, параметры командной строки, с которыми она запущена, GUID \(при наличии\) и другие соответствующие данные.  Если в процессе одновременно выполняется несколько сред выполнения, данные, предоставленные этими событиями \(ClrInstanceID\) помогают разрешить неоднозначность, связанную со средами выполнения.  
  
 В следующей таблице приведены два события сведений о среде выполнения.  Эти события можно вызвать любым ключевым словом или маской. \(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Событие|Идентификатор события|Поставщик|Описание|  
|-------------|---------------------------|---------------|--------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Создается при загрузке среды выполнения.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Перечисляет загруженные среды выполнения.|  
  
 В следующей таблице приведены сведения о событии.  
  
|Имя поля|Тип данных|Описание|  
|--------------|----------------|--------------|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра среды CLR или CoreCLR.|  
|Sku|win:UInt16|1 – среда CLR настольного компьютера.<br /><br /> 2 – CoreCLR.|  
|BclVersion – основной номер версии|win:UInt16|Основной номер версии mscorlib.dll.|  
|BclVersion – дополнительный номер версии|win:UInt16|Дополнительный номер версии mscorlib.dll.|  
|BclVersion – номер построения|win:UInt16|Номер построения mscorlib.dll.|  
|BclVersion – QFE|win:UInt16|Исправленный номер версии mscorlib.dll.|  
|VMVersion – основной номер версии|win:UInt16|Версия clr.dll или coreclr.dll, в зависимости от SKU.|  
|VMVersion – дополнительный номер версии|win:UInt16|Дополнительный номер версии clr.dll или coreclr.dll, в зависимости от SKU.|  
|VMVersion – номер построения|win:UInt16|Номер построения clr.dll или coreclr.dll.|  
|VMVersion – QFE|win:UInt16|Исправленный номер версии clr.dll или coreclr.dll.|  
|StartupFlags|win:UInt32|Флаги запуска определены в mscoree.h.|  
|StartupMode|win:UInt8|0x01 — управляемый выполняемый.<br /><br /> 0x02 — размещаемая среда CLR.<br /><br /> 0x04 — Управляемый метод взаимодействия C\+\+.<br /><br /> 0x08 — COM\-активируемый.<br /><br /> 0x10 — Другое.|  
|CommandLine|win:UnicodeString|Значение отличается от null, только если StartupMode\=0x01.|  
|ComObjectGUID|win:GUID|Значение отличается от null, только если StartupMode\=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Путь к DLL\-файлу среды CLR, загруженному в процесс.|  
  
## См. также  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)