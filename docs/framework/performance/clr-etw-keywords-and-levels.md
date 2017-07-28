---
title: "CLR ETW Keywords and Levels | Microsoft Docs"
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
  - "CLR ETW keywords"
  - "CLR ETW levels"
  - "ETW, CLR keywords"
  - "ETW, CLR levels"
ms.assetid: fdf5856d-516b-4042-849d-911c4518a6cb
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# CLR ETW Keywords and Levels
<a name="top"></a> События трассировки событий Windows можно отфильтровать по категории и уровню.[Ключевые слова трассировки событий Windows в среде CLR](#keywords) событий обеспечивают фильтрацию событий по категории. Они используются в различных сочетаниях для поставщиков среды выполнения и очистки.[Уровни событий](#levels) определяются флагами.  
  
<a name="keywords"></a>   
## Ключевые слова трассировки событий Windows в среде CLR  
 Ключевые слова служат флагами, которые можно объединять для формирования значений. На практике при использовании программ командной строки вместо имен ключевых слов применяются их шестнадцатеричные значения.  
  
 В следующих таблицах представлено описание ключевых слов:  
  
-   [Ключевые слова среды выполнения трассировки событий Windows в среде CLR](#runtime)  
  
-   [Ключевые слова среды очистки трассировки событий Windows в среде CLR](#rundown)  
  
-   [Сочетания ключевых слов для разрешения символов для поставщика среды выполнения](#runtime_combo)  
  
-   [Сочетания ключевых слов для разрешения символов для поставщика очистки](#rundown_combo)  
  
<a name="runtime"></a>   
### Ключевые слова среды выполнения трассировки событий Windows в среде CLR  
 В таблице ниже приведены ключевые слова среды выполнения трассировки событий Windows среды CLR, их значения и предназначение.  
  
|Имя ключевого слова среды выполнения|Значение|Цель|  
|------------------------------------------|--------------|----------|  
|`GCKeyword`|0x00000001|Включает сбор [событий сборки мусора](../../../docs/framework/performance/garbage-collection-etw-events.md).|  
|`LoaderKeyword`|0x00000008|Включает сбор [событий загрузчика](../../../docs/framework/performance/loader-etw-events.md).|  
|`JITKeyword`|0x00000010|Включает сбор [JIT\-событий](../../../docs/framework/performance/jit-tracing-etw-events.md).|  
|`NGenKeyword`|0x00000020|Включает сбор событий для методов образов в машинном коде \(методы, обрабатываемые генератором образов в машинном коде \(Ngen.exe\)\). Используется с ключевыми словами `StartEnumerationKeyword` и `EndEnumerationKeyword`. Использование этого ключевого слова связано с большими издержками. Оно формирует события для каждого метода внутри каждого загружаемого модуля NGen. По возможности вместо этого ключевого слова рекомендуется использовать базы данных программ \(PDB\), созданные с помощью средств профилирования, для получения сведений о методах из модулей NGen. См. также описание ключевого слова `OverrideAndSuppressNGenEventsKeyword` далее в этой таблице.|  
|`StartEnumerationKeyword`|0x00000040|Включает перечисление всех методов во время выполнения; используется вместе с `NGenKeyword`.|  
|`EndEnumerationKeyword`|0x00000080|Включает перечисление всех методов, уничтоженных во время выполнения; используется вместе с `JITKeyword` и `NGenKeyword`.|  
|`SecurityKeyword`|0x00000400|Включает сбор [событий безопасности](../../../docs/framework/performance/security-etw-events.md).|  
|`AppDomainResourceManagementKeyword`|0x00000800|Включает сбор событий отслеживания ресурсов на уровне домена приложения.|  
|`JITTracingKeyword`|0x00001000|Включает сбор [событий трассировки JIT\-компилятора](../../../docs/framework/performance/jit-tracing-etw-events.md).|  
|`InteropKeyword`|0x00002000|Включает сбор [событий взаимодействия](../../../docs/framework/performance/interop-etw-events.md).|  
|`ContentionKeyword`|0x00004000|Включает сбор [событий состязания](../../../docs/framework/performance/contention-etw-events.md).|  
|`ExceptionKeyword`|0x00008000|Включает сбор [событий исключений](../../../docs/framework/performance/exception-thrown-v1-etw-event.md).|  
|`ThreadingKeyword`|0x00010000|Включает сбор [событий пула потоков](../../../docs/framework/performance/thread-pool-etw-events.md).|  
|`OverrideAndSuppressNGenEventsKeyword`|0x00040000|\(Доступно в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздних версиях\). Подавляет ключевое слово `NGenKeyword`, обладающее высокими издержками, и запрещает создание событий для методов, входящих в состав модулей NGen. Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], средства профилирования должны использовать `OverrideAndSuppressNGenEventsKeyword` и `NGenKeyword` для подавления создания событий для методов модулей NGen. Это позволяет средству профилирования использовать более эффективные базы данных программы NGen для получения сведений о методах модулей NGen. Среда CLR в .NET Framework 4 и более ранних версиях не поддерживает создание баз данных программы NGen. В более ранних версиях среда CLR не распознает `OverrideAndSuppressNGenEventsKeyword` и обрабатывает `NGenKeyword`, создавая события для методов модулей NGen.|  
|`PerfTrackKeyWord`|0x2000000|Включает сбор событий `ModuleLoad` и `ModuleRange`.|  
|`StackKeyword`|0x40000000|Включает сбор [событий трассировки стека](../../../docs/framework/performance/stack-etw-event.md) среды CLR.|  
  
 [К началу](#top)  
  
<a name="rundown"></a>   
### Ключевые слова среды очистки трассировки событий Windows в среде CLR  
 В таблице ниже приведены ключевые слова среды очистки трассировки событий Windows среды CLR, их значения и предназначение.  
  
|Имя ключевого слова очистки|Значение|Цель|  
|---------------------------------|--------------|----------|  
|`LoaderRundownKeyword`|0x00000008|Включает сбор событий загрузчика при использовании с ключевыми словами `StartRundownKeyword` и `EndRundownKeyword`.|  
|`JitRundownKeyword`|0x00000010|Включает сбор событий `DCStart` и `DCEnd` методов \(скомпилированных JIT\-компилятором\) при использовании с ключевыми словами `StartRundownKeyword` и `EndRundownKeyword`.|  
|`NGenRundownKeyword`|0x00000020|Включает сбор событий `DCStart` и `DCEnd` для методов образов NGen в машинном коде при использовании с ключевыми словами `StartRundownKeyword` и `EndRundownKeyword`. Использование этого ключевого слова связано с большими издержками. Оно формирует события для каждого метода внутри каждого загружаемого модуля NGen. По возможности вместо этого ключевого слова рекомендуется использовать базы данных программ \(PDB\), созданные с помощью средств профилирования, для получения сведений о методах из модулей NGen. См. также описание ключевого слова `OverrideAndSuppressNGenEventsRundownKeyword` далее в этой таблице.|  
|`StartRundownKeyword`|0x00000040|Включает перечисление состояния системы во время очистки запуска.|  
|`EndRundownKeyword`|0x00000100|Включает перечисление состояния системы во время очистки завершения.|  
|`AppDomainResourceManagementRundownKeyword`|0x00000800|Включает сбор событий для отслеживания ресурсов на уровне <xref:System.AppDomain> при использовании с ключевыми словами `StartRundownKeyword` или `EndRundownKeyword`.|  
|`ThreadingKeyword`|0x00010000|Включает сбор событий пула потоков.|  
|`OverrideAndSuppressNGenEventsRundownKeyword`|0x00040000|\(Доступно в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздних версиях\). Подавляет ключевое слово `NGenRundownKeyword`, обладающее высокими издержками, и запрещает создание событий для методов, входящих в состав модулей NGen. Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], средства профилирования должны использовать `OverrideAndSuppressNGenEventsRundownKeyword` и `NGenRundownKeyword` для подавления создания событий для методов модулей NGen. Это позволяет средству профилирования использовать более эффективные базы данных программы NGen для получения сведений о методах модулей NGen. Среда CLR в .NET Framework 4 и более ранних версиях не поддерживает создание баз данных программы NGen. В более ранних версиях среда CLR не распознает `OverrideAndSuppressNGenEventsRundownKeyword` и обрабатывает `NGenRundownKeyword`, создавая события для методов модулей NGen.|  
|`PerfTrackKeyWord`|0x2000000|Включает сбор событий `ModuleDCStart`, `ModuleDCEnd`, `ModuleRangeDCStart` и `ModuleRangeDCEnd`.|  
  
 [К началу](#top)  
  
<a name="runtime_combo"></a>   
### Сочетания ключевых слов для разрешения символов для поставщика среды выполнения  
  
|Ключевые слова и флаги|События загрузки и выгрузки доменов приложений, сборок, модулей|События загрузки и выгрузки методов \(кроме динамических событий\)|События загрузки и уничтожения динамических методов|  
|----------------------------|---------------------------------------------------------------------|------------------------------------------------------------------------|---------------------------------------------------------|  
|`LoaderKeyword`|События загрузки и выгрузки.|Нет.|Нет.|  
|`JITKeyword`<br /><br /> \(\+ `StartEnumerationKeyword` ничего не добавляет\)|Нет.|События загрузки.|События загрузки и выгрузки.|  
|`JITKeyword` \+<br /><br /> `EndEnumerationKeyword`|Отсутствует.|События загрузки и выгрузки.|События загрузки и выгрузки.|  
|`NGenKeyword`|Нет.|Нет.|Неприменимо.|  
|`NGenKeyword` \+<br /><br /> `StartEnumerationKeyword`|Отсутствует.|События загрузки.|Неприменимо.|  
|`NGenKeyword` \+<br /><br /> `EndEnumerationKeyword`|Отсутствует.|События выгрузки.|Неприменимо.|  
  
 [К началу](#top)  
  
<a name="rundown_combo"></a>   
### Сочетания ключевых слов для разрешения символов для поставщика очистки  
  
|Ключевые слова и флаги|События DCStart и DCEnd для доменов приложений, сборок, модулей|События DCStart и DCEnd методов \(включая события динамических методов\)|  
|----------------------------|---------------------------------------------------------------------|------------------------------------------------------------------------------|  
|`LoaderRundownKeyword` \+<br /><br /> `StartRundownKeyword`|События `DCStart`.|Нет.|  
|`LoaderRundownKeyword` \+<br /><br /> `EndRundownKeyword`|События `DCEnd`.|Нет.|  
|`JITKeyword` \+<br /><br /> `StartRundownKeyword`|Нет.|События `DCStart`.|  
|`JITKeyword` \+<br /><br /> `EndRundownKeyword`|Отсутствует.|События `DCEnd`.|  
|`NGenKeyword` \+<br /><br /> `StartRundownKeyword`|Отсутствует.|События `DCStart`.|  
|`NGenKeyword` \+<br /><br /> `EndRundownKeyword`|Отсутствует.|События `DCEnd`.|  
  
 [К началу](#top)  
  
<a name="levels"></a>   
## Уровни событий трассировки событий Windows  
 События трассировки событий Windows также можно фильтровать по уровням. Если задан уровень 0x5, создаются события всех уровней, включая 0x5 и более низкие \(события относятся к категориям, включенным с помощью ключевых слов\). Если задан уровень 0x2, создаются только события, относящиеся к уровню 0x2 и более низким.  
  
 Уровни имеют следующие значения:  
  
 0x5 — Verbose \(подробный\);  
  
 0x4 — Informational \(информационный\);  
  
 0x3 — Warning \(предупреждение\);  
  
 0x2 — Error \(ошибка\);  
  
 0x1 — Critical \(критический\);  
  
 0x0 — LogAlways \(регистрировать всегда\).  
  
## См. также  
 [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)   
 [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)