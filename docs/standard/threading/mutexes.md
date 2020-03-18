---
title: Mutexes
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
ms.openlocfilehash: 874f879697db0b47c73626350eeb05a01b38e1bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127555"
---
# <a name="mutexes"></a>Mutexes
Объект <xref:System.Threading.Mutex> можно использовать для получения монопольного доступа к ресурсу. Класс <xref:System.Threading.Mutex> использует больше системных ресурсов, чем класс <xref:System.Threading.Monitor>, но он может маршалироваться между доменами приложений, использоваться с несколькими ожиданиями и синхронизировать потоки в нескольких процессах. Сравнение механизмов управляемой синхронизации см. в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Примеры кода см. в справочной документации по конструкторам <xref:System.Threading.Mutex.%23ctor%2A>.  
  
## <a name="using-mutexes"></a>Использование мьютексов  
 Поток вызывает метод <xref:System.Threading.WaitHandle.WaitOne%2A> из мьютекса, чтобы затребовать владение. Вызов блокируется до тех пор, пока мьютекс не будет доступен или пока не истечет дополнительное время ожидания. Если мьютексом не владеет ни один поток, сообщается состояние мьютекса.  
  
 Поток освобождает мьютекс, вызывая его метод <xref:System.Threading.Mutex.ReleaseMutex%2A>. Мьютексы поддерживают сходство потоков, т. е. мьютекс может быть освобожден только тем потоком, который им владеет. Если поток освобождает мьютекс, которым он не владеет, в потоке создается исключение <xref:System.ApplicationException>.  
  
 Так как класс <xref:System.Threading.Mutex> является производным от <xref:System.Threading.WaitHandle>, вы также можете вызвать статические методы <xref:System.Threading.WaitHandle.WaitAll%2A> или <xref:System.Threading.WaitHandle.WaitAny%2A> объекта <xref:System.Threading.WaitHandle>, чтобы запросить владение <xref:System.Threading.Mutex> в сочетании с другими дескрипторами ожидания.  
  
 Если поток владеет <xref:System.Threading.Mutex>, он может указывать этот же <xref:System.Threading.Mutex> в повторных запросах ожидания, не прерывая выполнение. Но в этом случае, чтобы отказаться от владения, потребуется освободить <xref:System.Threading.Mutex> столько же раз, сколько он был вызван.  
  
## <a name="abandoned-mutexes"></a>Брошенные мьютексы  
 Если поток завершается без освобождения <xref:System.Threading.Mutex>, мьютекс считается отмененным. Это часто указывает на серьезную ошибку программирования, поскольку ресурс, защищаемый мьютексом, может остаться в несогласованном состоянии. На платформе .NET Framework версии 2.0 в такой ситуации создается исключение <xref:System.Threading.AbandonedMutexException> в следующем потоке, который завладеет этим мьютексом.  
  
> [!NOTE]
> На платформе .NET Framework версий 1.0 и 1.1 отмененный объект <xref:System.Threading.Mutex> переходит в сигнальное состояние, а владение переходит к следующему ожидающему потоку. Если отсутствуют потоки в состоянии ожидания, <xref:System.Threading.Mutex> остается в сигнальном состоянии. Исключение не возникает.  
  
 В случае системного мьютекса брошенный мьютекс может указывать на то, что работа приложения была внезапно прекращена (например, с помощью диспетчера задач Windows).  
  
## <a name="local-and-system-mutexes"></a>Локальные и системные мьютексы  
 Мьютексы бывают двух типов: локальные и именованные системные. Если объект <xref:System.Threading.Mutex> создается с помощью конструктора, который принимает имя, мьютекс сопоставляется с объектом операционной системы, имеющим это имя. Именованные системные мьютексы доступны во всей операционной системе и могут использоваться для синхронизации действий процессов. Вы можете создать сразу несколько объектов <xref:System.Threading.Mutex>, представляющих один и тот именованный системный мьютекс, а также открывать именованный системный мьютекс с помощью метода <xref:System.Threading.Mutex.OpenExisting%2A>.  
  
 Локальный мьютекс существует только в вашем процессе. Его может использовать любой поток в вашем процессе, имеющий ссылку на локальный объект <xref:System.Threading.Mutex>. Каждый объект <xref:System.Threading.Mutex> является отдельным локальным мьютексом.  
  
### <a name="access-control-security-for-system-mutexes"></a>Безопасность управления доступом для системных мьютексов  
 Платформа .NET Framework версии 2.0 позволяет запрашивать и настраивать безопасность управления доступом Windows для именованных системных объектов. Системные мьютексы рекомендуется защищать с момента создания, поскольку системные объекты глобальны, а значит, могут быть заблокированы не вашим кодом.  
  
 Сведения о защите и управлении доступом для мьютексов вы найдете в описаниях классов <xref:System.Security.AccessControl.MutexSecurity> и <xref:System.Security.AccessControl.MutexAccessRule>, перечисления <xref:System.Security.AccessControl.MutexRights>, методов <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> и <xref:System.Threading.Mutex.OpenExisting%2A> класса <xref:System.Threading.Mutex> и описании конструктора <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Mutex?displayProperty=nameWithType>
- <xref:System.Threading.Mutex.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.MutexSecurity?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.MutexAccessRule?displayProperty=nameWithType>
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
- [Потоки и работа с ними](threads-and-threading.md)
- [Работа с потоками](index.md)
