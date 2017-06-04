---
title: "Foreground and Background Threads | Microsoft Docs"
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
  - "threading [.NET Framework], foreground"
  - "threading [.NET Framework], background"
  - "foreground threads"
  - "background threads"
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Foreground and Background Threads
Управляемый поток может быть фоновым и основным.  Фоновый поток отличается от основного потока тем, что он не сохраняет управляемую среду выполнения в активном состоянии.  Если в управляемом процессе \(управляемой сборкой является EXE\-файл\) были остановлены все основные потоки, система останавливает все фоновые потоки и завершает работу.  
  
> [!NOTE]
>  Когда среда выполнения останавливает фоновый поток в связи с завершением процесса, в этом потоке не выдается исключение.  Тем не менее, при останове потоков в связи с тем, что метод <xref:System.AppDomain.Unload%2A?displayProperty=fullName> выгружает домен приложения, выдается исключение <xref:System.Threading.ThreadAbortException> как в основном, так и в фоновом потоках.  
  
 Для определения того, каким является поток \(фоновым или основным\) и для изменения его статуса используется свойство <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>.  Поток можно сделать фоновым в любой момент, присвоив его свойству <xref:System.Threading.Thread.IsBackground%2A> значение `true`.  
  
> [!IMPORTANT]
>  Статус потока \(основной или фоновый\) не влияет на выдачу необрабатываемого исключения в этом потоке.  В платформе .NET Framework версии 2.0 необработанное исключение в основном или фоновом потоке ведет к завершению работы приложения.  См. раздел [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Потоки, которые относятся к пулу управляемых потоков \(то есть потоки, свойство <xref:System.Threading.Thread.IsThreadPoolThread%2A> которых имеет значение `true`\), являются фоновыми.  Все потоки, которые взаимодействуют с управляемой средой выполнения из неуправляемого кода, являются фоновыми.  Все потоки, образованные путем создания и запуска нового объекта <xref:System.Threading.Thread>, по умолчанию являются основными.  
  
 При использовании потока для отслеживания деятельности, например подключения к сокету, следует задать для его свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`, чтобы этот поток не препятствовал завершению процесса.  
  
## См. также  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadAbortException>