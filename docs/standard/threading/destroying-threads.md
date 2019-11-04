---
title: Удаление потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 1852135e9b7f48d6556e27f16819ddd48805af21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138091"
---
# <a name="destroying-threads"></a>Удаление потоков
Метод <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> используется для остановки управляемого потока без возможности возобновления. При вызове <xref:System.Threading.Thread.Abort%2A> общеязыковая среда выполнения создает в целевом потоке исключение <xref:System.Threading.ThreadAbortException>, которое целевой поток может перехватить. Дополнительные сведения можно найти по адресу: <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> Если в потоке выполняется неуправляемый код при вызове его метода <xref:System.Threading.Thread.Abort%2A>, в среде выполнения он отмечается как <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. В этом случае исключение вызывается после возврата потока в управляемый код.  
  
 После прерывания поток не перезапускается.  
  
 Метод <xref:System.Threading.Thread.Abort%2A> не приводит к немедленному прерыванию потока, так как целевой поток может перехватить <xref:System.Threading.ThreadAbortException> и выполнить любой объем кода в блоке `finally`. Если необходимо дождаться завершения потока, вы можете вызвать <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>. Блокирующий вызов <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> не завершится, пока поток полностью не закончит выполнение или не истечет указанный (необязательный) интервал времени ожидания. Прерванный поток может вызвать метод <xref:System.Threading.Thread.ResetAbort%2A> или выполнить любой объем операций в блоке `finally`, поэтому завершение ожидания не гарантируется, если вы не укажете время ожидания.  
  
 Потоки, ожидающие завершения метода <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, могут быть прерваны другими потоками, которые вызывают <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Обработка ThreadAbortException  
 Если вы ожидаете, что поток будет прерван вызовом <xref:System.Threading.Thread.Abort%2A> из вашего кода или в результате выгрузки домена приложения, в котором выполняется поток (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> использует <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для прерывания потоков), в таком потоке необходимо обработать <xref:System.Threading.ThreadAbortException>, включив в предложение `finally` все операции последней обработки, как показано в следующем примере.  
  
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
  
 Код завершения работы следует поместить в предложении `catch` или `finally`, так как система повторно создаст исключение <xref:System.Threading.ThreadAbortException> в конце предложения `finally` или `catch`, если отсутствует предложение `finally`.  
  
 Чтобы предотвратить повторное создание исключения, вы можете вызвать метод <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>. Но этот вариант следует использовать только в том случае, если <xref:System.Threading.ThreadAbortException> вызывается в пользовательском коде.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
