---
title: Классы Semaphore и SemaphoreSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- counting semaphores
- semaphores
- threading [.NET Framework], cross-process synchronization
- Semaphore class, about Semaphore class
- SemaphoreSlim class, about SemaphoreSlim class
- threading [.NET Framework], Semaphore class
ms.assetid: 7722a333-b974-47a2-a7c0-f09097fb644e
ms.openlocfilehash: b9f7c122ac8acf34f740aca5f0fafc162edcea82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127590"
---
# <a name="semaphore-and-semaphoreslim"></a>Классы Semaphore и SemaphoreSlim
<xref:System.Threading.Semaphore?displayProperty=nameWithType> Класс представляет собой именованный (общесистемный) или локальный семафор. Он является тонкой оболочкой вокруг объекта семафора Win32. Семафоры Win32 являются семафорами счета, которые могут быть использованы для управления доступом к пулу ресурсов.  
  
 <xref:System.Threading.SemaphoreSlim> Класс представляет упрощенный, быстрый семафор, который можно использовать для ожидания внутри одного процесса, когда предполагается, что времена ожидания будут очень короткими. <xref:System.Threading.SemaphoreSlim>использует максимально примитивы синхронизации, предоставляемые общеязыковой среды выполнения (CLR). Тем не менее, он также предоставляет неактивно инициализированные дескрипторы ожидания на основе ядра при необходимости поддержки ожидания для нескольких семафоров. <xref:System.Threading.SemaphoreSlim>также поддерживает использование токенов отмены, но не поддерживает именованные семафоры или использование дескриптора ожидания для синхронизации.  
  
## <a name="managing-a-limited-resource"></a>Управление ограниченным ресурсом  
 Потоки входят в семафор посредством вызова метода <xref:System.Threading.WaitHandle.WaitOne%2A>, который наследуется от класса <xref:System.Threading.WaitHandle>, в случае объекта <xref:System.Threading.Semaphore?displayProperty=nameWithType> либо метода <xref:System.Threading.SemaphoreSlim.Wait%2A?displayProperty=nameWithType> или <xref:System.Threading.SemaphoreSlim.WaitAsync%2A?displayProperty=nameWithType> в случае объекта <xref:System.Threading.SemaphoreSlim>. По возвращении вызова счетчик на семафоре уменьшается на единицу. При запросе потоком записи счетчик равен нулю, поток блокируется. Потоки освобождают семафор посредством вызова метода <xref:System.Threading.Semaphore.Release%2A?displayProperty=nameWithType> или <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>, заблокированные потоки разрешено вводить. Для входа блокированных потоков в семафор нет гарантированного порядка, например first-in, first-out (FIFO) или последним поступил — первым обслужен (LIFO).  
  
 Поток может войти в семафор несколько раз, многократно вызывая метод <xref:System.Threading.Semaphore?displayProperty=nameWithType> объекта <xref:System.Threading.WaitHandle.WaitOne%2A> или метод  <xref:System.Threading.SemaphoreSlim> объекта<xref:System.Threading.SemaphoreSlim.Wait%2A>. Чтобы освободить семафор, поток может либо вызвать метод перегрузки <xref:System.Threading.Semaphore.Release?displayProperty=nameWithType> или <xref:System.Threading.SemaphoreSlim.Release?displayProperty=nameWithType> одинаковое количество раз, либо вызвать метод перегрузки <xref:System.Threading.Semaphore.Release%28System.Int32%29?displayProperty=nameWithType> или <xref:System.Threading.SemaphoreSlim.Release%28System.Int32%29?displayProperty=nameWithType> и указать количество освобождаемых записей.  
  
### <a name="semaphores-and-thread-identity"></a>Семафоры и идентификация потоков  
 Типы два семафора не обеспечивают идентификацию потоков по вызовам методов <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.SemaphoreSlim.Wait%2A>, <xref:System.Threading.Semaphore.Release%2A> и <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>. Например, обычным сценарием использования семафора является наличие потока производителя и потока получателя. При этом один поток всегда увеличивает счетчик семафора, а другой всегда уменьшает его.  
  
 Программист должен обеспечить, чтобы поток не освобождал семафор слишком много раз. Например предположим, что семафор имеет максимальное значение счетчика равное двум, а два потока A и B входят в семафор. Если ошибка программирования в потоке B заставляет его вызывать метод `Release` дважды, оба вызова оканчиваются успешно. Счетчик на семафоре переполнен, и если поток A вызывает `Release`, <xref:System.Threading.SemaphoreFullException> создается исключение.  
  
## <a name="named-semaphores"></a>Именованные семафоры  
 Операционная система Windows позволяет присваивать семафорам имена. Именованный семафор относится ко всей системе. То есть после создания именованный семафор становится видимым для всех потоков во всех процессах. Таким образом именованный семафор может использоваться для синхронизации действий процессов, а также потоков.  
  
 Можно создать <xref:System.Threading.Semaphore> объект, который представляет именованный системный семафор с помощью одного из конструкторов, указывающих имя.  
  
> [!NOTE]
> Так как именованные семафоры относятся ко всей системе, можно иметь несколько объектов <xref:System.Threading.Semaphore>, представляющих один и тот же именованный семафор. При каждом вызове конструктора или метода <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType> создается новый объект <xref:System.Threading.Semaphore>. Если указать одно и то же имя несколько раз, создается несколько объектов, представляющих один и тот же именованный семафор.  
  
 Будьте осторожны при использовании именованных семафоров. Так как они относятся ко всей системе, другой процесс, использующий то же имя, может неожиданно войти в семафор. Вредоносный код, выполняемый на одном компьютере может использовать это как основу для атак типа "отказ в обслуживании".  
  
 Используйте безопасность управления доступом для защиты объекта <xref:System.Threading.Semaphore>, представляющего именованный семафор, предпочтительнее с помощью конструктора, который определяет объект <xref:System.Security.AccessControl.SemaphoreSecurity?displayProperty=nameWithType>. Также можно применить безопасность управления доступом с помощью метода <xref:System.Threading.Semaphore.SetAccessControl%2A?displayProperty=nameWithType>, однако это оставит брешь в защите между временем создания семафора и временем, когда он будет защищен. Защита семафоров с помощью безопасности управления доступом способствует предотвращению атак злоумышленников, но не решает проблемы непреднамеренного конфликта имен.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Semaphore>
- <xref:System.Threading.SemaphoreSlim>
- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
