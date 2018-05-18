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
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a>Параметры и возвращаемые значения для многопоточных процедур (C#)
Предоставлять и возвращать значения в многопоточном приложении сложно, поскольку в конструктор для класса потока должна передаваться ссылка на процедуру, которая принимает аргумент и не возвращает никакое значение. В следующих разделах показано несколько простых способов предоставления параметров и возвращения значений из процедур в отдельных потоках.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Предоставление параметров для многопоточных процедур  
 Лучший способ передать параметры для вызова многопоточного метода — это вложить нужный метод в класс и определить для этого класса поля, которые будут служить параметрами для нового потока. Преимущество этого подхода состоит в том, что новый экземпляр класса с его собственными параметрами можно создавать каждый раз, когда вам нужно запустить новый поток. Допустим, например, что у вас есть функция, вычисляющая площадь треугольника, как в следующем коде:  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 Напишем класс, в который вложена функция `CalcArea` и который создает поля для хранения входных параметров:  
  
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
  
 Чтобы использовать `AreaClass`, можно создать объект `AreaClass` и задать свойства `Base` и `Height`, как показано в следующем коде:  
  
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
  
 Обратите внимание на то, что процедура `TestArea` не проверяет значение поля `Area` после вызова метода `CalcArea`. Поскольку `CalcArea` выполняется в отдельном потоке, поле `Area` может оказаться не заданным, если проверять его сразу после вызова `Thread.Start`. В следующем разделе рассматривается более удобный способ получения возвращаемых значений из многопоточных процедур.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Получение возвращаемых значений из многопоточных процедур  
 Получение возвращаемых значений из процедур, выполняемых в отдельных потоках, осложняется тем, что процедуры не могут быть функциями, а аргументы `ByRef` использовать нельзя. Самый простой способ получить возвращаемые значения — это применить компонент <xref:System.ComponentModel.BackgroundWorker>, управляющий потоками и создающий событие по завершении задачи, а затем обработать результаты с помощью обработчика событий.  
  
 В следующем примере значение возвращается в результате создания события из процедуры, выполняемой в отдельном потоке:  
  
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
  
 Параметры и возвращаемые значения можно передавать в поток пула потоков с помощью необязательной переменной объекта состояния `ByVal` метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Потоки таймера потоков также поддерживают объект состояния в этом контексте. Сведения о группировке потоков в пул и таймерах потоков см. в разделах [Группировка потоков в пул (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) и [Таймеры потоков (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Группировка потоков в пул (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [Синхронизация потоков (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [События](../../../../csharp/programming-guide/events/index.md)  
 [Многопоточные приложения(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Делегаты](../../../../csharp/programming-guide/delegates/index.md)  
 [Многопоточность в компонентах](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
