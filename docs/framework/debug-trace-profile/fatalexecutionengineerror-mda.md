---
title: "fatalExecutionEngineError MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "corrupted CLR"
  - "fatal execution error"
  - "terminated processes"
  - "unexpected terminations"
  - "fatal errors"
  - "MDAs (managed debugging assistants), fatal errors"
  - "process termination"
  - "FatalExecutionEngineError MDA"
  - "managed debugging assistants (MDAs), fatal errors"
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# fatalExecutionEngineError MDA
Помощник по отладке управляемого кода \(MDA\) `fatalExecutionEngine``Error` активируется при обнаружении неустранимой ошибки в среде CLR.  Процесс будет завершен.  
  
## Признаки  
 Неожиданное завершение процесса.  Остальные признаки определить не удается, поскольку сбой в работе среды CLR может произойти в силу множества различных причин.  
  
## Причина  
 Произошло неустранимое повреждение среды выполнения CLR.  Чаще всего причиной является повреждение данных, которое может быть вызвано рядом таких проблем, как вызов неправильных функций вызова неуправляемого кода или передача недопустимых данных в среду выполнения CLR.  
  
## Решение  
 Выявить проблему поможет активация дополнительных помощников по отладке управляемого кода.  При диагностике проблемы могут помочь следующие помощники по отладке управляемого кода:  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на функционирование среды выполнения.  
  
## Output  
 Адрес функции среды CLR, которая явилась причиной возникновения неустранимой ошибки, идентификатор потока, в котором возникла ошибка, и код ошибки.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution.Cer>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)