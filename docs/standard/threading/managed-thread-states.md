---
title: "Состояния управляемых потоков | Microsoft Docs"
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
  - "работа с потоками [платформа .NET Framework], состояния"
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Состояния управляемых потоков
Свойство <xref:System.Threading.Thread.ThreadState%2A?displayProperty=fullName> предоставляет битовую маску, которая указывает текущее состояние потока. Поток постоянно находится по крайней мере в одном из возможных состояний, указанных в перечислении <xref:System.Threading.ThreadState>, и может иметь несколько состояний одновременно.  
  
> [!IMPORTANT]
>  Состояние потока используется только в некоторых сценариях отладки. Не используйте в коде состояния потоков для синхронизации действий потоков.  
  
 При создании управляемого потока он находится в состоянии <xref:System.Threading.ThreadState>. Поток остается в состоянии <xref:System.Threading.ThreadState>, пока не будет переведен в состояние запуска операционной системой. Вызов метода <xref:System.Threading.Thread.Start%2A> служит для того, чтобы сообщить системе, что поток можно запустить. При этом состояние потока не меняется.  
  
 Неуправляемые потоки, которые входят в управляемую среду, уже запущены. После запуска потока его состояние можно изменить, совершив с ним определенные действия. В приведенной ниже таблице представлены действия, изменяющие состояние потока, а также его новые состояния.  
  
|Действие|Новое состояние|  
|--------------|---------------------|  
|Вызывается конструктор класса <xref:System.Threading.Thread>.|<xref:System.Threading.ThreadState>|  
|Другой поток вызывает метод <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Поток отвечает на <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> и начинает выполняться.|<xref:System.Threading.ThreadState>|  
|Поток вызывает метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Поток вызывает метод <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> другого объекта.|<xref:System.Threading.ThreadState>|  
|Поток вызывает метод <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> другого потока.|<xref:System.Threading.ThreadState>|  
|Другой поток вызывает метод <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Поток отвечает на запрос <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Другой поток вызывает метод <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Другой поток вызывает метод <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>|  
|Поток отвечает на <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.|<xref:System.Threading.ThreadState>, а затем <xref:System.Threading.ThreadState>|  
  
 Так как состоянию <xref:System.Threading.ThreadState> соответствует значение 0, для определения этого состояния невозможно применить побитовую проверку. Вместо этого можно использовать следующий тест \(на псевдокоде\):  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 Как правило, поток одновременно имеет более одного состояния. Например, если поток заблокируется при вызове <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> и другой поток вызывает метод <xref:System.Threading.Thread.Abort%2A> того же потока, этот поток будет находиться в состояниях <xref:System.Threading.ThreadState> и <xref:System.Threading.ThreadState> одновременно. В этом случае, как только поток выполнит возврат из метода <xref:System.Threading.Monitor.Wait%2A> или его работа будет прервана, он получит исключение <xref:System.Threading.ThreadAbortException>.  
  
 Если поток был выведен из состояния <xref:System.Threading.ThreadState> в результате вызова метода <xref:System.Threading.Thread.Start%2A>, он не может вернуться в состояние <xref:System.Threading.ThreadState> ни при каких условиях. Поток никогда не может выйти из состояния <xref:System.Threading.ThreadState>.  
  
## См. также  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadState>   
 [Threading](../../../docs/standard/threading/index.md)