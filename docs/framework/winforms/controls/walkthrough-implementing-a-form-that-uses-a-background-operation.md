---
title: "Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "фоновые операции"
  - "фоновые задачи"
  - "BackgroundWorker - компонент"
  - "формы, фоновые операции"
  - "формы, многопоточность"
  - "работа с потоками [Windows Forms], фоновые операции"
  - "работа с потоками [Windows Forms], формы"
  - "работа с потоками [Windows Forms], пошаговые руководства"
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция
Если какая\-либо операция будет выполняться в течение долгого времени, и при этом требуется не допустить, чтобы пользовательский интерфейс перестал отвечать на запросы пользователя или "завис", можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.  
  
 В этом пошаговом руководстве показано использование класса <xref:System.ComponentModel.BackgroundWorker> для выполнения длительных вычислений в фоновом режиме, при сохранении работоспособности пользовательского интерфейса.  По завершении работы будет создано приложение, вычисляющее числа Фибоначии в асинхронном режиме.  Несмотря на то, что вычисление крупных чисел Фибоначчи может занять немало времени, основной поток пользовательского интерфейса не будет прерван, а форма будет отвечать на запросы пользователя во время вычисления.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание приложения Windows  
  
-   Создание <xref:System.ComponentModel.BackgroundWorker> в форме  
  
-   Добавление асинхронных обработчиков событий  
  
-   Добавление отчета о ходе выполнения и поддержки отмены  
  
 Полный текст кода для текущего примера см. в разделе [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Создание проекта  
 Для начала следует создать проект и подготовить форму.  
  
#### Чтобы создать форму, использующую фоновую операцию  
  
1.  Создайте проект приложения Windows под названием `BackgroundWorkerExample`.  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В **Обозревателе решений** щелкните правой кнопкой мыши **Form1** и выберите в контекстном меню **Переименовать**.  Измените имя файла на `FibonacciCalculator`.  Нажмите кнопку **Да**, чтобы переименовать все ссылки на элемент кода `Form1`.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.NumericUpDown> из **панели элементов** в форму.  Установите свойство <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> равным `1`, а свойство <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> равным `91`.  
  
4.  Добавьте в форму два элемента управления <xref:System.Windows.Forms.Button>.  
  
5.  Переименуйте первый элемент управления <xref:System.Windows.Forms.Button> `startAsyncButton` и установите свойство <xref:System.Windows.Forms.Control.Text%2A> равным `Start Async`.  Переименуйте второй элемент управления <xref:System.Windows.Forms.Button> `cancelAsyncButton` и установите свойство <xref:System.Windows.Forms.Control.Text%2A> равным `Cancel Async`.  Установите для свойства <xref:System.Windows.Forms.Control.Enabled%2A> значение `false`.  
  
6.  Создайте обработчик событий для событий <xref:System.Windows.Forms.Control.Click> обоих элементов управления <xref:System.Windows.Forms.Button>.  Дополнительные сведения см. в разделе [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ru-ru/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Перетащите элемент управления <xref:System.Windows.Forms.Label> из **панели элементов** в форму и переименуйте его в `resultLabel`.  
  
8.  Перетащите элемент управления <xref:System.Windows.Forms.ProgressBar> из **панели элементов** в форму.  
  
## Создание BackgroundWorker в форме  
 Можно создать <xref:System.ComponentModel.BackgroundWorker> для асинхронной операции с помощью **конструктора** **Windows**.  
  
#### Чтобы создать BackgroundWorker с помощью конструктора  
  
-   Со вкладки **Компоненты** **панели элементов** перетащите <xref:System.ComponentModel.BackgroundWorker>.  
  
## Добавление асинхронных обработчиков событий  
 Теперь можно добавить обработчики событий для асинхронных событий компонента <xref:System.ComponentModel.BackgroundWorker>.  Длительная вычислительная операция, вычисляющая числа Фибоначчи, будет запущена в фоновом режиме и вызывается одним из этих обработчиков.  
  
#### Реализация асинхронных обработчиков событий  
  
1.  В окне **Свойства** \(при выбранном компоненте <xref:System.ComponentModel.BackgroundWorker>\) нажмите кнопку **События**.  Дважды щелкните события <xref:System.ComponentModel.BackgroundWorker.DoWork>и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, чтобы создать обработчики событий.  Дополнительные сведения об использовании обработчиков событий см. в разделе [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ru-ru/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Создайте в форме в новый метод с именем `ComputeFibonacci`.  Этот метод будет выполнять вычисления, он будет запущен в фоновом режиме.  Код демонстрирует рекурсивную реализацию алгоритма Фибоначчи — она весьма неэффективна, вычисление больших чисел Фибоначчи с ее помощью занимает немало времени.  Она используется здесь для иллюстрации: чтобы показать, как выполнение операции может вызвать значительные задержки в работе приложения.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  В обработчике событий <xref:System.ComponentModel.BackgroundWorker.DoWork> добавьте вызов метода `ComputeFibonacci`.  Возьмите первый параметр `ComputeFibonacci` из свойства <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs>.  Параметры <xref:System.ComponentModel.BackgroundWorker> и <xref:System.ComponentModel.DoWorkEventArgs> будут использованы позднее для поддержки отчета о ходе выполнения и отмены.  Присвойте значение, возвращенное из `ComputeFibonacci`, свойству <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs>.  Результат будет доступен для обработчика событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
    > [!NOTE]
    >  Обработчик события <xref:System.ComponentModel.BackgroundWorker.DoWork> не ссылается на переменную экземпляра `backgroundWorker1` напрямую, поскольку в этом случае обработчик будет связан с определенным экземпляром <xref:System.ComponentModel.BackgroundWorker>.  Вместо этого ссылка на <xref:System.ComponentModel.BackgroundWorker>, создавший событие, берется из параметра `sender`.  Это важно, если в форме размещено несколько <xref:System.ComponentModel.BackgroundWorker>.  В обработчике событий <xref:System.ComponentModel.BackgroundWorker.DoWork> нельзя выполнять действия ни с одним из объектов пользовательского интерфейса.  Вместо этого следует взаимодействовать с пользовательским интерфейсом с помощью событий <xref:System.ComponentModel.BackgroundWorker>.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  В обработчике события <xref:System.Windows.Forms.Control.Click> элемента управления `startAsyncButton` добавьте код, запускающий асинхронную операцию.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  Назначьте результат вычислений средству управления `resultLabel` в обработчике событий <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## Добавление отчета о ходе выполнения и поддержки отмены  
 Для длительных асинхронных операций часто желательно сообщать пользователю о ходе выполнения и дать ему возможность отменить операцию.  Класс <xref:System.ComponentModel.BackgroundWorker> предоставляет событие, позволяющее публиковать ход выполнения фоновой операции.  Также предоставляется флаг, позволяющий рабочему коду обнаружить вызов <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> и прервать свою работу.  
  
#### Для внедрения отчета о ходе выполнения  
  
1.  В окне **Свойства** выберите `backgroundWorker1`.  Установите свойствам <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> значение `true`.  
  
2.  Объявите две переменные в форме `FibonacciCalculator`.  Они будут использоваться для отслеживания хода выполнения.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Добавьте обработчик события для события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  В обработчике события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> обновите <xref:System.Windows.Forms.ProgressBar> со свойством <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> параметра <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### Для реализации поддержки отмены  
  
1.  В обработчике события <xref:System.Windows.Forms.Control.Click> элемента управления `cancelAsyncButton` добавьте код, отменяющий асинхронную операцию.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  Следующие фрагменты кода в методе `ComputeFibonacci` сообщают о ходе выполнения и поддерживают отмену.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## Контрольная точка  
 Теперь можно скомпилировать и запустить приложение "Fibonacci Calculator".  
  
#### Проверка проекта  
  
-   Нажмите клавишу F5, чтобы скомпилировать и запустить приложение.  
  
     При выполнении вычислений в фоновом режиме вы увидите <xref:System.Windows.Forms.ProgressBar> с отображением хода выполнения вычислений.  Также можно отменить выполняющуюся операцию.  
  
     Для небольших чисел вычисление будет выполняться очень быстро, но при вычислении больших чисел возникнут задержки.  При вводе значения 20 или более задержка может составить несколько секунд \(в зависимости от мощности компьютера\).  Для значений, превышающих 40, вычисление может занять от нескольких минут до нескольких часов.  Обратите внимание, что пока калькулятор вычисляет большой число Фибоначчи, можно свободно перемещать форму, сворачивать ее, разворачивать и даже закрывать.  Это возможно из\-за того, что основной поток пользовательского интерфейса не дожидается завершения вычисления.  
  
## Следующие действия  
 Итак, мы реализовали форму, использующую компонент <xref:System.ComponentModel.BackgroundWorker> для вычислений в фоновом режиме. Теперь можно изучить другие возможности асинхронной работы.  
  
-   Используйте несколько объектов <xref:System.ComponentModel.BackgroundWorker> для нескольких одновременных операций.  
  
-   Сведения об отладке многопоточных приложений см. в разделе [Практическое руководство. Использование окна потоков](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
-   Реализуйте собственный компонент, поддерживающий асинхронную модель программирования.  Дополнительные сведения см. в разделе [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
    > [!CAUTION]
    >  При использовании многопоточных программ возникает опасность весьма серьезных и сложных ошибок.  Ознакомьтесь с разделом [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) перед реализацией любых решений, использующих многопоточность.  
  
## См. также  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ru-ru/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Пример. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)   
 [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)