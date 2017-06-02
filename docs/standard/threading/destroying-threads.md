---
title: "Destroying Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "destroying threads"
  - "threading [.NET Framework], destroying threads"
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Destroying Threads
Для останова выполнения управляемого потока без возобновления используется метод <xref:System.Threading.Thread.Abort%2A>.  При вызове метода <xref:System.Threading.Thread.Abort%2A> среда CLR выдает в целевом потоке исключение <xref:System.Threading.ThreadAbortException>, которое он может перехватить.  Для получения дополнительной информации см. <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Если в потоке при вызове его метода <xref:System.Threading.Thread.Abort%2A> выполняется неуправляемый код, среда выполнения отмечает его как <xref:System.Threading.ThreadState?displayProperty=fullName>.  Это исключение выдается при возврате потока в управляемый код.  
  
 Если потока прерван, его невозможно перезапустить.  
  
 Метод <xref:System.Threading.Thread.Abort%2A> не ведет к незамедлительному прерыванию выполнения потока, поскольку целевой поток может перехватить исключение <xref:System.Threading.ThreadAbortException> и выполнить произвольный объем кода в блоке `finally`.  Можно вызвать <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>, если требуется дождаться завершения потока.  Вызов метода <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> является блокирующим. Он не выполняет возврат до фактического прекращения выполнения работы потока или истечения дополнительно заданного периода таймаута.  Прерванный поток может вызвать метод <xref:System.Threading.Thread.ResetAbort%2A> или выполнить неограниченную обработку в блоке `finally`, поэтому при отсутствии заданного таймаута ожидание может длиться бесконечно.  
  
 Потоки, ожидающие вызова метода <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>,  могут быть прерваны другими потоками, вызывающими метод <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>.  
  
## Обработки исключения ThreadAbortException  
 Если ожидается прерывание потока в результате вызова метода <xref:System.Threading.Thread.Abort%2A> из собственного кода или выгрузки домена приложения, в котором выполняется поток \(метод <xref:System.AppDomain.Unload%2A?displayProperty=fullName> использует для завершения потоков перегруженный метод <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>\), в потоке должен обрабатываться исключение <xref:System.Threading.ThreadAbortException>, а также должна выполняться завершающая обработка в предложении `finally`.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 Код очистки должен находиться в предложении `catch` или `finally`, поскольку система повторно выдает исключение <xref:System.Threading.ThreadAbortException> в конце предложения `finally` или в конце предложения `catch`, если предложение `finally` отсутствует.  
  
 Можно блокировать повторную выдачу исключения системой путем вызова метода <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=fullName>.  Однако это следует делать только в том случае, если исключение <xref:System.Threading.ThreadAbortException> было вызвано собственным кодом.  
  
## См. также  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)