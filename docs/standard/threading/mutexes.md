---
title: "Mutexes | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], Mutex class"
  - "Mutex class, about Mutex class"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Mutexes
Можно использовать объект <xref:System.Threading.Mutex> для предоставления монопольного доступа к ресурсу.  Класс <xref:System.Threading.Mutex> использует больше системных ресурсов, чем класс <xref:System.Threading.Monitor>, однако он может маршалироваться через границы домена приложения, использоваться с несколькими ожиданиями, а также использоваться для синхронизации потоков в различных процессах.  Сравнение управляемых механизмов синхронизации см. в разделе [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Примеры кода см. в справочной документации для конструкторов <xref:System.Threading.Mutex.%23ctor%2A>.  
  
## Использование мьютексов  
 Поток вызывает метод <xref:System.Threading.WaitHandle.WaitOne%2A> мьютекса для запроса изменения владельца.  Вызов блокирует поток до того момента, как мьютекс станет доступным, или пока не истечет дополнительное время ожидания.  Если мьютекс не используется ни одним из потоков, он находится в свободном состоянии.  
  
 Поток освобождает мьютекс путем вызова метода <xref:System.Threading.Mutex.ReleaseMutex%2A>.  Мьютексы поддерживают сходство потоков; то есть мьютекс может быть освобожден только потоком, который владеет этим мьютексом.  Если поток освобождает мьютекс, которым не владеет, в потоке создается исключение <xref:System.ApplicationException>.  
  
 Так как класс <xref:System.Threading.Mutex> является производным из <xref:System.Threading.WaitHandle>, можно вызвать статические методы <xref:System.Threading.WaitHandle.WaitAll%2A> или <xref:System.Threading.WaitHandle.WaitAny%2A> класса <xref:System.Threading.WaitHandle> для запроса изменения владельца объекта <xref:System.Threading.Mutex> в комбинации с другими дескрипторами ожидания.  
  
 Если <xref:System.Threading.Mutex> используется потоком, этот поток может указывать тот же объект <xref:System.Threading.Mutex> при повторном вызове запроса\-ожидания, не прерывая выполнения. Для отказа от использования объекта <xref:System.Threading.Mutex> его нужно освободить соответствующее количество раз.  
  
## Брошенные мьютексы  
 Если поток прерывается без освобождения <xref:System.Threading.Mutex>, мьютекс называется брошенным.  Это часто указывает на серьезную ошибку при программировании, так как ресурс, защищаемый мьютексом, может остаться в несогласованном состоянии.  В .NET Framework версии 2.0 исключение <xref:System.Threading.AbandonedMutexException> в следующем потоке, который получает мьютекс.  
  
> [!NOTE]
>  В .NET Framework версии 1.0 и 1.1 состояние брошенного <xref:System.Threading.Mutex> задается как сигнальное и владельцем становится следующий ожидающий поток.  Если нет ни одного ожидающего потока, <xref:System.Threading.Mutex> остается в сигнальном состоянии.  Исключение не создается.  
  
 Брошенный системный мьютекс может свидетельствовать о внезапном прекращении выполнения приложения \(например, с помощью диспетчера задач Windows\).  
  
## Локальные и системные мьютексы  
 Мьютексы бывают двух типов: локальные мьютексы и именованные системные мьютексы.  При создании объекта <xref:System.Threading.Mutex> с помощью конструктора, позволяющего передавать параметр с именем объекта, объект связывается с имеющим данное имя объектом операционной системы.  Именованные системные мьютексы доступны в пределах всей операционной системы и могут быть использованы для синхронизации действий процессов.  Можно создать несколько объектов <xref:System.Threading.Mutex>, представляющих один и тот же именованный системный мьютекс, и использовать метод <xref:System.Threading.Mutex.OpenExisting%2A> для открытия существующего именованного системного мьютекса.  
  
 Локальный мьютекс существует только внутри одного процесса.  Он может использоваться любым потоком в процессе, имеющим ссылку на локальный объект <xref:System.Threading.Mutex>.  Каждый объект <xref:System.Threading.Mutex> является отдельным локальным мьютекс.  
  
### Безопасность управления доступом для системных мьютексов  
 В .NET Framework версии 2.0 предоставляется возможность запроса и установки безопасности управления доступом Windows для именованных системных объектов.  Рекомендуется защищать системные мьютексы с момента создания, потому что системные объекты являются глобальными и поэтому могут быть заблокированы посторонним кодом.  
  
 Сведения о безопасности управления доступом для мьютексов см. в классах <xref:System.Security.AccessControl.MutexSecurity> и <xref:System.Security.AccessControl.MutexAccessRule>, перечислении <xref:System.Security.AccessControl.MutexRights>, методах <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> и <xref:System.Threading.Mutex.OpenExisting%2A> класса <xref:System.Threading.Mutex> и в конструкторе <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>.  
  
## См. также  
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.Mutex.%23ctor%2A>   
 <xref:System.Security.AccessControl.MutexSecurity>   
 <xref:System.Security.AccessControl.MutexAccessRule>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Мониторы](../Topic/Monitors.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)