---
title: "overlappedFreeError MDA | Microsoft Docs"
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
  - "OverlappedFreeError MDA"
  - "overlapped free method call error"
  - "managed debugging assistants (MDAs), overlapped structures"
  - "overlapped structures"
  - "MDAs (managed debugging assistants), overlapped structures"
  - "freeing overlapped structures"
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# overlappedFreeError MDA
Помощник по отладке управляемого кода \(MDA\) `overlappedFreeError` активируется при вызове метода <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=fullName> до завершения перекрывающейся операции.  
  
## Признаки  
 Нарушение прав доступа или повреждения кучи, в которой производится сборка мусора.  
  
## Причина  
 Перекрывающаяся структура была высвобождена до завершения операции.  Функция, использующая перекрывающийся указатель, может выполнить запись в структуру позднее, после высвобождения.  Результатом может стать повреждение кучи, поскольку данная область может быть занята другим объектом.  
  
 Данный помощник по отладке управляемого кода может не представлять ошибку, если не удалось запустить перекрывающуюся операцию.  
  
## Решение  
 Следует проверить, чтобы операция ввода\-вывода, использующая перекрывающуюся структуру, завершилась до вызова метода <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  
  
## Output  
 Далее приведен пример результата работы данного помощника по отладке управляемого кода.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)