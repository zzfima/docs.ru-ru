---
title: "dangerousThreadingAPI MDA | Microsoft Docs"
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
  - "suspending threads"
  - "DangerousThreadingAPI MDA"
  - "managed debugging assistants (MDAs), dangerous threading operations"
  - "threading [.NET Framework], suspending"
  - "MDAs (managed debugging assistants), dangerous threading operations"
  - "Suspend method"
  - "threading [.NET Framework], managed debugging assistants"
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# dangerousThreadingAPI MDA
Управляемый помощник по отладке \(MDA\) `dangerousThreadingAPI` активируется, если метод <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> вызывается для потока, отличного от текущего.  
  
## Признаки  
 Приложение не отвечает или зависает на неопределенный срок.   Системные данные или данные приложения могут оставаться в непредсказуемом состоянии временно или постоянно после того, как приложение закроется.  Некоторые операции не завершаются должным образом.  
  
 Вследствие того, что данная проблема носит случайный характер, признаки могут быть разнообразными.  
  
## Причина  
 Поток асинхронно остановлен другим потоком с помощью метода <xref:System.Threading.Thread.Suspend%2A>.  Невозможно определить, когда остановка другого потока будет действительно безопасной, при том что поток может находиться в процессе выполнения операции.   Остановка потока может привести к повреждению данных, или нарушению инвариантов.   Если приостановить поток и не возобновлять его работу с помощью метода <xref:System.Threading.Thread.Resume%2A>, приложение может зависнуть на неопределенный срок, и есть вероятность повреждения данных приложения.  Данные методы помечены как устаревшие.  
  
 Если примитивы синхронизации удерживаются в целевом потоке, они остаются там во время остановки потока.  Это может привести к взаимоблокировке в том случае, если другой поток, например, поток, выполняющий метод <xref:System.Threading.Thread.Suspend%2A>, попытается получить блокировку примитива.  В данной ситуации проблема проявляется как взаимоблокировка.  
  
## Решение  
 Следует избегать разработок, для которых требуется использование <xref:System.Threading.Thread.Suspend%2A> и <xref:System.Threading.Thread.Resume%2A>.  Для совместной работы потоков следует использовать примитивы синхронизации, такие как <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> или оператор C\# `lock`.  Если необходимо использовать данные методы, следует сократить интервал времени и свести к минимуму объем кода, который выполняется, пока поток остановлен.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  Он только сообщает сведения о небезопасных операциях с потоками.  
  
## Output  
 MDA идентифицирует небезопасный поточный метод, который стал причиной его активации.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода демонстрируется вызов метода <xref:System.Threading.Thread.Suspend%2A>, который стал причиной активации `dangerousThreadingAPI`:  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## См. также  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Оператор lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md)