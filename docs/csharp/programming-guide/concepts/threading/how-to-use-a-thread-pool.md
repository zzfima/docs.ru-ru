---
title: Практическое руководство. Использование пула потоков (C#)
ms.date: 07/20/2015
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
ms.openlocfilehash: c89093bcff82715482b2ddb822916cfa5ff8ed72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340480"
---
# <a name="how-to-use-a-thread-pool-c"></a>Практическое руководство. Использование пула потоков (C#)
*Группировка потоков в пул* — это форма многопоточности, при которой задачи добавляются в очередь и при создании новых потоков запускаются автоматически. Дополнительные сведения см. в разделе [Группировка потоков в пул (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).  
  
 В следующем примере пул потоков .NET Framework используется для вычисления результата `Fibonacci` для десяти чисел в диапазоне от 20 до 40. Каждый результат `Fibonacci` представлен классом `Fibonacci`, который предоставляет метод с именем `ThreadPoolCallback`, выполняющий вычисление. Создается объект, представляющий каждое значение `Fibonacci`, а затем метод `ThreadPoolCallback` передается в объект <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, который назначает для выполнения метода доступный в пуле поток.  
  
 Поскольку каждому объекту `Fibonacci` присваивается полупроизвольное значение для расчета, а процессорное время распределяется между потоками, узнать, сколько времени займет вычисление всех десяти результатов, заранее невозможно. Именно поэтому во время конструирования каждому объекту `Fibonacci` передается экземпляр класса <xref:System.Threading.ManualResetEvent>. Каждый объект сигнализирует предоставленному объекту события о завершении расчетов, что позволяет основному потоку блокировать выполнение <xref:System.Threading.WaitHandle.WaitAll%2A> до получения результатов по всем десяти объектам `Fibonacci`. После этого метод `Main` отображает каждый результат `Fibonacci`.  
  
## <a name="example"></a>Пример  
  
```csharp  
using System;  
using System.Threading;  
  
public class Fibonacci  
{  
    private int _n;  
    private int _fibOfN;  
    private ManualResetEvent _doneEvent;  
  
    public int N { get { return _n; } }  
    public int FibOfN { get { return _fibOfN; } }  
  
    // Constructor.  
    public Fibonacci(int n, ManualResetEvent doneEvent)  
    {  
        _n = n;  
        _doneEvent = doneEvent;  
    }  
  
    // Wrapper method for use with thread pool.  
    public void ThreadPoolCallback(Object threadContext)  
    {  
        int threadIndex = (int)threadContext;  
        Console.WriteLine("thread {0} started...", threadIndex);  
        _fibOfN = Calculate(_n);  
        Console.WriteLine("thread {0} result calculated...", threadIndex);  
        _doneEvent.Set();  
    }  
  
    // Recursive method that calculates the Nth Fibonacci number.  
    public int Calculate(int n)  
    {  
        if (n <= 1)  
        {  
            return n;  
        }  
  
        return Calculate(n - 1) + Calculate(n - 2);  
    }  
}  
  
public class ThreadPoolExample  
{  
    static void Main()  
    {  
        const int FibonacciCalculations = 10;  
  
        // One event is used for each Fibonacci object.  
        ManualResetEvent[] doneEvents = new ManualResetEvent[FibonacciCalculations];  
        Fibonacci[] fibArray = new Fibonacci[FibonacciCalculations];  
        Random r = new Random();  
  
        // Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations);  
        for (int i = 0; i < FibonacciCalculations; i++)  
        {  
            doneEvents[i] = new ManualResetEvent(false);  
            Fibonacci f = new Fibonacci(r.Next(20, 40), doneEvents[i]);  
            fibArray[i] = f;  
            ThreadPool.QueueUserWorkItem(f.ThreadPoolCallback, i);  
        }  
  
        // Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents);  
        Console.WriteLine("All calculations are complete.");  
  
        // Display the results.  
        for (int i= 0; i<FibonacciCalculations; i++)  
        {  
            Fibonacci f = fibArray[i];  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN);  
        }  
    }  
}  
```  
  
 Ниже показан пример выходных значений.  
  
```  
launching 10 tasks...  
thread 0 started...  
thread 1 started...  
thread 1 result calculated...  
thread 2 started...  
thread 2 result calculated...  
thread 3 started...  
thread 3 result calculated...  
thread 4 started...  
thread 0 result calculated...  
thread 5 started...  
thread 5 result calculated...  
thread 6 started...  
thread 4 result calculated...  
thread 7 started...  
thread 6 result calculated...  
thread 8 started...  
thread 8 result calculated...  
thread 9 started...  
thread 9 result calculated...  
thread 7 result calculated...  
All calculations are complete.  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(25) = 75025  
Fibonacci(22) = 17711  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(29) = 514229  
Fibonacci(38) = 39088169  
Fibonacci(21) = 10946  
Fibonacci(27) = 196418  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [Группировка потоков в пул (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) (Работа с потоками (C#))  
 [Безопасность](../../../../standard/security/index.md)
