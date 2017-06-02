---
title: "How to: Enable Thread-Tracking Mode in SpinLock | Microsoft Docs"
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
  - "SpinLock, how to enable thread-tracking"
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Enable Thread-Tracking Mode in SpinLock
<xref:System.Threading.SpinLock?displayProperty=fullName> — это низкоуровневая взаимно исключающая блокировка, которую можно использовать для сценариев с очень короткими временами ожидания.  <xref:System.Threading.SpinLock> не поддерживает повторный вход.  Вошедший в блокировку поток должен правильной выйти из блокировки, прежде чем он сможет войти повторно.  Обычно любая попытка повторного входа в блокировку вызывает взаимоблокировку, а отладка взаимоблокировок может быть очень трудной.  Чтобы помочь при разработке, <xref:System.Threading.SpinLock?displayProperty=fullName> поддерживает режим отслеживания потоков, который вызывает исключение, когда поток пытается повторно войти в уже установленную потоком блокировку.  Это упростит поиск точки, в которой выход из блокировки не был правильно выполнен.  Режим отслеживания потоков можно включить с помощью конструктора <xref:System.Threading.SpinLock>, принимающего логический входной параметр, и передачи ему аргумента `true`.  После завершения стадий разработки и тестирования отключите режим отслеживания потоков, чтобы повысить производительность.  
  
## Пример  
 В следующем примере показан режим отслеживания потоков.  Строки, выполняющие правильный выход из блокировки, закомментированы, чтобы сымитировать ошибку кода, приводящую к одному из следующих результатов:  
  
-   Возникает исключение, если блокировка <xref:System.Threading.SpinLock> была создана с помощью аргумента `true` \(`True` в Visual Basic\).  
  
-   Взаимоблокировка, если блокировка <xref:System.Threading.SpinLock> была создана с помощью аргумента `false` \(`False` в Visual Basic\).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## См. также  
 [SpinLock](../../../docs/standard/threading/spinlock.md)