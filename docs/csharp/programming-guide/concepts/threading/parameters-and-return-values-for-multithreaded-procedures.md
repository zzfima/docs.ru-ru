---
title: Параметры и возвращаемые значения для многопоточных процедур (C#)
ms.date: 07/20/2015
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
ms.openlocfilehash: e27f8e67ff03260e1d13fa633064efc2059e6bdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a><span data-ttu-id="3c0f7-102">Параметры и возвращаемые значения для многопоточных процедур (C#)</span><span class="sxs-lookup"><span data-stu-id="3c0f7-102">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>
<span data-ttu-id="3c0f7-103">Предоставлять и возвращать значения в многопоточном приложении сложно, поскольку в конструктор для класса потока должна передаваться ссылка на процедуру, которая принимает аргумент и не возвращает никакое значение.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="3c0f7-104">В следующих разделах показано несколько простых способов предоставления параметров и возвращения значений из процедур в отдельных потоках.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="3c0f7-105">Предоставление параметров для многопоточных процедур</span><span class="sxs-lookup"><span data-stu-id="3c0f7-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="3c0f7-106">Лучший способ передать параметры для вызова многопоточного метода — это вложить нужный метод в класс и определить для этого класса поля, которые будут служить параметрами для нового потока.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="3c0f7-107">Преимущество этого подхода состоит в том, что новый экземпляр класса с его собственными параметрами можно создавать каждый раз, когда вам нужно запустить новый поток.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="3c0f7-108">Допустим, например, что у вас есть функция, вычисляющая площадь треугольника, как в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3c0f7-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 <span data-ttu-id="3c0f7-109">Напишем класс, в который вложена функция `CalcArea` и который создает поля для хранения входных параметров:</span><span class="sxs-lookup"><span data-stu-id="3c0f7-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```csharp  
class AreaClass  
{  
    public double Base;  
    public double Height;  
    public double Area;  
    public void CalcArea()  
    {  
        Area = 0.5 * Base * Height;  
        MessageBox.Show("The area is: " + Area.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="3c0f7-110">Чтобы использовать `AreaClass`, можно создать объект `AreaClass` и задать свойства `Base` и `Height`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3c0f7-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```csharp  
protected void TestArea()  
{  
    AreaClass AreaObject = new AreaClass();  
  
    System.Threading.Thread Thread =  
        new System.Threading.Thread(AreaObject.CalcArea);  
    AreaObject.Base = 30;  
    AreaObject.Height = 40;  
    Thread.Start();  
}  
```  
  
 <span data-ttu-id="3c0f7-111">Обратите внимание на то, что процедура `TestArea` не проверяет значение поля `Area` после вызова метода `CalcArea`.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="3c0f7-112">Поскольку `CalcArea` выполняется в отдельном потоке, поле `Area` может оказаться не заданным, если проверять его сразу после вызова `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="3c0f7-113">В следующем разделе рассматривается более удобный способ получения возвращаемых значений из многопоточных процедур.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="3c0f7-114">Получение возвращаемых значений из многопоточных процедур</span><span class="sxs-lookup"><span data-stu-id="3c0f7-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="3c0f7-115">Получение возвращаемых значений из процедур, выполняемых в отдельных потоках, осложняется тем, что процедуры не могут быть функциями, а аргументы `ByRef` использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="3c0f7-116">Самый простой способ получить возвращаемые значения — это применить компонент <xref:System.ComponentModel.BackgroundWorker>, управляющий потоками и создающий событие по завершении задачи, а затем обработать результаты с помощью обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="3c0f7-117">В следующем примере значение возвращается в результате создания события из процедуры, выполняемой в отдельном потоке:</span><span class="sxs-lookup"><span data-stu-id="3c0f7-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```csharp  
class AreaClass2  
{  
    public double Base;  
    public double Height;  
    public double CalcArea()  
    {  
        // Calculate the area of a triangle.  
        return 0.5 * Base * Height;  
    }  
}  
  
private System.ComponentModel.BackgroundWorker BackgroundWorker1  
    = new System.ComponentModel.BackgroundWorker();  
  
private void TestArea2()  
{  
    InitializeBackgroundWorker();  
  
    AreaClass2 AreaObject2 = new AreaClass2();  
    AreaObject2.Base = 30;  
    AreaObject2.Height = 40;  
  
    // Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2);  
}  
  
private void InitializeBackgroundWorker()  
{  
    // Attach event handlers to the BackgroundWorker object.  
    BackgroundWorker1.DoWork +=  
        new System.ComponentModel.DoWorkEventHandler(BackgroundWorker1_DoWork);  
    BackgroundWorker1.RunWorkerCompleted +=  
        new System.ComponentModel.RunWorkerCompletedEventHandler(BackgroundWorker1_RunWorkerCompleted);  
}  
  
private void BackgroundWorker1_DoWork(  
    object sender,  
    System.ComponentModel.DoWorkEventArgs e)  
{  
    AreaClass2 AreaObject2 = (AreaClass2)e.Argument;  
    // Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea();  
}  
  
private void BackgroundWorker1_RunWorkerCompleted(  
    object sender,  
    System.ComponentModel.RunWorkerCompletedEventArgs e)  
{  
    // Access the result through the Result property.  
    double Area = (double)e.Result;  
    MessageBox.Show("The area is: " + Area.ToString());  
}  
```  
  
 <span data-ttu-id="3c0f7-118">Параметры и возвращаемые значения можно передавать в поток пула потоков с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="3c0f7-119">Потоки таймера потоков также поддерживают объект состояния в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="3c0f7-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="3c0f7-120">Сведения о группировке потоков в пул и таймерах потоков см. в разделах [Группировка потоков в пул (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) и [Таймеры потоков (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f7-120">For information on thread pooling and thread timers, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) and [Thread Timers (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0f7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3c0f7-121">See Also</span></span>  
 [<span data-ttu-id="3c0f7-122">Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)</span><span class="sxs-lookup"><span data-stu-id="3c0f7-122">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="3c0f7-123">Группировка потоков в пул (C#)</span><span class="sxs-lookup"><span data-stu-id="3c0f7-123">Thread Pooling (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="3c0f7-124">Синхронизация потоков (C#)</span><span class="sxs-lookup"><span data-stu-id="3c0f7-124">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="3c0f7-125">События</span><span class="sxs-lookup"><span data-stu-id="3c0f7-125">Events</span></span>](../../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="3c0f7-126">Многопоточные приложения(C#)</span><span class="sxs-lookup"><span data-stu-id="3c0f7-126">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="3c0f7-127">Делегаты</span><span class="sxs-lookup"><span data-stu-id="3c0f7-127">Delegates</span></span>](../../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="3c0f7-128">Многопоточность в компонентах</span><span class="sxs-lookup"><span data-stu-id="3c0f7-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
