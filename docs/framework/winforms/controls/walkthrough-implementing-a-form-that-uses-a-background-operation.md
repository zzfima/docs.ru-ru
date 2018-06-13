---
title: Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: 28b1ac924fb9b6b8cbc09db62ee33c6780bee820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542084"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a>Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция
Если какая-либо операция будет выполняться длительное время, и вы не хотите пользовательского интерфейса (UI) перестает отвечать на запросы или «зависнуть», можно использовать <xref:System.ComponentModel.BackgroundWorker> класс для выполнения операции в другом потоке.  
  
 В этом пошаговом руководстве показано, как использовать <xref:System.ComponentModel.BackgroundWorker> класса для выполнения длительных вычислений «в фоновом режиме», пока пользовательский интерфейс продолжает отвечать на запросы.  По завершении работы будет создано приложение, вычисляющее числа Фибоначчи в асинхронном режиме. Несмотря на то что вычисление крупных чисел Фибоначчи может занимать много времени, основной поток пользовательского интерфейса в результате этой задержки прерываться не будет, а форма в ходе вычисления останется рабочей.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание приложения на базе Windows  
  
-   Создание <xref:System.ComponentModel.BackgroundWorker> в форме  
  
-   Добавление обработчиков асинхронных событий  
  
-   Добавление отчетов о ходе выполнения и поддержка отмены  
  
 Полный код, используемый в этом примере, см. в разделе [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом являются создание проекта и настройка формы.  
  
#### <a name="to-create-a-form-that-uses-a-background-operation"></a>Создание формы, в которой выполняется фоновая операция  
  
1.  Создайте проект приложения Windows с именем `BackgroundWorkerExample`. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В **обозревателе решений** щелкните правой кнопкой мыши **Form1** и выберите в контекстном меню команду **Переименовать**. Измените имя файла на `FibonacciCalculator`. Чтобы переименовать все ссылки на элемент кода '`Form1`', в соответствующем запросе нажмите кнопку **Да**.  
  
3.  Перетащите <xref:System.Windows.Forms.NumericUpDown> управления из **элементов** в форму. Задать <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> свойства `1` и <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> свойства `91`.  
  
4.  Добавление двух <xref:System.Windows.Forms.Button> элементов управления в форму.  
  
5.  Переименуйте первый <xref:System.Windows.Forms.Button> управления `startAsyncButton` и задайте <xref:System.Windows.Forms.Control.Text%2A> свойства `Start Async`. Переименуйте <xref:System.Windows.Forms.Button> управления `cancelAsyncButton`и задайте <xref:System.Windows.Forms.Control.Text%2A> свойства `Cancel Async`. Задайте его <xref:System.Windows.Forms.Control.Enabled%2A> свойства `false`.  
  
6.  Создайте обработчик событий для обоих <xref:System.Windows.Forms.Button> элементов управления <xref:System.Windows.Forms.Control.Click> события. Дополнительные сведения см. в разделе [Практическое руководство. Создание обработчика событий с помощью конструктора](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Перетащите <xref:System.Windows.Forms.Label> управления из **элементов** в форму и присвойте ему `resultLabel`.  
  
8.  Перетащите <xref:System.Windows.Forms.ProgressBar> управления из **элементов** в форму.  
  
## <a name="creating-a-backgroundworker-in-your-form"></a>Создание BackgroundWorker в форме  
 Можно создать <xref:System.ComponentModel.BackgroundWorker> для асинхронной операции с помощью **Windows** **конструктор форм**.  
  
#### <a name="to-create-a-backgroundworker-with-the-designer"></a>Создание BackgroundWorker с помощью конструктора  
  
-   Из **компоненты** вкладке **элементов**, перетащите <xref:System.ComponentModel.BackgroundWorker> в форму.  
  
## <a name="adding-asynchronous-event-handlers"></a>Добавление обработчиков асинхронных событий  
 Теперь вы готовы для добавления обработчиков событий для <xref:System.ComponentModel.BackgroundWorker> асинхронных событий компонента. Один из этих обработчиков вызывает длительную операцию, вычисляющую числа Фибоначчи в фоновом режиме.  
  
#### <a name="to-implement-asynchronous-event-handlers"></a>Реализация обработчиков асинхронных событий  
  
1.  В **свойства** окне с <xref:System.ComponentModel.BackgroundWorker> выбранном компоненте щелкните **события** кнопки. Дважды щелкните <xref:System.ComponentModel.BackgroundWorker.DoWork> и <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> событий для создания обработчиков событий. Дополнительные сведения о том, как использовать обработчики событий, см. в разделе [Практическое руководство. Создание обработчиков событий с помощью конструктора](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Создайте в форме новый метод с именем `ComputeFibonacci`. Этот метод выполняет фактическую работу и делает это в фоновом режиме. Данный код демонстрирует рекурсивную реализацию алгоритма Фибоначчи — она довольно неэффективна и занимает в разы больше времени при работе с большими числами. Он приводится в иллюстративных целях, чтобы показать, что операция может значительно замедлить работу вашего приложения.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  В <xref:System.ComponentModel.BackgroundWorker.DoWork> обработчик событий, добавьте вызов `ComputeFibonacci` метод. Возьмите первый параметр `ComputeFibonacci` из <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs>. <xref:System.ComponentModel.BackgroundWorker> И <xref:System.ComponentModel.DoWorkEventArgs> параметры будут использоваться позже для отчета о ходе выполнения и отмены поддержки. Присвоить значение, возвращаемое из `ComputeFibonacci` для <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> свойство <xref:System.ComponentModel.DoWorkEventArgs>. Этот результат будет доступен для <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.BackgroundWorker.DoWork> Не ссылается на обработчик событий `backgroundWorker1` переменную экземпляра напрямую, как это будет привязать этот обработчик событий к определенному экземпляру <xref:System.ComponentModel.BackgroundWorker>. Вместо этого ссылка на <xref:System.ComponentModel.BackgroundWorker> , вызвавшего это событие восстанавливается из `sender` параметра. Это важно, если в форме размещено несколько <xref:System.ComponentModel.BackgroundWorker>. Нельзя выполнять действия любые объекты пользовательского интерфейса в вашей <xref:System.ComponentModel.BackgroundWorker.DoWork> обработчика событий. Вместо этого взаимодействия с пользовательским интерфейсом посредством <xref:System.ComponentModel.BackgroundWorker> события.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  В `startAsyncButton` элемента управления <xref:System.Windows.Forms.Control.Click> обработчика событий, добавьте код, который начинает асинхронную операцию.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  В <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> обработчика событий, присвоить его результат вычисления для `resultLabel` элемента управления.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## <a name="adding-progress-reporting-and-support-for-cancellation"></a>Добавление отчетов о ходе выполнения и поддержка отмены  
 В случае асинхронных операций, занимающих долгое время, желательно сообщать пользователю о ходе выполнения, чтобы пользователь мог отменить операцию. <xref:System.ComponentModel.BackgroundWorker> Класс предоставляет событие, которое позволяет публиковать ход выполнения фоновой операции. Он также предоставляет флаг, который позволяет рабочему коду обнаружить вызов <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> и прервать свою работу.  
  
#### <a name="to-implement-progress-reporting"></a>Реализация отчета о ходе выполнения  
  
1.  В окне **Свойства** выберите `backgroundWorker1`. Задайте для свойств <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> и <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> значение `true`.  
  
2.  Объявите две переменные в форме `FibonacciCalculator`. Они будут использоваться для отслеживания хода выполнения.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Добавьте обработчик для события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>. В <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> обработчик событий, обновление <xref:System.Windows.Forms.ProgressBar> с <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> свойство <xref:System.ComponentModel.ProgressChangedEventArgs> параметр.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### <a name="to-implement-support-for-cancellation"></a>Реализация поддержки отмены  
  
1.  В `cancelAsyncButton` элемента управления <xref:System.Windows.Forms.Control.Click> обработчика событий, добавьте код, который Отменяет асинхронную операцию.  
  
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
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно скомпилировать и запустить приложение калькулятора Фибоначчи.  
  
#### <a name="to-test-your-project"></a>Тестирование проекта  
  
-   Чтобы скомпилировать и запустить приложение, нажмите клавишу F5.  
  
     Пока вычисление выполняется в фоновом режиме, вы увидите <xref:System.Windows.Forms.ProgressBar> отображением хода выполнения вычислений. Операцию, ожидающую выполнения, можно отменить.  
  
     Если числа небольшие, вычисления выполняются быстро, а с крупными числами занимают заметно больше времени. Если ввести значение 30 или больше, задержка составит несколько секунд, в зависимости от скорости работы вашего компьютера. Для значений больше 40 вычисление может затянуться на несколько часов. Пока калькулятор вычисляет большое число Фибоначчи, форму можно свободно переместить, свернуть, развернуть и даже закрыть. Это связано с тем, что основной поток пользовательского интерфейса не дожидается, пока вычисление будет завершено.  
  
## <a name="next-steps"></a>Следующие шаги  
 Теперь, когда вы реализовали форму, которая использует <xref:System.ComponentModel.BackgroundWorker> компонента для вычислений в фоновом режиме, можно исследовать другие возможности для асинхронных операций:  
  
-   Используйте несколько <xref:System.ComponentModel.BackgroundWorker> объектов для нескольких одновременных операций.  
  
-   Отладка многопоточных приложений (см. раздел [Практическое руководство. Использование окна потоков](/visualstudio/debugger/how-to-use-the-threads-window)).  
  
-   Реализация собственного компонента, поддерживающего модель асинхронного программирования. Дополнительные сведения см. в разделе [Обзор асинхронной модели на основе событий](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
    > [!CAUTION]
    >  При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок. Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Рекомендации по работе с потоками](../../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Многопоточность в компонентах](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 (Не относится к этой сборке) [Многопоточность в Visual Basic](http://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Пример. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 [Компонент BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
