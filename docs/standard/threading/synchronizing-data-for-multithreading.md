---
title: Синхронизация данных для многопоточности
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET Framework], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a7561a09b1b47827b3476b5525863503765064f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027743"
---
# <a name="synchronizing-data-for-multithreading"></a>Синхронизация данных для многопоточности
Если несколько потоков могут вызывать свойства и методы отдельного объекта, эти вызовы важно синхронизировать. В противном случае поток может прерваться действиями другого потока, а объект может остаться в недопустимом состоянии. Класс, члены которого защищены от подобных прерываний, называется потокобезопасным.  
  
 CLR предоставляет несколько способов синхронизации доступа к экземпляру и статическим членам:  
  
-   Синхронизированные области кода. Используя класс <xref:System.Threading.Monitor> или поддержку компилятора для этого класса, можно синхронизировать только тот блок кода, которому эту требуется, повысив тем самым производительность.  
  
-   Синхронизация вручную. Вы можете использовать объекты синхронизации, предоставляемые библиотекой классов .NET Framework. См. статью [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md), в которой обсуждается класс <xref:System.Threading.Monitor>.  
  
-   Синхронизированные контексты. Вы можете использовать <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> для реализации простой автоматической синхронизации для объектов <xref:System.ContextBoundObject>.  
  
-   Классы коллекции в пространстве имен <xref:System.Collections.Concurrent?displayProperty=nameWithType>. Эти классы предоставляют встроенные синхронизированные операции добавления и удаления. Дополнительные сведения см. в разделе [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
 CLR предоставляет потоковую модель, где классы делятся на ряд категорий, которые можно синхронизировать различными способами в зависимости от конкретных требований. В следующей таблице показано, какая поддержка синхронизации предоставляется для полей и методов в соответствующей категории синхронизации.  
  
|Категория|Глобальные поля|Статические поля|Статические методы|Поля экземпляра|Методы экземпляра|Определенные блоки кода|  
|--------------|-------------------|-------------------|--------------------|---------------------|----------------------|--------------------------|  
|Синхронизации нет|Нет|Нет|Нет|Нет|Нет|Нет|  
|Синхронизированные контексты|Нет|Нет|Нет|Да|Да|Нет|  
|Синхронизированные области кода|Нет|Нет|Только если помечены|Нет|Только если помечены|Только если помечены|  
|Синхронизация вручную|Вручную|Вручную|Вручную|Вручную|Вручную|Вручную|  
  
## <a name="no-synchronization"></a>Синхронизации нет  
 По умолчанию для объектов. Любой поток может получить доступ к любому методу или полю в любое время. Одновременно обращаться к этим объектам может только один поток.  
  
## <a name="manual-synchronization"></a>Синхронизация вручную  
 Библиотека классов .NET Framework предоставляет ряд классов для синхронизации потоков. См. раздел [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="synchronized-code-regions"></a>Синхронизированные области кода  
 Класс <xref:System.Threading.Monitor> или ключевое слово компилятора можно использовать для синхронизации блоков кода, методов экземпляров и статических методов. Синхронизированные статические поля не поддерживаются.  
  
 Visual Basic и C# поддерживают маркировку блоков кода ключевым словом определенного языка, оператором `lock` в C# или `SyncLock` в Visual Basic. Если код выполняется потоком, он пытается получить блокировку. Если блокировка уже получена другим потоком, поток блокируется, пока блокировка не станет доступной. Когда поток выходит из синхронизированного блока кода, блокировка снимается независимо от того, каким образом поток выходит из блока.  
  
> [!NOTE]
>  Инструкции `lock` И `SyncLock` реализуются с помощью <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>, чтобы в синхронизованной области с ними можно было использовать другие методы <xref:System.Threading.Monitor>.  
  
 Метод можно также оформить с помощью **MethodImplAttribute** и **MethodImplOptions.Synchronized**, которые действуют точно так же, как **Monitor** или одно из ключевых слов компилятора, блокируя все тело метода.  
  
 С помощью <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> можно вывести поток из операций блокировки, таких как ожидание доступа к синхронизированной области кода. **Thread.Interrupt** также используется для вывода потоков из таких операций, как <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Не блокируйте тип, т. е. `typeof(MyType)` в C#, `GetType(MyType)` в Visual Basic или `MyType::typeid` в C++, для защиты методов `static` (методы `Shared` в Visual Basic). Вместо этого используйте закрытый статический объект. Кроме того, не блокируйте методы экземпляра, используя `this` в C# (`Me` в Visual Basic). Вместо этого используйте закрытый объект. Класс или экземпляр может заблокировать чужой код, вызвав при этом взаимоблокировку или проблемы производительности.  
  
### <a name="compiler-support"></a>Поддержка компилятора  
 Visual Basic и C# поддерживают ключевое слово языка для блокировки объекта с помощью <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>. Visual Basic поддерживает оператор [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md), а C# поддерживает оператор [lock](~/docs/csharp/language-reference/keywords/lock-statement.md).  
  
 В обоих случаях, если в коде блока возникает исключение, блокировка, введенная оператором **lock** или **SyncLock**, автоматически снимается. Компиляторы C# и Visual Basic выдают блок **try**/**finally** с **Monitor.Enter** в начале оператора try и **Monitor.Exit** в блоке **finally**. Если исключение возникает в блоке **lock** или **SyncLock**, запускается обработчик **finally**, позволяющий выполнить очистку.  
  
## <a name="synchronized-context"></a>Синхронизированные контексты  
 **SynchronizationAttribute** можно использовать в любом объекте **ContextBoundObject** для синхронизации всех методов и полей экземпляра. Блокировка распространяется на все объекты с одним и тем же контекстным доменом. К методам и полям могут обращаться сразу несколько потоков, но только по одному за раз.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>  
- [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)  
- [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
- [Оператор SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md)  
- [Оператор lock](~/docs/csharp/language-reference/keywords/lock-statement.md)
