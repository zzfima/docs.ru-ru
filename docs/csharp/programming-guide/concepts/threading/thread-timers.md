---
title: Таймеры потоков (C#)
ms.date: 07/20/2015
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
ms.openlocfilehash: c2be9fef0b3f6f3db7ae8c9a519ece0cb64b6f49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323447"
---
# <a name="thread-timers-c"></a><span data-ttu-id="11968-102">Таймеры потоков (C#)</span><span class="sxs-lookup"><span data-stu-id="11968-102">Thread Timers (C#)</span></span>
<span data-ttu-id="11968-103">Класс <xref:System.Threading.Timer?displayProperty=nameWithType> полезно использовать для периодического выполнения задачи в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="11968-103">The <xref:System.Threading.Timer?displayProperty=nameWithType> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="11968-104">Например, можно использовать таймер потока для проверки состояния и целостности базы данных или для создания резервных копий важных файлов.</span><span class="sxs-lookup"><span data-stu-id="11968-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="11968-105">Пример таймера потока</span><span class="sxs-lookup"><span data-stu-id="11968-105">Thread Timer Example</span></span>  
 <span data-ttu-id="11968-106">В следующем примере задача запускается каждые две секунды и использует флаг для инициализации метода <xref:System.IDisposable.Dispose%2A>, который останавливает таймер.</span><span class="sxs-lookup"><span data-stu-id="11968-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="11968-107">В этом примере сведения о состояния отображаются в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="11968-107">This example posts status to the output window.</span></span>  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="11968-108">Таймеры потоков особенно полезны в случае отсутствия доступа к объекту <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>, например при разработке консольных приложений.</span><span class="sxs-lookup"><span data-stu-id="11968-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11968-109">См. также</span><span class="sxs-lookup"><span data-stu-id="11968-109">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="11968-110">Многопоточные приложения(C#)</span><span class="sxs-lookup"><span data-stu-id="11968-110">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
