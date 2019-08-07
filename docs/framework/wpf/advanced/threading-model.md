---
title: Модель потоков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text on buttons [WPF], updating
- message processing [WPF], nested
- blocking operations [WPF]
- Common Language Runtime (CLR), locking mechanism
- locking mechanism of Common Language Runtime (CLR)
- threading model [WPF]
- Word [WPF], spelling checking
- button text [WPF], updating
- spelling checking in Word [WPF]
- asynchronous behavior [WPF], exposing
- nested message processing [WPF]
- reentrancy [WPF]
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
ms.openlocfilehash: da9eaf127a4db02cddbb36e53a0d0ddb5b28b841
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68818052"
---
# <a name="threading-model"></a>Модель потоков
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] призвана помочь разработчикам избежать трудностей при разработке потоков. В результате большинству [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработчиков не придется писать интерфейс, использующий более одного потока. Поскольку многопотоковые программы являются сложными и трудно отлаживаемыми, их следует избегать, если существуют однопоточные решения.  
  
 Но независимо от того, насколько хорошо спроектирована архитектура [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , ни одна из платформ не сможет предоставить однопотоковое решение для каждой проблемы. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]в близком случае, но существуют ситуации, когда несколько потоков [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] улучшают скорость реагирования или производительность приложения. После рассмотрения некоторых основных материалов в данном документе рассматриваются подобные ситуации и в завершение обсуждаются некоторые более подробные сведения.  

> [!NOTE]
>  В этом разделе обсуждается работа с потоками <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> с помощью метода для асинхронных вызовов. Асинхронные вызовы также можно выполнять, вызывая <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> метод, <xref:System.Action> принимающий или <xref:System.Func%601> в качестве параметра.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> Метод возвращает<xref:System.Windows.Threading.DispatcherOperation.Task%2A> или ,<xref:System.Windows.Threading.DispatcherOperation%601>который имеет свойство. <xref:System.Windows.Threading.DispatcherOperation> Можно использовать `await` ключевое слово со <xref:System.Windows.Threading.DispatcherOperation> связанным или с ним <xref:System.Threading.Tasks.Task>. Если необходимо <xref:System.Threading.Tasks.Task> выполнить синхронное ожидание для, возвращаемого <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, вызовите <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> метод расширения.  Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> приведет к взаимоблокировке. Дополнительные сведения об использовании <xref:System.Threading.Tasks.Task> для выполнения асинхронных операций см. в разделе Параллелизм задач.  Метод также имеет перегрузки, <xref:System.Action> принимающие или <xref:System.Func%601> в качестве параметра. <xref:System.Windows.Threading.Dispatcher.Invoke%2A>  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> Метод можно использовать для выполнения синхронных вызовов путем передачи <xref:System.Action> делегата или <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Общие сведения и Dispatcher  
 Как правило [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , приложения начинаются с двух потоков: один для обработки отрисовки, а другой [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]для управления. Поток отрисовки фактически запускается в фоновом режиме, когда [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток получает входные данные, обрабатывает события, закрашивает экран и выполняет код приложения. Большинство приложений используют один [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток, хотя в некоторых случаях лучше использовать несколько. Позже это будет рассмотрено на примере.  
  
 Поток помещает в очередь рабочие элементы внутри объекта с <xref:System.Windows.Threading.Dispatcher>именем. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Объект <xref:System.Windows.Threading.Dispatcher> выбирает рабочие элементы на основе приоритетов и выполняет каждый из них до завершения.  Каждый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток должен иметь по крайней <xref:System.Windows.Threading.Dispatcher>мере один, <xref:System.Windows.Threading.Dispatcher> и каждый из них может выполнять рабочие элементы только в одном потоке.  
  
 Хитрость в создании ориентированных на пользователя приложений заключается в том, чтобы <xref:System.Windows.Threading.Dispatcher> максимально увеличить пропускную способность, сохранив рабочие элементы небольшими. Таким образом, элементы никогда не устаревают в очереди <xref:System.Windows.Threading.Dispatcher> , ожидающей обработки. Любая задержка между входными данными и ответами может разочаровать пользователя.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Как приложения должны работать с большими операциями? Что если код включает большие вычисления или требуется запрос к базе данных на удаленном сервере? Как правило, ответ заключается в обработке большой операции в отдельном потоке, в результате [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] чего поток остается неизменным для элементов <xref:System.Windows.Threading.Dispatcher> в очереди. После завершения большой операции она может сообщить результат обратно в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток для вывода.  
  
 Исторически [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] позволяет получить доступ к элементам только создавшего их потока. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Это означает, что фоновый поток, отвечающий за некоторую длительную задачу, не может обновить текстовое поле при своем завершении. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]делает это для обеспечения целостности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] компонентов. Список может выглядеть странно, если его содержимое обновляется фоновым потоком в процессе отображения.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеет встроенный механизм взаимного исключения, который осуществляет эту координацию. Большинство классов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] классе являются производными от. <xref:System.Windows.Threading.DispatcherObject> В конструкции объект <xref:System.Windows.Threading.DispatcherObject> хранит ссылку на объект <xref:System.Windows.Threading.Dispatcher> , связанный с текущим выполняющимся потоком. Фактически, <xref:System.Windows.Threading.DispatcherObject> связывается с потоком, который его создает. Во время выполнения программы объект <xref:System.Windows.Threading.DispatcherObject> может вызвать его открытый <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> метод. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>проверяет объект, <xref:System.Windows.Threading.Dispatcher> связанный с текущим потоком, и сравнивает его со ссылкой, <xref:System.Windows.Threading.Dispatcher> хранящейся во время создания. Если они не совпадают, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> создает исключение. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>предназначен для вызова в начале каждого метода, <xref:System.Windows.Threading.DispatcherObject>принадлежащего к.  
  
 Если только один поток может изменить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], как фоновые потоки взаимодействуют с пользователем? Фоновый поток может попросить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток выполнить операцию от его имени. Это достигается путем регистрации рабочего элемента в <xref:System.Windows.Threading.Dispatcher> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. Класс предоставляет два метода для регистрации рабочих элементов: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> и <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. <xref:System.Windows.Threading.Dispatcher> Оба метода назначают делегат для выполнения. <xref:System.Windows.Threading.Dispatcher.Invoke%2A>— Это синхронный вызов, то есть он не возвращает значение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , пока поток фактически не завершит выполнение делегата. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>является асинхронным и возвращается немедленно.  
  
 <xref:System.Windows.Threading.Dispatcher> Упорядочивает элементы в своей очереди по приоритету. При добавлении элемента в <xref:System.Windows.Threading.Dispatcher> очередь можно указать десять уровней. Эти приоритеты поддерживаются в <xref:System.Windows.Threading.DispatcherPriority> перечислении. Подробные сведения об <xref:System.Windows.Threading.DispatcherPriority> уровнях можно найти [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] в документации по.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Потоки в действии: Примеры  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Пример однопоточного приложения с длительным выполнением вычислений  
 Большинство графических интерфейсов пользователя (GUI) тратят большую часть времени простоя, когда ожидают события, создаваемые в ответ на взаимодействие с пользователем. При тщательном программировании это время простоя можно использовать в конструкторе, не влияя на [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]скорость реагирования. Потоковая модель не позволяет входным данным прерывать операции, происходящие [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в потоке. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Это означает, что необходимо периодически возвращаться к, чтобы <xref:System.Windows.Threading.Dispatcher> обрабатывать ожидающие события ввода, прежде чем они станут устаревшими.  
  
 Рассмотрим следующий пример.  
  
 ![Снимок экрана, показывающий поток простых чисел.](./media/threading-model/threading-prime-numbers.png)  
  
 Это простое приложение ищет простые числа, начиная от трех и далее. Когда пользователь нажимает кнопку **Start** , начинается поиск. Когда программа находит простое число, она обновляет пользовательский интерфейс. В любой момент пользователь может остановить поиск.  
  
 При всей простоте операции поиск простых чисел может происходить бесконечно, что представляет некоторые трудности.  Если бы мы обработали весь Поиск внутри обработчика событий Click кнопки, мы никогда не предбы придать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоку возможность обрабатывать другие события. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Не сможет ответить на входные или обрабатывающие сообщения. Он бы никогда не обновил отображение и не ответил бы на нажатие кнопки.  
  
 Можно провести поиск простого числа в отдельном потоке, но тогда пришлось бы иметь дело с проблемами синхронизации. С помощью однопотокового подхода можно непосредственно обновить подпись, в которой перечислено наибольшее простое число.  
  
 Если разделить задачу вычисления на управляемые фрагменты, мы можем периодически возвращаться к <xref:System.Windows.Threading.Dispatcher> событиям обработки и. Мы можем предоставить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможность перерисовки и обработки входных данных.  
  
 Лучший способ разделить время обработки между вычислениями и обработкой событий — Управление вычислениями из <xref:System.Windows.Threading.Dispatcher>. С помощью <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> метода можно запланировать проверки простого числа в той же очереди, из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] которой отображаются события. В приведенном примере запланирована проверка только одного простого числа в каждый момент времени. После завершения проверки простого числа немедленно планируется следующая проверка. Эта проверка продолжается только после обработки ожидающих [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] событий.  
  
 ![Снимок экрана, на котором показана очередь диспетчера.](./media/threading-model/threading-dispatcher-queue.png)  
  
 С помощью этого механизма приложение [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] выполняет проверку орфографии. Проверка орфографии выполняется в фоновом режиме с использованием времени [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] простоя потока. Давайте посмотрим на код.  
  
 В следующем примере показан код XAML, который создает пользовательский интерфейс.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 В следующем примере показан код программной части.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 В следующем примере показан обработчик событий для <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Помимо обновления текста в <xref:System.Windows.Controls.Button>, этот обработчик отвечает за планирование проверки первого простого числа путем добавления делегата <xref:System.Windows.Threading.Dispatcher> в очередь. После завершения работы <xref:System.Windows.Threading.Dispatcher> этого обработчика событий будет выбран этот делегат для выполнения.  
  
 Как упоминалось ранее, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> <xref:System.Windows.Threading.Dispatcher> элемент используется для планирования выполнения делегата. В этом случае мы выбираем <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> приоритет. <xref:System.Windows.Threading.Dispatcher> Будет выполнять этот делегат только в том случае, если нет важных событий для обработки. Быстродействие [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] представляет большую важность, чем проверка числа. Также передается новый делегат, представляющий подпрограмму проверки числа.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Этот метод проверяет, является ли следующее нечетное число простым. Если это просто, метод непосредственно обновляет объект, `bigPrime` <xref:System.Windows.Controls.TextBlock> чтобы отразить его обнаружение. Мы можем сделать так потому, что вычисление происходит в том же потоке, который был использован для создания компонента. Если бы мы решили использовать отдельный поток для вычисления, нам пришлось бы использовать более сложный механизм синхронизации и выполнять обновление в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. Эта ситуация будет продемонстрирована далее.  
  
 Полный исходный код для этого примера см. в разделе [Пример однопотокового приложения с длительным выполнением вычислений](https://go.microsoft.com/fwlink/?LinkID=160038) .  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Обработка блокирующей операции с фоновым потоком  
 Обработка блокировки операций в графическом приложении может оказаться трудной задачей. Мы не будем вызывать методы блокировки из обработчиков событий, так как приложение будет остановлено. Для обработки этих операций можно использовать отдельный поток, но после этого нам нужно выполнить синхронизацию с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоком, так как мы не можем напрямую изменить GUI из нашего рабочего потока. Можно использовать <xref:System.Windows.Threading.Dispatcher.Invoke%2A> или <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> длявставки[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] делегатов в поток. <xref:System.Windows.Threading.Dispatcher> Со временем эти делегаты будут выполняться с разрешением на изменение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов.  
  
 В этом примере мы имитируем вызов удаленной процедуры, который получает прогноз погоды. Мы используем отдельный рабочий поток для выполнения этого вызова и планируем метод обновления в <xref:System.Windows.Threading.Dispatcher> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке после завершения.  
  
 ![Снимок экрана, на котором показан пользовательский интерфейс погоды.](./media/threading-model/threading-weather-ui.png)  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Ниже приведены некоторые подробности, на которые следует обратить внимание.  
  
- Создание обработчика кнопки  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 При нажатии кнопки мы отображаем рисунок часов и запускаем анимацию. Мы отключаем кнопку. Мы вызываем `FetchWeatherFromServer` метод в новом потоке, а затем возвращаем, <xref:System.Windows.Threading.Dispatcher> позволяя обрабатывать события, пока мы дожидаться накопления прогноза погоды.  
  
- Выборка погоды  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Для простоты мы фактически не используем никакого сетевого кода в данном примере. Вместо этого мы моделируем задержку доступа к сети, задав для нашего нового потока спящий режим в течение четырех секунд. В этот раз исходный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток по-прежнему выполняется и отвечает на события. Чтобы показать это, была оставлена запущенная анимация, и кнопки свертывания и развертывания также продолжают работать.  
  
 После завершения задержки и случайного выбора нашего прогноза погоды пора вернуться к [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоку. Это делается путем планирования вызова `UpdateUserInterface` [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в <xref:System.Windows.Threading.Dispatcher>потоке, использующем этот поток. В запланированный вызов этого метода передается строка, описывающая погоду.  
  
- Обновление[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Когда в потоке есть время, он выполняет запланированный вызов метода `UpdateUserInterface`. <xref:System.Windows.Threading.Dispatcher> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Этот метод останавливает анимацию часов и выбирает изображение для описания погоды. Он отображает это изображение и восстанавливает кнопку "Получить прогноз погоды".  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Несколько окон, несколько потоков  
 Для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] некоторых приложений требуется несколько окон верхнего уровня. Это вполне допустимо для одного потока или<xref:System.Windows.Threading.Dispatcher> сочетания для управления несколькими окнами, но иногда несколько потоков выполняют более качественную работу. Это особенно верно, когда существует возможность, что одно из окон будет монополизировать поток.  
  
 Проводник [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] работает таким образом. Каждое новое окно проводника принадлежит исходному процессу, однако оно создается под управлением независимого потока.  
  
 С помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> элемента управления можно отобразить веб-страницы. Можно легко создать простое подстановку Internet Explorer. Начнем с важной функции: возможности открыть новое окно браузера. Когда пользователь нажимает кнопку "Новое окно", запускается копия окна в отдельном потоке. Таким образом, долго выполняющиеся или блокирующие операции в одном из окон не блокируют все остальные окна.  
  
 На самом деле у браузера имеется своя собственная сложная поточная модель. Мы выбрали его, поскольку он знаком большинству читателей.  
  
 В следующем примере показан код.  
  
 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 В данном контексте наиболее интересными являются следующие сегменты потоков этого кода:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Этот метод вызывается при нажатии кнопки "Новое окно". Она создает новый поток и запускает его в асинхронном режиме.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Этот метод является начальной точкой для нового потока. Мы создаем новое окно под элементом управления этого потока. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]автоматически создает новый <xref:System.Windows.Threading.Dispatcher> объект для управления новым потоком. Все, что нужно сделать, чтобы сделать окно функциональным, — запустить <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Технические подробности и важные моменты  
  
### <a name="writing-components-using-threading"></a>Написание компонентов, использующих поток  
 Руководство разработчика платформы Microsoft .NET Framework описывает шаблон того, как компонент может предоставлять асинхронное поведение своим клиентам (см. раздел [Общие сведения об асинхронной модели на основе событий](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Например, предположим, что мы хотели упаковать `FetchWeatherFromServer` метод в неграфический компонент для многократного использования. После стандартного шаблона Microsoft .NET Framework это будет выглядеть примерно следующим образом.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` использовал бы один из методов, описанных выше, таких как создание фонового потока, для работы в асинхронном режиме, не блокируя вызов потока.  
  
 Одна из важнейших частей этого шаблона — вызов метода *имя_метода* `Completed` в том же потоке, который вызывал метод *имя_метода* `Async` , чтобы начать с. Это можно сделать с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , сохраняя <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, но затем неграфический компонент можно использовать только в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложениях, а не в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или ASP.NET программах.  
  
 Класс решает эту потребность — представьте ее как упрощенную <xref:System.Windows.Threading.Dispatcher> версию, которая также работает с другими [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] платформами. <xref:System.Windows.Threading.DispatcherSynchronizationContext>  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Вложенная накачка  
 Иногда нецелесообразно полностью заблокировать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток. <xref:System.Windows.MessageBox.Show%2A> Рассмотрим метод<xref:System.Windows.MessageBox> класса. <xref:System.Windows.MessageBox.Show%2A>не возвращает значение, пока пользователь не нажмет кнопку ОК. Однако он создает окно, которое должно иметь цикл обработки сообщений, чтобы быть интерактивным. Ожидая, когда пользователь нажмет кнопку "ОК", исходное окно приложения не отвечает на ввод данных пользователем. Тем не менее оно продолжает обрабатывать сообщения отображения. Исходное окно перерисовывается при его перекрытии и выведении.  
  
 ![Снимок экрана, показывающий MessageBox с кнопкой "ОК"](./media/threading-model/threading-message-loop.png)  
  
 Данное окно сообщения должно подчиняться какому-либо потоку. Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] могло бы создать новый поток специально для данного окна сообщения, но этот поток не смог бы отображать отключенные элементы в исходном окне (вспомните предыдущее обсуждение взаимного исключения). Вместо этого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует систему обработки вложенных сообщений. Класс включает специальный метод с именем <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, который сохраняет текущую точку выполнения приложения, а затем начинает новый цикл обработки сообщений. <xref:System.Windows.Threading.Dispatcher> После завершения цикла вложенных сообщений выполнение возобновляется после исходного <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> вызова.  
  
 В этом случае <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> обслуживает контекст программы при <xref:System.Windows.MessageBox>вызове.<xref:System.Windows.MessageBox.Show%2A>и запускает новый цикл обработки сообщений для перерисовки фонового окна и обработки входных данных в окне сообщения. Когда пользователь нажимает кнопку ОК и очищает всплывающее окно, вложенный цикл завершает работу и управление возобновляется после вызова <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Устаревшие перенаправленные события  
 Система перенаправленных событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] уведомляет все деревья при возникновении событий.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 При нажатии левой кнопки мыши над эллипсом `handler2` выполняется. По завершении событие передается <xref:System.Windows.Controls.Canvas> объекту, который использует `handler1` для его обработки. `handler2` Это происходит только в `handler2` том случае, если явно не помечает объект события как обработанный.  
  
 `handler2` Это может потребовать много времени на обработку этого события. `handler2`может использовать <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> для запуска вложенного цикла сообщений, который не возвращается в течение часов. Если `handler2` не помечает событие как обработанное при завершении цикла обработки сообщений, событие передается вверх по дереву, несмотря на то, что оно очень старое.  
  
### <a name="reentrancy-and-locking"></a>Повторный вход и блокировка  
 Механизм блокировки среды CLR не работает в точности так, как это возможно. один из них может ожидать, что поток полностью прекратит операцию при запросе блокировки. В действительности поток продолжает получать и обрабатывать сообщения с высоким приоритетом. Это помогает избежать взаимоблокировок и максимально повышает скорость отклика интерфейсов, но может приводить к незначительным ошибкам.  Подавляющее большинство раз не нужно ничего знать об этом, но в редких обстоятельствах (обычно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] при использовании оконных сообщений или компонентов COM STA) это может быть необходимо знать.  
  
 Большинство интерфейсов не создаются с учетом потокобезопасности, поскольку разработчики работают с предположением о [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] том, что доступ к объекту никогда не осуществляется более чем одним потоком. В этом случае один поток может вносить изменения в окружающую среду в непредвиденное время, что приводит к некорректному влиянию <xref:System.Windows.Threading.DispatcherObject> механизма взаимного исключения. Рассмотрим следующий псевдокод:  
  
 ![Схема, показывающая повторный вход в поток.](./media/threading-model/threading-reentrancy.png "Среадингринтранци")  
  
 В большинстве случаев это верно, но бывают случаи, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] когда такой непредвиденный повторный вход может привести к проблемам. Таким образом, в определенный момент времени [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызовы <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, изменяющие инструкцию блокировки для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] этого потока, используют блокировку без повторного входа, а не обычную блокировку CLR.  
  
 Итак, почему группа разработчиков CLR выбрала такое поведение? Это было связано с объектами COM STA и завершением потока. Когда объект уничтожается сборщиком мусора, `Finalize` его метод выполняется в выделенном потоке метода завершения, а [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] не в потоке. И в этом заключается проблема, поскольку объект COM STA, созданный в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке, может быть удален только [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в потоке. Среда CLR эквивалентна <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (в данном случае используется Win32's `SendMessage`). Но если [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток занят, поток завершения останавливается и объект COM STA не может быть удален, что создает серьезную утечку памяти. Так что группа разработчиков CLR сделала трудный вызов, чтобы блокировки работали так, как они делают.  
  
 Задача для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] заключается в том, чтобы избежать непредвиденного повторного входа без повторного введения утечки памяти, поэтому мы не блокируем повторного входа везде.  
  
## <a name="see-also"></a>См. также

- [Пример однопоточного приложения с длительным выполнением вычислений](https://go.microsoft.com/fwlink/?LinkID=160038)
