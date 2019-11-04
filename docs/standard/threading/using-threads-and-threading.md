---
title: Использование потоков и работа с потоками
ms.date: 08/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
ms.openlocfilehash: 863fa565f7c107214273912a6d110b7664bffe6b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131500"
---
# <a name="using-threads-and-threading"></a>Использование потоков и работа с потоками

С помощью языка .NET можно создавать приложения, которые выполняют несколько операций одновременно. Операции, которые потенциально могут задержать выполнение других операций, выполняются в отдельных потоках; такой способ организации работы приложения называется *многопоточностью* или *свободным созданием потоков*.  
  
Приложения, использующие многопоточность, более оперативно реагируют на действия пользователя, поскольку пользовательский интерфейс остается активным, в то время как задачи, требующие интенсивной работы процессора, выполняются в других потоках. Многопоточность также эффективна при создании масштабируемых приложений, поскольку пользователь может добавлять потоки при увеличении рабочей нагрузки.

> [!NOTE]
> Если требуется больший контроль над поведением потоков приложения, можно управлять потоками самостоятельно. Но начиная с .NET Framework 4 многопоточное программирование значительно упростилось благодаря классам <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/parallel-linq-plinq.md), новым классам параллельных коллекций из пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> и новой модели программирования, которая вместо потоков использует концепцию задач. Дополнительные сведения см. в статье [Параллельное программирование в .NET](../parallel-programming/index.md) и [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md).

## <a name="how-to-create-and-start-a-new-thread"></a>Практическое руководство. Создание и запуск нового потока

Чтобы создать поток, создайте новый экземпляр класса <xref:System.Threading.Thread?displayProperty=nameWithType> и укажите в конструкторе имя метода, который должен выполняться в новом потоке. Чтобы запустить созданный поток, вызовите метод <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>. Дополнительные сведения и примеры см. в статье [Создание потоков и передача данных во время запуска](creating-threads-and-passing-data-at-start-time.md) и справочнике по API <xref:System.Threading.Thread>.

## <a name="how-to-stop-a-thread"></a>Практическое руководство. Остановка потока

Чтобы прервать выполнение потока, используйте метод <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Этот метод вызывает <xref:System.Threading.ThreadAbortException> в потоке, для которого был вызван. Дополнительные сведения см. в разделе [Уничтожение потоков](destroying-threads.md).

Начиная с .NET Framework 4 вы можете использовать <xref:System.Threading.CancellationToken?displayProperty=nameWithType> для совместной отмены потока. Подробные сведения см. в статье [Отмена в управляемых потоках](cancellation-in-managed-threads.md).

Используйте метод <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, чтобы вызывающий поток ждал завершения потока, для которого был вызван метод.

## <a name="how-to-pause-or-interrupt-a-thread"></a>Практическое руководство. Приостановка или прерывание потока

Используйте метод <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>, чтобы приостановить текущий поток на определенное время. Заблокированный поток можно прервать путем вызова метода <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Приостановка и прерывание потоков](pausing-and-resuming-threads.md).

## <a name="thread-properties"></a>Свойства потока

В приведенной ниже таблице показаны некоторые свойства <xref:System.Threading.Thread>.  
  
|Свойство.|ОПИСАНИЕ|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Возвращает `true`, если поток был запущен и не был завершен нормально либо был прерван.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Возвращает или задает логическое значение, которое указывает, является ли поток фоновым потоком. Фоновые потоки отличаются от основных потоков лишь тем, что они не влияют на завершение процесса. Когда обработка всех основных потоков закончена, общеязыковая среда выполнения завершает процесс, применяя метод <xref:System.Threading.Thread.Abort%2A> к тем фоновым потокам, которые еще продолжают существовать. См. дополнительные сведения об [основных и фоновых потоках](foreground-and-background-threads.md).|  
|<xref:System.Threading.Thread.Name%2A>|Возвращает или задает имя потока. Наиболее часто используется для обнаружения отдельных потоков при отладке.|  
|<xref:System.Threading.Thread.Priority%2A>|Возвращает или задает значение <xref:System.Threading.ThreadPriority>, которое используется операционной системой для установки приоритетов потоков. Дополнительные сведения см. в разделе [Планирование потоков](scheduling-threads.md) и в справочнике по <xref:System.Threading.ThreadPriority>.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Возвращает значение <xref:System.Threading.ThreadState>, содержащее текущие состояния потока.|  

## <a name="see-also"></a>См. также

- <xref:System.Threading.Thread?displayProperty=nameWithType>
- [Потоки и работа с потоками](threads-and-threading.md)
- [Параллельное программирование](../parallel-programming/index.md)
