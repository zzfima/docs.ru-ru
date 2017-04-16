---
title: "SpinWait | Microsoft Docs"
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
  - "synchronization primitives, SpinWait"
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# SpinWait
<xref:System.Threading.SpinWait?displayProperty=fullName> — это упрощенный тип синхронизации, который можно использовать в низкоуровневых сценариях, чтобы избежать ресурсоемких переключений контекста и переходов в режим ядра, необходимых для событий ядра.  На многоядерных компьютерах, когда не предполагается, что ресурс будет удерживаться в течение длительного времени, для ожидающего потока более эффективным решением может быть переход в цикл в пользовательском режиме на несколько десятков или сотен тактов процессора и повторная попытка получения ресурса.  Если ресурс доступен после выхода из цикла, можно сэкономить несколько тысяч тактов процессора.  Если ресурс еще недоступен, то потрачено только несколько тактов процессора и еще не поздно перейти в режим ожидания на основе ядра.  Эта комбинация, цикл с последующим ожиданием, иногда называется *двухэтапной операцией ожидания*.  
  
 <xref:System.Threading.SpinWait> предназначен для использования вместе с типами .NET Framework, которые служат оболочкой для событий ядра, например <xref:System.Threading.ManualResetEvent>.  <xref:System.Threading.SpinWait> также можно использовать самостоятельно для базовых функций цикла в одной программе.  
  
 <xref:System.Threading.SpinWait> — это не просто пустой цикл.  Этот тип аккуратно реализован, чтобы обеспечить правильное циклическое поведение в общем случае, и сам будет инициировать переключения контекста, если цикл оказывается достаточно длинным \(примерно равным интервалу времени, необходимому для перехода в режим ядра\).  Например, на одноядерных компьютерах <xref:System.Threading.SpinWait> немедленно возвращает временной интервал в потоке, так как цикл блокирует дальнейшее выполнение всех потоков.  <xref:System.Threading.SpinWait> также возвращает управление даже на многоядерных компьютерах, чтобы помешать ожидающему потоку блокировать потоки с более высоким приоритетом или сборщик мусора.  Следовательно, при использовании <xref:System.Threading.SpinWait> в двухэтапной операции ожидания рекомендуется вызывать ожидание ядра до того, как <xref:System.Threading.SpinWait> сам инициирует переключение контекста.  <xref:System.Threading.SpinWait> предоставляет свойство <xref:System.Threading.SpinWait.NextSpinWillYield%2A>, которое можно проверять перед каждым вызовом метода <xref:System.Threading.SpinWait.SpinOnce%2A>.  Когда свойство возвращает значение `true`, инициируйте собственную операцию ожидания.  Пример см. в разделе [How to: Use SpinWait to Implement a Two\-Phase Wait Operation](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Если вместо двухэтапной операции ожидания просто выполняется цикл до выполнения некоторого условия, можно разрешить объекту <xref:System.Threading.SpinWait> самому выполнять переключение контекста, чтобы он был "вежливым" в среде операционной системы Windows.  В следующем базовом примере показано применение <xref:System.Threading.SpinWait> в стеке без блокировок.  Если необходимо создать высокопроизводительный потокобезопасный стек, следует рассмотреть возможность использования <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## См. также  
 <xref:System.Threading.Thread.SpinWait%2A>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)