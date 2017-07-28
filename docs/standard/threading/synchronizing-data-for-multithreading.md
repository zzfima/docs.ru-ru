---
title: "Synchronizing Data for Multithreading | Microsoft Docs"
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
  - "synchronization, threads"
  - "threading [.NET Framework], synchronizing threads"
  - "managed threading"
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Synchronizing Data for Multithreading
Если несколько потоков могут вызывать свойства и методы отдельного объекта, эти вызовы необходимо синхронизовать.  В противном случае поток может прервать операцию другого потока, и объект будет иметь неверное состояние.  Класс, элементы которого защищены от подобных прерываний, называется потокобезопасным.  
  
 Общеязыковая инфраструктура содержит несколько способов синхронизации доступа к статическим элементам и элементам экземпляров.  
  
-   Синхронизованные области кода.  Для синхронизации только требуемых блоков кода в целях улучшения производительности можно воспользоваться классом <xref:System.Threading.Monitor> или поддержкой компилятора для этого класса.  
  
-   Синхронизация вручную.  Можно использовать объекты синхронизации, предоставленные в библиотеке классов .NET Framework.  См. раздел [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md), в котором обсуждается класс <xref:System.Threading.Monitor>.  
  
-   Синхронизованные контексты.  Можно использовать <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> для разрешения простой автоматической синхронизации для объектов <xref:System.ContextBoundObject>.  
  
-   Коллекция классов в пространстве имен <xref:System.Collections.Concurrent?displayProperty=fullName>.  Эти классы предоставляют синхронизированные операции добавления и удаления.  Для получения дополнительной информации см. [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
 Общеязыковая среда выполнения содержит модель, в которой классы делятся на категории, которые можно синхронизировать различными путями в соответствии с необходимыми требованиями.  В следующей таблице представлены виды поддержки синхронизации, доступные для полей и методов в заданной категории синхронизации.  
  
|Категория|Глобальные поля|Статические поля|Статические методы|Поля экземпляра|Методы экземпляра|Определенные блоки кода|  
|---------------|---------------------|----------------------|------------------------|---------------------|-----------------------|-----------------------------|  
|Без синхронизации|Нет|Нет|Нет|Нет|Нет|Нет|  
|Синхронизованный контекст|Нет|Нет|Нет|Да|Да|Нет|  
|Синхронизованные области кода|Нет|Нет|Только если помечены|Нет|Только если помечены|Только если помечены|  
|Синхронизация вручную|Вручную|Вручную|Вручную|Вручную|Вручную|Вручную|  
  
## Без синхронизации  
 Этот вариант используется по умолчанию для объектов.  Любой поток может обратиться к любому методу или полю в любое время.  К этим объектам может единовременно обращаться только один поток.  
  
## Синхронизация вручную  
 Библиотека классов .NET Framework предоставляет ряд классов для синхронизации потоков.  См. раздел [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## Синхронизованные области кода  
 Можно использовать класс <xref:System.Threading.Monitor> или ключевое слово компилятора для синхронизации блоков кода, методов экземпляра и статических методов.  Данная поддержка не распространяется на синхронизованные статические поля.  
  
 Visual Basic и C\# поддерживают маркировку блоков кода ключевым словом определенного языка: оператор `lock` в C\# или оператор `SyncLock` в Visual Basic.  Если код выполняется потоком, происходит попытка получить блокировку.  Если блокировка уже была получена другим потоком, поток блокируется до того момента, как блокировка станет доступной.  Если поток выходит из синхронизированного блока кода, блокировка освобождается независимо от способа выхода потока из блокировки.  
  
> [!NOTE]
>  Операторы `lock` и `SyncLock` реализованы с помощью методов <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> и <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName>, так что другие методы <xref:System.Threading.Monitor> могут быть использованы вместе с ними в синхронизованной области.  
  
 Также можно дополнить метод с помощью **MethodImplAttribute** и **MethodImplOptions.Synchronized**, что приведет к тому же эффекту, что и использование **Monitor** или любого ключевого слова компилятора для блокировки всей основной части метода.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> может быть использован для вывода потока из операций блокирования, таких как ожидание доступа к синхронизированной области кода.  **Thread.Interrupt** также используется для вывода потоков из операций, таких как <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Не блокируйте тип, то есть `typeof(MyType)` in C\#, `GetType(MyType)` в Visual Basic или `MyType::typeid` в C\+\+, чтобы защитить методы `static` methods \(методы `Shared` в Visual Basic\).  Вместо этого используйте закрытый статический объект.  Так же не используйте `this` в C\# \(`Me` в Visual Basic\) для блокирования методов экземпляра.  Вместо этого используйте закрытый объект.  Класс или экземпляр могут быть заблокированы другим кодом, что может привести к взаимоблокировкам или проблемам, связанным с производительностью.  
  
### Поддержка компилятора  
 Visual Basic и C\# поддерживают ключевое слово языка, которое использует <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> и <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName> для блокировки объекта.  Visual Basic поддерживает оператор [SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md); C\# поддерживает оператор [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md).  
  
 В обоих случаях блокировка, назначенная с помощью **lock** или **SyncLock**, снимается автоматически, если в блоке кода создано исключение.  Компиляторы языка C\# и Visual Basic выдают блокировку **try**\/**finally** с помощью **Monitor.Enter** в начале работы, а блокировку **finally** с помощью **Monitor.Exit**.  Если в блокировке **lock** или **SyncLock** создано исключение, запускается обработчик **finally**, разрешающий операцию очистки.  
  
## Синхронизованный контекст  
 Для синхронизации всех полей и методов экземпляров можно воспользоваться атрибутом **SynchronizationAttribute** любого объекта **ContextBoundObject**.  Все объекты в одном контекстном домене имеют одинаковую блокировку.  Доступ к методам и полям предоставляется нескольким потокам, но только один из них может обращаться к методам или полям одновременно.  
  
## См. также  
 <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)   
 [Оператор SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md)   
 [Оператор lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md)