---
title: "Модель потоков | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "текст на кнопках, обновление"
  - "обработки сообщения, вложенные"
  - "блокирующие операции"
  - "Dispatcher - класс"
  - "Common Language Runtime (CLR), механизм блокировки"
  - "механизм блокировки среды CLR"
  - "потоковая модель"
  - "классы, DependencyObject"
  - "Word, проверка орфографии проверка"
  - "текст, кнопки обновления"
  - "проверка в Word"
  - "асинхронное поведение предоставление"
  - "DependencyObject - класс"
  - "обработка вложенных сообщений"
  - "классы, диспетчер"
  - "повторный вход"
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Модель потоков
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]призвана помочь разработчикам избежать трудностей при разработке потоков. В результате большинство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработчиков не требуется писать интерфейс, использующий более одного потока. Поскольку многопотоковые программы являются сложными и трудно отлаживаемыми, их следует избегать, если существуют однопотоковые решения.  
  
 Независимо от того, насколько хорошо архитектурой, однако нет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework никогда не сможете предоставить однопоточное решение для каждого типа задач.              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Идет закрыть, но по-прежнему существуют ситуации, в которых несколько потоков улучшают [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] отклика или производительность приложения. После обсуждения некоторых исходных материалов, в этом документе рассматриваются эти ситуации и затем завершается обсуждением некоторых сведений нижнего уровня.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
> [!NOTE]
>  В этом разделе обсуждаются потоки с помощью <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> метод для асинхронных вызовов. Вы также можете асинхронных вызовов, вызвав <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> метод, который будет принимать <xref:System.Action> или <xref:System.Func%601> как параметр.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> возвращает метод <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, который имеет <xref:System.Windows.Threading.DispatcherOperation.Task%2A> свойство. Можно использовать `await` ключевого слова with либо <xref:System.Windows.Threading.DispatcherOperation> или связанный с ним <xref:System.Threading.Tasks.Task>. Если требуется отложить синхронно <xref:System.Threading.Tasks.Task> , возвращаемый <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, вызовите <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> метода расширения.  Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> привести к взаимоблокировке. Дополнительные сведения об использовании <xref:System.Threading.Tasks.Task> для выполнения асинхронных операций, в разделе параллелизм задач.  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> метод также имеет перегрузки, принимающие <xref:System.Action> или <xref:System.Func%601> как параметр.  Можно использовать <xref:System.Windows.Threading.Dispatcher.Invoke%2A> вызывает синхронный метод, передавая делегат, <xref:System.Action> или <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Обзор и диспетчер  
 Как правило [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения начинается с двух потоков: одного для обработки отрисовки и другого для управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Поток отрисовки эффективно выполняется скрыто в фоновом режиме при [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток получает входные данные, обрабатывает события, выводит изображение на экран и выполняет код приложения. Большинство приложений используют один [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток, хотя в некоторых случаях лучше использовать несколько. Мы рассмотрим это на примере ниже.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Поток очереди рабочих элементов внутри объекта, называемого <xref:System.Windows.Threading.Dispatcher>. <xref:System.Windows.Threading.Dispatcher> выбирает рабочие элементы на основе приоритетов и выполняет каждый из них до завершения.  Каждый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток должен иметь по крайней мере один <xref:System.Windows.Threading.Dispatcher>и каждая <xref:System.Windows.Threading.Dispatcher> может выполнять рабочие элементы только в одном потоке.  
  
 Условием для построения быстро реагирующих, понятные пользователю приложений является максимальное повышение <xref:System.Windows.Threading.Dispatcher> пропускной способности, сохранения рабочие элементы небольшими. Этот способ элементы никогда не устаревают <xref:System.Windows.Threading.Dispatcher> очереди, ожидающих обработки. Любая задержка между входными данными и ответами может разочаровывать пользователя.  
  
 Как в таком случае [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения должны обрабатывать большие операции? Что делать, если код включает большие вычисления или требуется запрос к базе данных на удаленном сервере? Как правило, дает большие операции обрабатываются в отдельном потоке, оставляя [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток для обслуживания элементов в <xref:System.Windows.Threading.Dispatcher> очереди. После завершения большой операции, она может передать результат обратно [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток для отображения.  
  
 Исторически [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] позволяет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы только из потока, который создал их. Это означает, что фоновый поток владеет некоторые длительную задачу не может обновить текстовое поле, при его завершении.                  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]Это делается, чтобы обеспечить целостность [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] компонентов. Поле со списком может выглядеть странно, если его содержимое было обновлено фоновым потоком в процессе отображения.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]имеет встроенный механизм взаимного исключения, осуществляет эту координацию. Большинство классов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются производными от <xref:System.Windows.Threading.DispatcherObject>. При создании <xref:System.Windows.Threading.DispatcherObject> хранит ссылку на <xref:System.Windows.Threading.Dispatcher> связан с текущим выполняемым потоком. В результате <xref:System.Windows.Threading.DispatcherObject> связывается с потоком, который его создал. Во время выполнения программы <xref:System.Windows.Threading.DispatcherObject> может вызвать свой открытый <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> метод.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> проверяет <xref:System.Windows.Threading.Dispatcher> связанный с текущим потоком и сравнивает его <xref:System.Windows.Threading.Dispatcher> сохраняется во время создания ссылки. Если они не совпадают, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> приводит к возникновению исключения.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> предназначен для вызова в начале каждого метода, принадлежащего к <xref:System.Windows.Threading.DispatcherObject>.  
  
 Если только один поток может изменить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], как фоновые потоки взаимодействуют с пользователем? Фоновый поток может запросить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток для выполнения операции от его имени. Это достигается путем регистрации рабочего элемента с <xref:System.Windows.Threading.Dispatcher> из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока. <xref:System.Windows.Threading.Dispatcher> класс предоставляет два метода для регистрации рабочих элементов: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> и <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Оба метода назначают делегат для выполнения.                  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> является синхронным вызовом — то есть, он не возвращает до [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток не закончит выполнение делегата.                  <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> является асинхронным и немедленно возвращается.  
  
 <xref:System.Windows.Threading.Dispatcher> упорядочивает элементы в своей очереди по приоритету. Существуют десять уровней, которые могут быть указаны при добавлении элемента к <xref:System.Windows.Threading.Dispatcher> очереди. Эти приоритеты сохраняются в <xref:System.Windows.Threading.DispatcherPriority> перечисления. Подробные сведения о <xref:System.Windows.Threading.DispatcherPriority> уровней можно найти в [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] документации.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Потоки в действии: примеры  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Однопоточном приложении с длительным выполнением вычислений  
 Большинство [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] тратят большую часть своего времени простоя, ожидая события, создаваемые в ответ на взаимодействие с пользователем. При внимательном программировании это время простоя можно использовать конструктивно, не затрагивая [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Потоковая модель не позволяет вводу прерывать операцию, которая происходит в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. Это означает, что вы должны быть уверены, чтобы вернуться к <xref:System.Windows.Threading.Dispatcher> периодически, чтобы обработать отложенные события ввода, прежде чем они станут устаревшими.  
  
 Рассмотрим следующий пример.  
  
 ![Снимок экрана начальных чисел](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.png "ThreadingPrimeNumberScreenShot")  
  
 Это простое приложение вверх отсчитывается от трех ищет простые числа. Когда пользователь щелкает **запустить** кнопки, поиск начинается. Когда программа находит простое число, она обновляет пользовательский интерфейс с его обнаружения. В любой точке пользователь может остановить поиск.  
  
 Простоте поиск простых чисел может происходить бесконечно, что представляет некоторые трудности.  Если бы обработка всего поиска выполнялась внутри обработчика события click кнопки, никогда бы не получил [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков возможность для обработки других событий. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Сможет отвечать на входные данные или обработать сообщения. Он бы никогда не обновил отображение и никогда не отвечать на нажатия кнопок.  
  
 Можно провести поиск простого числа в отдельном потоке, но тогда пришлось бы иметь дело с проблемами синхронизации. С помощью однопотокового подхода можно непосредственно обновить метку, которая перечисляет наибольшее простое число.  
  
 Если разбить задачу вычисления на управляемые фрагменты, можно периодически возвращаться к <xref:System.Windows.Threading.Dispatcher> и обработки событий. Мы можем дать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможность обновлять и обрабатывать ввод.  
  
 Лучшим способом разбиения времени обработки между вычислением и обработкой события является управление вычислением из <xref:System.Windows.Threading.Dispatcher>. С помощью <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> метод, можно запланировать проверку простого числа в той же очереди, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] события, являются производными от. В нашем примере запланирована проверка только одного простого числа одновременно. После завершения проверки простого числа, мы планируем следующую проверку немедленно. Эта проверка выполняется только после ожидающих [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] обработки событий.  
  
 ![Иллюстрация очереди отправителя](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)]выполняет проверку орфографии, с помощью этого механизма. Проверка орфографии выполняется в фоновом режиме, используя время простоя [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока. Давайте взглянем на код.  
  
 В следующем примере показано XAML, который создает пользовательский интерфейс.  
  
 [!code-xml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 В следующем примере показано кода.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 В следующем примере показан обработчик событий для <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Помимо обновления текста в <xref:System.Windows.Controls.Button>, этот обработчик отвечает за планирование проверки первого простого числа путем добавления делегата к <xref:System.Windows.Threading.Dispatcher> очереди. Иногда после завершения работы, этот обработчик событий <xref:System.Windows.Threading.Dispatcher> выбирает этот делегат для выполнения.  
  
 Как упоминалось ранее, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> — <xref:System.Windows.Threading.Dispatcher> элемент, использованный при планировании делегата для выполнения. В этом случае мы выбираем <xref:System.Windows.Threading.DispatcherPriority> приоритет. <xref:System.Windows.Threading.Dispatcher> будет выполнять данный делегат только при отсутствии важных событий для обработки.                          [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]скорость реагирования более важна, чем проверка числа. Кроме того, мы передаем новый делегат, представляющий подпрограмму проверки числа.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Этот метод проверяет, является ли следующее нечетное число простым. Если оно простое, метод непосредственно обновляет `bigPrime` <xref:System.Windows.Controls.TextBlock> в соответствии с его обнаружения. Это можно сделать потому, что вычисление происходит в том же потоке, который был использован для создания компонента. Бы мы решили использовать отдельный поток для вычислений, нам пришлось бы использовать более сложный механизм синхронизации и выполнять обновления в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. Далее будут продемонстрированы этой ситуации.  
  
 Полный исходный код для этого примера, в разделе [однопотокового приложения с образцом длительных вычислений](http://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Обработка блокирующей операции с фоновым потоком  
 Обработка блокировки операций в графическом приложении может быть затруднено. Мы не хотим вызвать методы блокировки из обработчиков событий, так как приложение будет остановлено. Можно использовать отдельный поток для обработки этих операций, но когда мы это сделаем, нам нужно будет синхронизироваться с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков, поскольку нельзя непосредственно изменить [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] из рабочего потока. Мы можем использовать <xref:System.Windows.Threading.Dispatcher.Invoke%2A> или <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> вставку делегатов в <xref:System.Windows.Threading.Dispatcher> из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока. В конечном счете, эти делегаты будут выполнены с разрешением на изменение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы.  
  
 В этом примере мы имитируют вызов удаленной процедуры, который получает прогноз погоды. Мы используем отдельный рабочий поток для выполнения этого вызова и планируем метод обновления в <xref:System.Windows.Threading.Dispatcher> из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков, когда мы закончили.  
  
 ![Снимок экрана пользовательского интерфейса Weather](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.png "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Ниже приведены некоторые сведения, которые следует иметь в виду.  
  
-   Создание обработчика кнопки  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 При нажатии кнопки мы отображаем рисунок часов и запускаем анимацию. Мы отключаем кнопку. Мы вызываем `FetchWeatherFromServer` метод в новом потоке, а затем мы возвращаем, позволяя <xref:System.Windows.Threading.Dispatcher> для обработки событий во время ожидания сбора прогноза погоды.  
  
-   Выборка погоды  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Чтобы не усложнять, мы фактически не используем никакого сетевого кода в данном примере. Вместо этого мы моделируем задержку доступа к сети путем помещения нашего нового потока спящий режим в течение четырех секунд. В течение этого времени исходный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков по-прежнему работает и реагирование на события. Чтобы показать это, мы оставили запущенную анимацию и свертывания и развертывания кнопок также продолжают работать.  
  
 После завершения задержки и случайного выбора прогноза погоды, пора отчет обратно в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. Это делается путем создания расписания вызов `UpdateUserInterface` в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков с помощью этого потока <xref:System.Windows.Threading.Dispatcher>. Передается строка, описывающая погоду запланированный вызов этого метода.  
  
-   Обновление[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Когда <xref:System.Windows.Threading.Dispatcher> в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока есть время, он выполняет запланированный вызов метода `UpdateUserInterface`. Этот метод останавливает часы анимации и выбирает изображение для описания погоды. Он отображает это изображение и восстанавливает кнопку «получить прогноз погоды».  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Несколько окон, несколько потоков  
 Некоторые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения требуют нескольких окон верхнего уровня. Вполне допустимо для одного потока и <xref:System.Windows.Threading.Dispatcher> сочетания для управления несколькими окнами, но иногда несколько потоков выполняют задание лучше. Это особенно важно, когда возможность, что одно из окон будет захватывать поток.  
  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]Обозреватель работает таким образом. Каждое новое окно проводника принадлежит исходному процессу, однако оно создано под управлением независимого потока.  
  
 С помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> элемента управления, можно отобразить веб-страниц. Можно легко создать простую [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] заменить. Мы начинаем с важной функции: возможности открыть новое окно обозревателя. Когда пользователь нажимает кнопку «новое окно» кнопку, запускается копия окна в отдельном потоке. Таким образом, долго выполняющиеся или блокирующие операции в одном из окон не блокируют все остальные окна.  
  
 На самом деле браузера имеет свою собственную сложную модель потоков. Мы выбрали его, поскольку он должен быть знаком большинству читателей.  
  
 В следующем примере показано код.  
  
 [!code-xml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 Следующие сегменты потоков этого кода наиболее интересны для нас в этом контексте:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Этот метод вызывается, когда «новое окно» кнопки. Он создает новый поток и запускает его в асинхронном режиме.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Этот метод является начальной точкой для нового потока. Мы создаем новое окно под управлением данного потока.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]автоматически создает новую <xref:System.Windows.Threading.Dispatcher> управление в новом потоке. Все что нужно сделать для обеспечения функциональности окна является запуск <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Технические подробности и важные моменты  
  
### <a name="writing-components-using-threading"></a>Написание компонентов, использующих поток  
 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] Руководство разработчика описывает образец того, как компонент может предоставлять асинхронное поведение для своих клиентов (см. [Обзор асинхронной модели на основе событий](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Например, предположим, что нужно упаковать `FetchWeatherFromServer` метод в неграфический компонент многократного использования. Следуя стандартному [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] шаблона, это будет выглядеть примерно следующим образом.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync`использовать один из методов, описанных выше, таких как создание фонового потока, для работы в асинхронном режиме, не блокируя вызывающий поток.  
  
 Одной из наиболее важных частей этот шаблон вызова *ИмяМетода* `Completed` метод в том же потоке, который вызвал *ИмяМетода* `Async` метода начинается с. Это можно сделать с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] довольно легко, сохраняя <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>— но затем неграфический компонент может использоваться только в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений, не в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] программ.  
  
 <xref:System.Windows.Threading.DispatcherSynchronizationContext> класс адреса этой задачи — представляйте его упрощенную версию <xref:System.Windows.Threading.Dispatcher> , работает с другими [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] также платформ.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Вложенная Накачка  
 Иногда не выполнима полная блокировка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока. Давайте рассмотрим <xref:System.Windows.MessageBox.Show%2A> метод <xref:System.Windows.MessageBox> класса.                          <xref:System.Windows.MessageBox.Show%2A> не возвращает, пока пользователь не нажмет кнопку «OK». Тем не менее, она создает окно, которое должно иметь цикл обработки сообщений, чтобы быть интерактивным. Во время ожидания, когда пользователь нажмет кнопку ОК, исходное окно приложения не отвечает на ввод данных пользователем. Он тем не менее, продолжает обрабатывать сообщения рисования. Исходное окно перерисовывается при перекрытии и выведении.  
  
 ![MessageBox с кнопкой «ОК»](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 Некоторые потоки должны отвечать за окно сообщения.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]можно создать новый поток специально для данного окна сообщения, но этот поток сможет отображать отключенные элементы в исходном окне (вспомните предыдущее обсуждение взаимного исключения). Вместо этого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует систему обработки вложенных сообщений. <xref:System.Windows.Threading.Dispatcher> класс содержит специальный метод <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, который сохраняет текущую точку выполнения приложения затем начинает новый цикл обработки сообщений. После завершения цикла обработки вложенных сообщений выполнение возобновляется после исходного <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> вызова.  
  
 В этом случае <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> поддерживает программный контекст при вызове <xref:System.Windows.MessageBox>.                         <xref:System.Windows.MessageBox.Show%2A>, и он начинает новый цикл обработки сообщений для перерисовки фона окна и обработки входных данных для окна сообщения. Когда пользователь нажимает кнопку OK и очищает всплывающее окно, вложенный цикл завершается и управление возобновляется после вызова <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Устаревшие маршрутизированные события  
 Маршрутизация системы обработки событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] уведомляет все деревья, когда вызываются события.  
  
 [!code-xml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 При нажатии левой кнопки мыши над эллипсом, `handler2` выполняется. После `handler2` окончания события передается вдоль <xref:System.Windows.Controls.Canvas> объекта, который использует `handler1` для его обработки. Это происходит только в том случае, если `handler2` не задает явно пометить объект событие как обработанное.  
  
 Возможно, `handler2` займет много времени на обработку этого события.                          `handler2`может использовать <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> для начала цикла вложенных сообщений, не возвращает часов. Если `handler2` не помечает событие как обработанное после цикла обработки сообщений завершения, событие передается вверх по дереву, даже если оно является очень старым.  
  
### <a name="reentrancy-and-locking"></a>Повторный вход и блокировка  
 Механизм блокировки [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] не ведут себя так же, как это можно представить; можно предположить, что поток завершит операцию полностью, запрашивая блокировку. В действительности поток продолжает получать и обрабатывать сообщения с высоким приоритетом. Это помогает избежать взаимоблокировок и максимально повышает скорость отклика интерфейсов, но может приводить к незначительным ошибкам.  Большая часть времени, не нужно ничего знать об этом, но в редких случаях (как правило, включающих [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] сообщения окна или компоненты COM STA) это знания могут потребоваться.  
  
 Большинство интерфейсов построено без учета безопасности потока не так, как разработчики работают в предположении, что [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] никогда не осуществляется более чем одним потоком. В данном случае, что один поток может изменить окружающей среды в неожиданные моменты времени неблагоприятные последствия, <xref:System.Windows.Threading.DispatcherObject> предполагается механизм взаимного исключения. Рассмотрим следующий псевдокод:  
  
 ![Схема повторного входа потоков](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 Большую часть времени все работает правильно, но иногда в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] где такой непредвиденный повторный вход может действительно вызвать проблемы. Поэтому в некий ключевой момент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызовов <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, который меняет инструкцию блокировки для этого потока, чтобы использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свободную от повторного входа блокировку вместо обычного [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] блокировки.  
  
 Так почему было [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] команда выбрать это поведение? Это было связано с объектами COM STA и завершением потока. Если объект является сборщиком мусора, его `Finalize` метод не выполняется в выделенном потоке завершения, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потока. Именно в этом лежит проблема, поскольку объект COM STA, созданный в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток может быть удален только в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоке. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Предоставляет эквивалент метода <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (в этом случае с помощью Win32 `SendMessage`). Но если [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] поток занят, поток завершения останавливается, и объект COM STA не удается завершить, что приводит к серьезной утечке памяти. Поэтому [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] создала сложный вызов для создания блокировки работы способ они делают.  
  
 Задача для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] — избежать непредвиденного повторного входа без внесения утечка памяти, поэтому мы не блокируем где.  
  
## <a name="see-also"></a>См. также  
 [Однопоточных приложений с образцом длительных вычислений](http://go.microsoft.com/fwlink/?LinkID=160038)