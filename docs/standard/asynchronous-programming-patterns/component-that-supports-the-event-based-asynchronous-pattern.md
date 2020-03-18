---
title: Практическое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
ms.openlocfilehash: 44a1019ac8169138aa95b03e2027d9539cbf8391
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71957369"
---
# <a name="how-to-implement-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Практическое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях
Если вы создаете класс и некоторые операции этого класса могут привести к значительным задержкам, подумайте о том, чтобы реализовать для этого класса асинхронные функции с помощью [асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 В этом руководстве мы покажем, как создать компонент, реализующий асинхронную модель на основе событий. Для такой реализации применяются вспомогательные классы из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента для приложений любой модели, включая ASP.NET, консольные приложения и приложения Windows Forms. Также этот компонент можно создать на основе элемента управления <xref:System.Windows.Forms.PropertyGrid> и пользовательских конструкторов.  
  
 Завершив работу с руководством, вы получите приложение, вычисляющее простые числа в асинхронном режиме. В приложении создается главный поток пользовательского интерфейса и отдельный поток для вычисления каждого простого числа. Несмотря на то что проверка крупных простых чисел может занимать много времени, основной поток пользовательского интерфейса не будет прерываться в результате этой задержки, а форма в ходе вычислений будет нормально реагировать на действия пользователя. Вы сможете запустить любое количество вычислений одновременно, а также избирательно отменять еще не оконченные вычисления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
- Создание компонента  
  
- определение открытых асинхронных событий и делегатов;  
  
- определение закрытых делегатов;  
  
- Реализация открытых событий  
  
- Реализация метода завершения  
  
- Реализация рабочих методов  
  
- реализация методов запуска и отмены.  
  
 Чтобы скопировать код из этого раздела единым блоком, см. [практическое руководство по реализация клиента асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Создание компонента  
 На первом шаге мы создадим компонент, который будет реализовать асинхронную модель на основе событий.  
  
### <a name="to-create-the-component"></a>Создание компонента  
  
- Создайте класс `PrimeNumberCalculator`, производный от <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>определение открытых асинхронных событий и делегатов;  
 Этот компонент взаимодействует с клиентами с помощью событий. Событие _имя_метода_**Completed** предупреждает клиенты о завершении асинхронной задачи, а событие _имя_метода_**ProgressChanged** информирует клиенты о ходе выполнения асинхронной задачи.  
  
### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Чтобы определить асинхронные события для клиентов своего компонента, выполните следующие действия.  
  
1. Импортируйте пространства имен <xref:System.Threading?displayProperty=nameWithType> и <xref:System.Collections.Specialized?displayProperty=nameWithType> в верхней части файла.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2. Перед определением класса `PrimeNumberCalculator` объявите делегаты для событий выполнения и завершения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3. В определении класса `PrimeNumberCalculator` объявите делегаты для событий информирования клиентов о ходе выполнения и завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4. После определения класса `PrimeNumberCalculator` наследуйте класс `CalculatePrimeCompletedEventArgs`, чтобы передавать результаты каждого вычисления в обработчик событий клиента для `CalculatePrimeCompleted`.event. Помимо реализации свойств `AsyncCompletedEventArgs`, этот класс позволяет клиенту определить, какое число было проверено, является ли оно простым, а если нет, то каков его первый делитель.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно выполнить сборку компонента.  
  
### <a name="to-test-your-component"></a>Проверка компонента  
  
- Скомпилируйте компонент.  
  
     Вы увидите два предупреждения компилятора.  
  
    ```console  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Мы рассмотрим эти предупреждения в следующем разделе.  
  
## <a name="defining-private-delegates"></a>определение закрытых делегатов;  
 Асинхронные аспекты компонента `PrimeNumberCalculator` реализуются внутри него в виде специального делегата <xref:System.Threading.SendOrPostCallback>. <xref:System.Threading.SendOrPostCallback> представляет метод обратного вызова, который выполняется для потока <xref:System.Threading.ThreadPool>. Метод обратного вызова должен содержать подпись, которая принимает один параметр типа <xref:System.Object>. Это значит, что вам следует передавать состояние вместе с делегатами в классе-оболочке. Дополнительные сведения см. в разделе <xref:System.Threading.SendOrPostCallback>.  
  
### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Чтобы реализовать внутреннее асинхронное поведение компонента, выполните следующие действия.  
  
1. Объявите и создайте делегаты <xref:System.Threading.SendOrPostCallback> в классе `PrimeNumberCalculator`. Создайте объекты <xref:System.Threading.SendOrPostCallback> во вспомогательном методе с именем `InitializeDelegates`.  
  
     Вам потребуются два делегата: один для информирования клиента о ходе выполнения, другой — для информирования клиента о завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2. Вызовите метод `InitializeDelegates` в конструкторе компонента.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3. Объявите в классе `PrimeNumberCalculator` делегат, который обрабатывает фактические операции для асинхронного выполнения. Этот делегат является оболочкой для рабочего метода, который проверяет, является ли число простым. Этот делегат принимает параметр <xref:System.ComponentModel.AsyncOperation>, который позволяет отслеживать время существования асинхронной операции.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4. Создайте коллекцию для управления временем существования асинхронных операций, ожидающих выполнения. Клиент должен отслеживать операции по мере их выполнения и завершения. Для реализации такого отслеживания у клиента запрашивается уникальный маркер (идентификатор) задачи, когда этот клиент вызывает асинхронный метод. Компонент `PrimeNumberCalculator` должен отслеживать все вызовы, сопоставляя идентификаторы задач с вызывающими объектами. Если клиент передает идентификатор задачи, не являющийся уникальным, компонент `PrimeNumberCalculator` должен создать исключение.  
  
     Компонент `PrimeNumberCalculator` отслеживает идентификаторы задач с помощью класса коллекции <xref:System.Collections.Specialized.HybridDictionary>. В определении класса создайте <xref:System.Collections.Specialized.HybridDictionary> с именем `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Реализация открытых событий  
 Компоненты, реализующие асинхронную модель на основе событий, взаимодействуют с клиентами через события. Эти события вызываются в соответствующем потоке с помощью класса <xref:System.ComponentModel.AsyncOperation>.  
  
### <a name="to-raise-events-to-your-components-clients"></a>Чтобы создать события в клиентах компонента, выполните следующие действия.  
  
1. Реализуйте открытые события, которые будут передавать информацию клиентам. Вам потребуется одно событие для информирования о ходе выполнения, и еще одно — для информирования о завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Реализация метода завершения  
 Делегат завершения — это метод, который будет вызываться из базовой среды со свободным потоком при успешном завершении, сбое или отмене асинхронной операции. Такой вызов происходит в произвольном потоке.  
  
 В этом методе идентификатор клиентской задачи удаляется из внутренней коллекции уникальных клиентских маркеров. Также этот метод завершает время существования конкретной асинхронной операции, вызывая метод <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> для соответствующего объекта <xref:System.ComponentModel.AsyncOperation>. Этот вызов создает событие завершения в потоке, который соответствует модели приложения. После вызова метода <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> этот экземпляр <xref:System.ComponentModel.AsyncOperation> нельзя использовать повторно. При любых последующих попытках будет создано исключение.  
  
 Подпись `CompletionMethod` должна содержать все состояния, необходимые для описания результата асинхронной операции. Она содержит информацию о числе, которое проверялось в конкретной асинхронной операции: является ли число простым и каково значение его первого делителя, если число не является простым. Также она содержит состояние, которое описывает все возникшие исключения, и объект <xref:System.ComponentModel.AsyncOperation>, соответствующий этой конкретной задаче.  
  
### <a name="to-complete-an-asynchronous-operation"></a>Для завершения асинхронной операции сделайте следующее.  
  
- Реализуйте метод завершения. Он принимает шесть параметров, на основании которых заполняет класс `CalculatePrimeCompletedEventArgs` и возвращает их клиенту через `CalculatePrimeCompletedEventHandler` для этого клиента. Он также удаляет маркер идентификатора задачи из внутренней коллекции, после чего завершает срок существования асинхронной операции с помощью вызова <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. <xref:System.ComponentModel.AsyncOperation> маршалирует вызов в поток или контекст, соответствующий модели приложения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно выполнить сборку компонента.  
  
### <a name="to-test-your-component"></a>Проверка компонента  
  
- Скомпилируйте компонент.  
  
     Вы увидите одно предупреждение компилятора:  
  
    ```console  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Мы рассмотрим это предупреждение в следующем разделе.  
  
## <a name="implementing-the-worker-methods"></a>Реализация рабочих методов  
 Итак, у вас готов весь асинхронный код поддержки для компонента `PrimeNumberCalculator`. Теперь можно переходить к созданию кода, который выполнит фактическую работу. Для этого вы реализуете три метода: `CalculateWorker`, `BuildPrimeNumberList` и `IsPrime`. Сочетание `BuildPrimeNumberList` и `IsPrime` реализует хорошо известный алгоритм "решето Эратосфена", который определяет, является ли число простым, проверяя все простые числа меньше квадратного корня из проверяемого числа. Если к этому моменту не будет обнаружено делителей, проверяемое число считается простым.  
  
 Если бы этот компонент создавался с прицелом на максимальную эффективность, он должен был бы запоминать все простые числа, обнаруженные при вычислениях для различных проверяемых чисел. Также он выполнял бы проверку на тривиальные делители, например 2, 3 и 5. Но в этом примере просто показано, как выполнять асинхронно длительные операции, поэтому всю оптимизацию мы оставляем вам для самостоятельного освоения.  
  
 Метод `CalculateWorker` заключается в делегат и вызывается асинхронно с помощью вызова к `BeginInvoke`.  
  
> [!NOTE]
> Отчет о ходе выполнения реализован в методе `BuildPrimeNumberList`. На быстрых компьютерах события `ProgressChanged` могут возникать быстро друг за другом. Клиентский поток, в котором возникают эти события, должен быть готов к такой ситуации. Если код пользовательского интерфейса будет перегружен сообщениями, это приведет к зависанию. Пример пользовательского интерфейса, который успешно справляется с этой ситуацией, см. в статье [Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Для асинхронного вычисления простых чисел выполните следующие действия.  
  
1. Реализуйте вспомогательный класс `TaskCanceled`. Он проверяет, существует ли определенный идентификатор в коллекции жизненных циклов задач, и возвращает `true`, если не обнаружит его.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2. Выполните метод `CalculateWorker`. Он принимает два параметра: число для тестирования и <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3. Реализуйте расширение `BuildPrimeNumberList`. Он принимает два параметра: число для тестирования и <xref:System.ComponentModel.AsyncOperation>. С помощью <xref:System.ComponentModel.AsyncOperation> он отображает ход выполнения и результаты по мере их получения. Благодаря этому клиентские обработчики событий вызываются в правильном потоке или контексте для модели приложения. Когда метод `BuildPrimeNumberList` находит простое число, он передает его для накопления результатов в клиентский обработчик событий через событие `ProgressChanged`. Для этого нам нужен производный от <xref:System.ComponentModel.ProgressChangedEventArgs> класс с именем `CalculatePrimeProgressChangedEventArgs`, который реализует одно дополнительное свойство с именем `LatestPrimeNumber`.  
  
     Также метод `BuildPrimeNumberList` периодически вызывает метод `TaskCanceled` и завершает работу, если тот возвращает значение `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4. Реализуйте расширение `IsPrime`. Он принимает три параметра: список известных простых чисел, проверяемое число и выходной параметр для первого найденного делителя. Полученный список простых чисел он использует, чтобы определить, является ли проверяемое число простым.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5. Получите `CalculatePrimeProgressChangedEventArgs` из <xref:System.ComponentModel.ProgressChangedEventArgs>. Этот класс используется для передачи результатов по мере их получения в клиентский обработчик событий для события `ProgressChanged`. Он содержит одно дополнительное свойство с именем `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно выполнить сборку компонента.  
  
### <a name="to-test-your-component"></a>Проверка компонента  
  
- Скомпилируйте компонент.  
  
     Теперь осталось создать только методы `CalculatePrimeAsync` и `CancelAsync`для запуска и отмены асинхронных операций.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Реализация методов запуска и отмены  
 Чтобы запустить рабочий метод в отдельном потоке, вызовите `BeginInvoke` для делегата, который является его оболочкой. Метод <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> вспомогательного класса <xref:System.ComponentModel.AsyncOperationManager> позволяет управлять временем существования конкретной асинхронной операции. Он возвращает параметр <xref:System.ComponentModel.AsyncOperation>, который маршалирует вызовы клиентских обработчиков событий в подходящий поток или контекст.  
  
 Чтобы отменить незавершенную операцию, вызовите <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> для соответствующего <xref:System.ComponentModel.AsyncOperation>. Это действие завершает операцию, а все последующие вызовы <xref:System.ComponentModel.AsyncOperation> приводят к исключениям.  
  
### <a name="to-implement-start-and-cancel-functionality"></a>Чтобы реализовать функциональные возможности запуска и отмены, выполните следующие действия.  
  
1. Выполните метод `CalculatePrimeAsync`. Обеспечьте уникальность маркера (идентификатора задачи), предоставляемого клиентом, среди всех маркеров для незавершенных в конкретный момент задач. Если клиент передает неуникальный маркер, `CalculatePrimeAsync` создает исключение. В противном случае этот маркер добавляется в коллекцию идентификаторов задач.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2. Выполните метод `CancelAsync`. Если параметр `taskId` существует в коллекции маркеров, он удаляется. Это действие блокирует запуск отмененных задач, выполнение которых еще не началось. Если задача уже выполняется, метод `BuildPrimeNumberList` обнаруживает, что идентификатор задачи удален из коллекции жизненных циклов, и завершает работу.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно выполнить сборку компонента.  
  
### <a name="to-test-your-component"></a>Проверка компонента  
  
- Скомпилируйте компонент.  
  
 Итак, компонент `PrimeNumberCalculator` полностью готов к использованию.  
  
 Пример клиента, который использует компонент `PrimeNumberCalculator`, см. в статье [Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Next Steps  
 Попробуйте изучить следующий пример, в котором вы создадите `CalculatePrime`, синхронный эквивалент метода `CalculatePrimeAsync`. После этого компонент `PrimeNumberCalculator` будет полностью совместим с асинхронной моделью на основе событий.  
  
 Вы можете улучшить этот пример, сохранив список всех простых чисел, обнаруженных при вызовах для проверки разных чисел. Это позволит каждой задаче использовать результаты работы всех предыдущих задач. Обязательно защитите этот список с помощью регионов `lock`, чтобы сериализовать доступ к списку из разных потоков.  
  
 Также вы можете улучшить этот пример, выполнив проверку на тривиальные делители, например 2, 3 и 5.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
