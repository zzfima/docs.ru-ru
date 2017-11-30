---
title: Mutexes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>Mutexes
Можно использовать <xref:System.Threading.Mutex> для получения монопольного доступа к ресурсу. <xref:System.Threading.Mutex> Класс использует больше системных ресурсов, чем <xref:System.Threading.Monitor> класса, но может быть маршалирован через границы домена приложения, он может использоваться с несколькими ожиданиями, а также он может использоваться для синхронизации потоков в различных процессах. Сравнение механизмов управляемой синхронизации см. в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Примеры кода см. в справочной документации по <xref:System.Threading.Mutex.%23ctor%2A> конструкторы.  
  
## <a name="using-mutexes"></a>Использование мьютексов  
 Поток вызывает метод <xref:System.Threading.WaitHandle.WaitOne%2A> метод мьютекса, который запросит владение. Вызов блокируется до тех пор, пока мьютекс на будет доступен или пока не истечет дополнительное время ожидания. Если мьютексом не владеет ни один поток, сообщается состояние мьютекса.  
  
 Поток освобождает мьютекс путем вызова его <xref:System.Threading.Mutex.ReleaseMutex%2A> метод. Мьютексы поддерживают сходство потоков, т. е. мьютекс может быть освобожден только тем потоком, который им владеет. Если поток освобождает мьютекс не владеет, <xref:System.ApplicationException> исключение в потоке.  
  
 Поскольку <xref:System.Threading.Mutex> класс является производным от <xref:System.Threading.WaitHandle>, вы также можете вызвать статический <xref:System.Threading.WaitHandle.WaitAll%2A> или <xref:System.Threading.WaitHandle.WaitAny%2A> методы <xref:System.Threading.WaitHandle> который запросит владение <xref:System.Threading.Mutex> в сочетании с другими дескрипторы ожидания.  
  
 Если поток владеет <xref:System.Threading.Mutex>, что поток может указывать тот же <xref:System.Threading.Mutex> при вызове повторного запроса ожидания, не прерывая выполнения; тем не менее, его нужно освободить <xref:System.Threading.Mutex> количество раз для освобождения владения.  
  
## <a name="abandoned-mutexes"></a>Брошенные мьютексы  
 Если поток завершается без освобождения <xref:System.Threading.Mutex>, мьютекс называется к прерыванию. Это часто указывает на серьезную ошибку программирования, поскольку ресурс, защищаемый мьютексом, может остаться в несогласованном состоянии. В .NET Framework версии 2.0 <xref:System.Threading.AbandonedMutexException> вызывается в следующий поток, который получает объект взаимного исключения.  
  
> [!NOTE]
>  В .NET Framework версий 1.0 и 1.1, прерванное <xref:System.Threading.Mutex> сигнальное состояние и следующий ожидающий поток-владелец получает. Если ни один поток не находится в состоянии ожидания, <xref:System.Threading.Mutex> остается в состоянии получения сигнала. Исключение не возникает.  
  
 В случае системного мьютекса брошенный мьютекс может указывать на то, что работа приложения была внезапно прекращена (например, с помощью диспетчера задач Windows).  
  
## <a name="local-and-system-mutexes"></a>Локальные и системные мьютексы  
 Мьютексы бывают двух типов: локальные и именованные системные. Если вы создаете <xref:System.Threading.Mutex> объекта, используя конструктор, который принимает имя, она связана с объектом операционной системы с тем же именем. Именованные системные мьютексы доступны во всей операционной системе и могут использоваться для синхронизации действий процессов. Можно создать несколько <xref:System.Threading.Mutex> объекты, представляющие же именованный системный мьютекс, и можно использовать <xref:System.Threading.Mutex.OpenExisting%2A> метод, чтобы открыть существующий именованный системный мьютекс.  
  
 Локальный мьютекс существует только в вашем процессе. Он может использоваться любым потоком в процессе, имеющим ссылку на локальный <xref:System.Threading.Mutex> объекта. Каждый <xref:System.Threading.Mutex> объект является отдельным локальным мьютекс.  
  
### <a name="access-control-security-for-system-mutexes"></a>Безопасность управления доступом для системных мьютексов  
 Платформа .NET Framework версии 2.0 позволяет запрашивать и настраивать безопасность управления доступом Windows для именованных системных объектов. Системные мьютексы рекомендуется защищать с момента создания, поскольку системные объекты глобальны, а значит, могут быть заблокированы не вашим кодом.  
  
 Сведения о безопасности управления доступом для мьютексов см. в разделе <xref:System.Security.AccessControl.MutexSecurity> и <xref:System.Security.AccessControl.MutexAccessRule> классы, <xref:System.Security.AccessControl.MutexRights> перечисления, <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, и <xref:System.Threading.Mutex.OpenExisting%2A> методы <xref:System.Threading.Mutex> класс и <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> конструктор.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Мониторы](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)
