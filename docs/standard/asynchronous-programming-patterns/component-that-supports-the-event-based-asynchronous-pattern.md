---
title: "Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern
При создании класса с некоторыми операциями, которые могут привести к значительным задержкам, рассмотрите предоставление этому классу асинхронных функциональных возможностей посредством реализации [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 В этом пошаговом руководстве показано, как создать компонент, который реализует асинхронную модель, основанную на событиях.  Он реализуется с помощью вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=fullName>, которое гарантирует правильность работы компонента в любой модели приложения, включая [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], консольные приложения и приложения Windows Forms.  Этот компонент также может быть разработан с помощью элемента управления <xref:System.Windows.Forms.PropertyGrid> и собственных разработчиков.  
  
 По завершении работы будет создано приложение, вычисляющее простые числа в асинхронном режиме.  Пользовательское приложение должно иметь основной поток пользовательского интерфейса и поток для каждого вычисления простого числа.  Несмотря на то, что проверка большого числа на то, является ли оно простым, занимает большое количество времени, основной поток пользовательского интерфейса не будет прерван из\-за этой задержки, а форма будет интерактивна во время вычисления.  Можно будет запустить столько вычислений, сколько нужно, при этом отменяя вычисления, находящиеся в очереди или одновременно, или выборочно.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание компонента  
  
-   Определение открытых асинхронных событий и делегатов  
  
-   Определение закрытых делегатов  
  
-   Реализация открытых событий  
  
-   Реализация метода завершения  
  
-   Реализация рабочих методов  
  
-   Реализация методов запуска и отмены  
  
 Чтобы скопировать весь текст кода из этой темы, см. ссылку [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## Создание компонента  
 Первый шаг заключается в создании компонента, который будет реализовывать асинхронную модель, основанную на событиях.  
  
#### Чтобы создать компонент  
  
-   Создайте класс с названием `PrimeNumberCalculator`, который наследует от <xref:System.ComponentModel.Component>.  
  
## Определение открытых асинхронных событий и делегатов  
 Компонент взаимодействует с клиентами с помощью событий.  Событие *MethodName*`Completed` предупреждает клиентов о завершении асинхронной задачи, а событие *MethodName*`ProgressChanged` информирует клиентов об этапе выполнения асинхронной задачи.  
  
#### Чтобы определить асинхронные события для клиентов пользовательского компонента:  
  
1.  Импортируйте пространства имен <xref:System.Threading?displayProperty=fullName> и <xref:System.Collections.Specialized?displayProperty=fullName> в верхнюю часть файла.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Перед определением класса  `PrimeNumberCalculator` можно объявить делегатов для событий выполнения и завершения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  В определении класса  `PrimeNumberCalculator` объявите событие для предоставления клиентам отчетности о выполнении и завершении задачи.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  После определения класса  `PrimeNumberCalculator`  следует сделать класс  `CalculatePrimeCompletedEventArgs`  производным для составления отчетности по каждому вычислению для дескриптора события клиента, касающегося события `CalculatePrimeCompleted`.  Помимо свойств `AsyncCompletedEventArgs` этот класс позволяет клиенту определять, какое число было проверено, было ли оно простым и что является первым делителем, если это число простым не было.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## Контрольная точка  
 На этом этапе можно построить компонент.  
  
#### Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Будут отображены два предупреждения компилятора:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Эти предупреждения будут очищены в следующем разделе:  
  
## Определение закрытых делегатов  
 Асинхронные аспекты компонента  `PrimeNumberCalculator` реализованы внутренне со специальным делегатом, который известен как <xref:System.Threading.SendOrPostCallback>.  Объект <xref:System.Threading.SendOrPostCallback> представляет метод обратного вызова, который выполняется в потоке <xref:System.Threading.ThreadPool>.  Этот метод обратного вызова должен иметь сигнатуру, которая принимает один параметр типа <xref:System.Object>, что означает необходимость передачи состояния вместе с делегатами в классе\-оболочке.  Для получения дополнительной информации см. <xref:System.Threading.SendOrPostCallback>.  
  
#### Чтобы реализовать внутреннее асинхронное поведение компонента:  
  
1.  Объявите и создайте делегаты <xref:System.Threading.SendOrPostCallback> в классе  `PrimeNumberCalculator` .  Создайте объекты <xref:System.Threading.SendOrPostCallback> в служебном методе  `InitializeDelegates`.  
  
     Будут необходимы два делегата: один для отображения клиенту хода выполнения, а другой — для оповещения клиента о завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Вызовите метод `InitializeDelegates` в конструкторе компонента.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Объявите делегат в классе `PrimeNumberCalculator`, который обрабатывает ту работу, которая должна быть выполнена асинхронно.  Этот делегат оборачивает рабочий метод, который проверяет, является ли число простым.  Делегат принимает параметр <xref:System.ComponentModel.AsyncOperation>, который будет использоваться для отслеживания жизненного цикла асинхронной операции.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Создайте коллекцию для управления жизненными циклами асинхронных операций в очереди.  Клиент нуждается в способе отслеживания приложений по мере их выполнения и завершения. Это отслеживание реализуется путем обязательной передачи клиентом уникального маркера \(или идентификатора задачи\) при вызове клиентом асинхронного метода.  Компонент `PrimeNumberCalculator` должен отслеживать каждый вызов путем сопоставления идентификатора задачи с соответствующим вызовом.  Если клиент передает идентификатор задачи, который не является уникальным, компонент `PrimeNumberCalculator` должен создать исключение.  
  
     Компонент `PrimeNumberCalculator` отслеживает идентификаторы задач с помощью специального класса коллекции, который называется <xref:System.Collections.Specialized.HybridDictionary>.  В определении класса создайте объект <xref:System.Collections.Specialized.HybridDictionary> с названием `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## Реализация открытых событий  
 Компоненты, который реализуют асинхронную модель, основанную на событиях, связываются с клиентами с помощью событий.  Эти события вызываются в соответствующем потоке посредством класса <xref:System.ComponentModel.AsyncOperation>.  
  
#### Чтобы создать события в клиентах компонента:  
  
1.  Реализуйте открытые события, о которых следует уведомить клиентов.  Понадобится одно событие для отображения хода выполнения и одно для оповещения о завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## Реализация метода завершения  
 Делегат завершения — это метод, который будет вызван при базовом асинхронном поведении со свободными потоками, при успешном завершении асинхронной операции, при ее завершении с ошибкой или при ее отмене.  Этот вызов происходит в произвольном потоке.  
  
 При работе этого метода идентификатор задачи клиента удаляется из внутренней коллекции уникальных маркеров клиента.  Этот метод также завершает жизненный цикл определенной асинхронной операции посредством вызова метода <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> для соответствующей операции <xref:System.ComponentModel.AsyncOperation>.  При этом вызове создается событие завершения в том потоке, который подходит для модели приложения.  После вызова метода <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> этот экземпляр <xref:System.ComponentModel.AsyncOperation> уже не может быть использован, поэтому все последующие попытки его использования приведут к созданию исключения.  
  
 В сигнатуре `CompletionMethod` должны содержаться все состояния, необходимые для описания результата асинхронной операции.  Здесь содержится состояние для числа, которое было проверено в этой определенной асинхронной операции, является ли это число простым и какой его первый делитель, если число простым не является.  Также здесь содержится состояние, которое описывает любое возникшее исключение и операцию <xref:System.ComponentModel.AsyncOperation>, связанную именно с этой задачей.  
  
#### Чтобы завершить асинхронную операцию:  
  
-   Реализуйте метод завершения.  Он принимает шесть параметров, которые используются для заполнения объекта  `CalculatePrimeCompletedEventArgs`, который возвращается клиенту посредством клиентского дескриптора  `CalculatePrimeCompletedEventHandler`.  Он удаляет маркер идентификатора задачи клиента из внутренней коллекции, после чего завершает жизненный цикл асинхронной операции посредством вызова метода <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>.  Операция <xref:System.ComponentModel.AsyncOperation> маршалирует вызов в поток или контекст, который является подходящим для модели приложения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## Контрольная точка  
 На этом этапе можно построить компонент.  
  
#### Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Будет получено одно предупреждение компилятора:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Причины, приведшие к этому предупреждению, будут устранены в следующем разделе.  
  
## Реализация рабочих методов  
 На данный момент был реализован асинхронный код поддержки для компонента `PrimeNumberCalculator`.  Теперь можно реализовать код, с помощью которого работа фактически выполняется.  Необходимо будет реализовать три метода: `CalculateWorker`, `BuildPrimeNumberList` и `IsPrime`.  `BuildPrimeNumberList` и `IsPrime` вместе образуют хорошо известный алгоритм, который называется "решетом Эратосфена", с помощью которого можно определить, является ли число простым путем нахождения всех простых чисел до квадратного корня из проверяемого числа.  Если делители не будут найдены, проверяемое число считается простым.  
  
 Чтобы сделать этот компонент максимально эффективным, в нем должны запоминаться все основные числа, обнаруженные во время различных вызовов для проверки различных чисел.  Также будут проверены простые делители, такие как 2, 3 и 5.  Предназначение этого примера заключается в необходимости демонстрации асинхронного выполнения операций, которые занимают много времени, поэтому поупражняйтесь в оптимизации самостоятельно.  
  
 Метод `CalculateWorker` заключается в оболочку делегата и вызывается асинхронно при вызове `BeginInvoke`.  
  
> [!NOTE]
>  Отчет о ходе выполнения реализуется в методе `BuildPrimeNumberList`.  На быстрых компьютерах события `ProgressChanged` могут создаваться в быстрой последовательности.  Клиентский поток, в котором создаются эти события, должен иметь возможность обработать подобное поведение.  Код пользовательского интерфейса может быть перегружен сообщениями, с которыми не сможет справиться, что приведет к "зависанию".  Пример пользовательского интерфейса, способного обработать подобную ситуацию, см. в разделе [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### Чтобы асинхронно выполнить вычисление простого числа:  
  
1.  Реализуйте рабочий метод `TaskCanceled`.  Это приведет к проверке коллекции жизненных циклов задач для определенного идентификатора задачи и возвратит значение `true`, если идентификатор задач найден не будет.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Реализуйте метод `CalculateWorker`.  Он принимает два параметра: проверяемое число и <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Реализуйте интерфейс `BuildPrimeNumberList`.  Он принимает два параметра: проверяемое число и <xref:System.ComponentModel.AsyncOperation>.  <xref:System.ComponentModel.AsyncOperation> здесь используется для отображения хода выполнения и результатов.  Это гарантирует вызов клиентских обработчиков события в допустимом для модели приложения потоке или контексте.  При нахождении `BuildPrimeNumberList` простого числа это преподносится клиентскому обработчику события `ProgressChanged` как добавочный результат.  Для этого необходим класс, производный из <xref:System.ComponentModel.ProgressChangedEventArgs>, который называется `CalculatePrimeProgressChangedEventArgs`, где содержится свойство `LatestPrimeNumber`.  
  
     Метод `BuildPrimeNumberList` также периодически вызывает метод `TaskCanceled` и выполняет выход, если последний возвращает значение `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Реализуйте интерфейс `IsPrime`.  Он принимает три параметра: список известных простых чисел, проверяемое число и выходной параметр для первого найденного делителя.  Используя предоставленный список простых чисел, он определяет, является ли проверяемое число простым.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Сделайте `CalculatePrimeProgressChangedEventArgs` производным из <xref:System.ComponentModel.ProgressChangedEventArgs>.  Этот класс необходим для предоставления добавочных результатов клиентскому обработчику события `ProgressChanged`.  Здесь имеется одно добавленное свойство с названием `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## Контрольная точка  
 На этом этапе можно построить компонент.  
  
#### Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Все, что осталось создать — это методы запуска и отмены асинхронных операций, `CalculatePrimeAsync` и `CancelAsync`.  
  
## Реализация методов запуска и отмены  
 Рабочий метод следует запускать в собственном потоке путем вызова `BeginInvoke` в делегате, который является для него оболочкой.  Чтобы управлять жизненным циклом определенной асинхронной операции, следует вызвать метод <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> для вспомогательного класса <xref:System.ComponentModel.AsyncOperationManager>.  Это возвращает <xref:System.ComponentModel.AsyncOperation>, которая маршалирует вызовы клиентских обработчиков события в допустимый поток или контекст.  
  
 Отменить какую\-либо операцию в очереди можно путем вызова метода <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> для соответствующей <xref:System.ComponentModel.AsyncOperation>.  Это приведет к завершению операции, а любые последующие вызовы операции <xref:System.ComponentModel.AsyncOperation> приведут к созданию исключения.  
  
#### Чтобы реализовать функциональность запуска и отмены:  
  
1.  Реализуйте метод `CalculatePrimeAsync`.  Убедитесь, что маркер, предоставленный клиентом \(идентификатор задачи\) является уникальным по отношению ко всем остальным маркерам, представляющим задачи, находящиеся в очереди.  Если клиент передает неуникальный маркер, `CalculatePrimeAsync` создает исключение.  В противном случае, маркер добавляется в коллекцию идентификаторов задач.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Реализуйте метод `CancelAsync`.  Если параметр `taskId` существует в коллекции маркеров, он удаляется.  Это препятствует запуску отмененных задач, которые еще не были запущены.  Если задача выполняется, метод `BuildPrimeNumberList` завершает работу при определении, что идентификатор задачи был удален из коллекции жизненных циклов.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## Контрольная точка  
 На этом этапе можно построить компонент.  
  
#### Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
 Теперь компонент  `PrimeNumberCalculator` завершен и готов к использованию.  
  
 Пример клиента, который использует компонент `PrimeNumberCalculator` см. в разделе [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## Следующие действия  
 Такое пример можно сделать, создав метод `CalculatePrime`, который является синхронным эквивалентом метода `CalculatePrimeAsync`.  Это приведет к тому, что компонент `PrimeNumberCalculator` будет полностью совместим с асинхронной моделью, основанной на событиях.  
  
 Этот пример можно улучшить посредством сохранения списка всех простых чисел, обнаруженных при различных вызовах проверки различных чисел.  Таким образом, каждая задача выигрывает вследствие использования работы, выполненной предыдущими задачами.  Следует с осторожностью защитить этот список с помощь областей `lock`, чтобы доступ к списку различными потоками был сериализован.  
  
 Этот пример также можно улучшить путем проверки на простые делители: 2, 3 и 5.  
  
## См. также  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ru-ru/c731a50c-09c1-4468-9646-54c86b75d269)   
 [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)