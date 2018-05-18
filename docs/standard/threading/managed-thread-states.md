---
title: Состояния управляемых потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4266aea9bf206d127e2837955dcc00cc23f4119b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="managed-thread-states"></a>Состояния управляемых потоков
Свойство <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> предоставляет битовую маску, которая указывает текущее состояние потока. Поток постоянно находится по крайней мере в одном из возможных состояний, указанных в перечислении <xref:System.Threading.ThreadState> , и может иметь несколько состояний одновременно.  
  
> [!IMPORTANT]
>  Состояние потока используется только в некоторых сценариях отладки. Не используйте в коде состояния потоков для синхронизации действий потоков.  
  
 При создании управляемого потока он находится в состоянии <xref:System.Threading.ThreadState.Unstarted> . Поток остается в состоянии <xref:System.Threading.ThreadState.Unstarted> , пока не будет переведен в состояние запуска операционной системой. Вызов метода <xref:System.Threading.Thread.Start%2A> служит для того, чтобы сообщить системе, что поток можно запустить. При этом состояние потока не меняется.  
  
 Неуправляемые потоки, которые входят в управляемую среду, уже запущены. После запуска потока его состояние можно изменить, совершив с ним определенные действия. В приведенной ниже таблице представлены действия, изменяющие состояние потока, а также его новые состояния.  
  
|Действие|Новое состояние|  
|------------|-------------------------|  
|Вызывается конструктор класса <xref:System.Threading.Thread> .|<xref:System.Threading.ThreadState.Unstarted>|  
|Другой поток вызывает <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Unstarted>|  
|Поток отвечает на <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> и начинает выполняться.|<xref:System.Threading.ThreadState.Running>|  
|Поток вызывает <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Поток вызывает <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> другого объекта.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Поток вызывает <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> другого потока.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Другой поток вызывает <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.SuspendRequested>|  
|Поток отвечает на запрос <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Suspended>|  
|Другой поток вызывает <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Running>|  
|Другой поток вызывает <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.AbortRequested>|  
|Поток отвечает на <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Aborted>, а затем <xref:System.Threading.ThreadState.Stopped>|  
  
 Так как состоянию <xref:System.Threading.ThreadState.Running> соответствует значение 0, для определения этого состояния невозможно применить побитовую проверку. Вместо этого можно использовать следующий тест (на псевдокоде):  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 Как правило, поток одновременно имеет более одного состояния. Например, если поток заблокируется при вызове <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> и другой поток вызывает <xref:System.Threading.Thread.Abort%2A> того же потока, этот поток будет находиться в состояниях <xref:System.Threading.ThreadState.WaitSleepJoin> и <xref:System.Threading.ThreadState.AbortRequested> одновременно. В этом случае, как только поток выполнит возврат из метода <xref:System.Threading.Monitor.Wait%2A> или его работа будет прервана, он получит исключение <xref:System.Threading.ThreadAbortException>.  
  
 Если поток был выведен из состояния <xref:System.Threading.ThreadState.Unstarted> в результате вызова метода <xref:System.Threading.Thread.Start%2A>, он не может вернуться в состояние <xref:System.Threading.ThreadState.Unstarted> ни при каких условиях. Поток никогда не может выйти из состояния <xref:System.Threading.ThreadState.Stopped> .  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadState>  
 [Работа с потоками](../../../docs/standard/threading/index.md)
