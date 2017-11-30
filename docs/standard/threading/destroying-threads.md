---
title: "Уничтожение потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>Уничтожение потоков
<xref:System.Threading.Thread.Abort%2A> Метод используется для прекращения управляемого потока, без возможности восстановления. При вызове <xref:System.Threading.Thread.Abort%2A>, общеязыковая среда выполнения создает исключение <xref:System.Threading.ThreadAbortException> в целевом потоке, который целевой поток может перехватить. Для получения дополнительной информации см. <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Если поток выполняет неуправляемый код, при его <xref:System.Threading.Thread.Abort%2A> вызывается метод, среда выполнения отмечает его <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. Исключение вызывается при возврате потока в управляемый код.  
  
 После прерывания потока не перезапускается.  
  
 <xref:System.Threading.Thread.Abort%2A> Метод не вызывает немедленно, прерывание потока, поскольку целевой поток может перехватить <xref:System.Threading.ThreadAbortException> и выполнить произвольный объем кода в `finally` блока. Можно вызвать <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Если необходимо дождаться завершения потока. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>является блокирующий вызов, который не отвечает, пока поток остановки выполнения или истечении интервала необязательное время ожидания. Прерванный поток может вызвать <xref:System.Threading.Thread.ResetAbort%2A> метод или выполнить неограниченную обработку в `finally` блокировать, если указать время ожидания для завершения ожидания не гарантируется.  
  
 Потоков, ожидающих во время вызова <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> метод может быть прервана, другие потоки, которые вызывают <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Обработка ThreadAbortException  
 Если ожидается, что поток будет прерван, в результате вызова <xref:System.Threading.Thread.Abort%2A> из собственного кода или выгрузки домена приложения, в котором выполняется поток (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> использует <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для прерывания потоков), в потоке должен обрабатываться <xref:System.Threading.ThreadAbortException> и выполнить обработку в окончательный `finally` предложения, как показано в следующем коде.  
  
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
  
 Код очистки должен быть в `catch` предложение или `finally` предложение, так как <xref:System.Threading.ThreadAbortException> повторно создается системой в конце `finally` предложение, или в конце `catch` предложение, если имеется не `finally` предложения.  
  
 Система может предотвратить повторное создание исключения путем вызова <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> метод. Однако делать это, только если код вызвал <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
