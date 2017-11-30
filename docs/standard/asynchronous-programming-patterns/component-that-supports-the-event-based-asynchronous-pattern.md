---
title: "Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях
При создании класса с некоторыми операциями, которые могут привести к значительным задержкам, рассмотрите возможность предоставления асинхронных функциональных возможностей посредством реализации [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 В этом пошаговом руководстве показано, как создать компонент, реализующий асинхронную модель на основе событий. Он реализуется с помощью вспомогательных классов из <xref:System.ComponentModel?displayProperty=nameWithType> пространства имен, которое гарантирует правильность работы компонента в любой модели приложения, включая [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], консольные приложения и приложения Windows Forms. Этот компонент также может быть разработан с <xref:System.Windows.Forms.PropertyGrid> управления и пользовательские конструкторы.  
  
 После завершения работы, имеется приложение, вычисляющее простые числа в асинхронном режиме. Ваше приложение получит главной пользовательского потока пользовательского интерфейса и поток для каждого вычисления простого числа. Несмотря на то, что тестирования, является ли большое число простым, занимает длительное время, основной поток пользовательского интерфейса не будет прерван, задержка и форма будет отвечать на запросы во время вычисления. Можно работать, как много вычислений, сколько пожелаете одновременно или выборочно отмену ожидающего выполнения вычисления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание компонента  
  
-   Определение открытых асинхронных событий и делегатов  
  
-   Определение закрытых делегатов  
  
-   Реализация открытых событий  
  
-   Реализация метода завершения  
  
-   Реализация рабочих методов  
  
-   Реализация методов запуска и отмены  
  
 Скопируйте код из этой темы, в разделе [как: реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Создание компонента  
 Первым шагом является создание компонента, который будет реализовать асинхронную модель на основе событий.  
  
#### <a name="to-create-the-component"></a>Создание компонента  
  
-   Создайте класс с именем `PrimeNumberCalculator` , наследуемый от <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Определение открытых асинхронных событий и делегатов  
 Компонент взаимодействует с клиентами с помощью событий. *Имя_метода* `Completed` событие предупреждения клиентов до завершения асинхронной задачи и *имя_метода* `ProgressChanged` событие информирует клиентов о ходе выполнения асинхронной задачи.  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Чтобы определить асинхронные события для клиентов пользовательского компонента:  
  
1.  Импорт <xref:System.Threading?displayProperty=nameWithType> и <xref:System.Collections.Specialized?displayProperty=nameWithType> пространства имен в верхней части файла.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Прежде чем `PrimeNumberCalculator` определение класса объявить делегаты для событий выполнения и завершения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  В `PrimeNumberCalculator` определения класса, объявите событие для отображения хода выполнения и завершения клиентам.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  После `PrimeNumberCalculator` определения класса, следует наследовать `CalculatePrimeCompletedEventArgs` класса для каждого вычисления для обработчика событий клиента для составления `CalculatePrimeCompleted`вычислению. В дополнение к `AsyncCompletedEventArgs` свойства, этот класс позволяет клиенту определить, какое число было проверено, будь то основной и первый делитель, к которым — если он не является простым.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно создать компонент.  
  
#### <a name="to-test-your-component"></a>Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Будут отображены два предупреждения компилятора:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Эти предупреждения будут очищены в следующем разделе.  
  
## <a name="defining-private-delegates"></a>Определение закрытых делегатов  
 Асинхронные аспекты `PrimeNumberCalculator` компонент реализованы внутренне со специальным делегатом, который называется <xref:System.Threading.SendOrPostCallback>. Объект <xref:System.Threading.SendOrPostCallback> представляет метод обратного вызова, который выполняется на <xref:System.Threading.ThreadPool> потока. Метод обратного вызова должен иметь сигнатуру, которая принимает один параметр типа <xref:System.Object>, а значит, вам потребуется для передачи состояния вместе с делегатами в классе-оболочке. Для получения дополнительной информации см. <xref:System.Threading.SendOrPostCallback>.  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Чтобы реализовать внутреннее асинхронное поведение компонента:  
  
1.  Объявите и создайте <xref:System.Threading.SendOrPostCallback> делегирует в `PrimeNumberCalculator` класса. Создание <xref:System.Threading.SendOrPostCallback> объектов в вспомогательный метод вызывается `InitializeDelegates`.  
  
     Вам потребуется два делегата: один для информирования о ходе выполнения для клиента и один для создания отчетов о завершении клиента.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Вызовите `InitializeDelegates` метод в конструкторе компонента.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Объявление делегата в `PrimeNumberCalculator` класс, который обрабатывает ту работу, которая должна быть выполнена асинхронно. Этот делегат оборачивает рабочий метод, который проверяет, является ли число простым. Этот делегат принимает <xref:System.ComponentModel.AsyncOperation> параметр, который будет использоваться для отслеживания времени существования асинхронной операции.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Создайте коллекцию для управления временем жизни ожидающих асинхронных операций. Клиент должен способ отслеживания операций, как выполняются и завершения, и этот отслеживания можно сделать, требуя от клиента для передачи уникального токена или идентификатор задачи, если клиент осуществляет вызов асинхронного метода. `PrimeNumberCalculator` Компонент должен хранить список каждый вызов путем сопоставления идентификатора задачи с соответствующим вызовом. Если клиент передает идентификатор задачи, который не является уникальным, `PrimeNumberCalculator` компонент должен создать исключение.  
  
     `PrimeNumberCalculator` Компонент сохраняет отслеживайте от идентификатор задачи, используя класс специальная коллекция с именем <xref:System.Collections.Specialized.HybridDictionary>. В определении класса создайте <xref:System.Collections.Specialized.HybridDictionary> вызывается `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Реализация открытых событий  
 Компоненты, реализующие асинхронную модель на основе событий взаимодействия с клиентами с помощью событий. Эти события вызываются в соответствующем потоке с помощью <xref:System.ComponentModel.AsyncOperation> класса.  
  
#### <a name="to-raise-events-to-your-components-clients"></a>Чтобы создать события в клиентах компонента:  
  
1.  Реализуйте открытые события, для создания отчетов для клиентов. Событие потребуется для отображения хода выполнения и одно для оповещения о завершении.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Реализация метода завершения  
 Делегат завершения — метод, который будет вызывать базовый, свободнопоточный асинхронного поведения при завершении асинхронной операции при успешном завершении, ошибке или отмены. Этот вызов происходит в произвольном потоке.  
  
 Этот метод является, где идентификатор задачи клиента удаляется из внутренней коллекции уникальных маркеров клиента. Этот метод также завершает время существования конкретную асинхронную операцию, вызвав <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> метод соответствующего <xref:System.ComponentModel.AsyncOperation>. Этот вызов событие завершения в потоке, который подходит для модели приложения. После <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> вызова этого экземпляра <xref:System.ComponentModel.AsyncOperation> больше не используется, и все последующие попытки использовать его будет создано исключение.  
  
 `CompletionMethod` Подписи должны содержаться все состояния, необходимые для описания результата асинхронной операции. Она содержит состояние для числа, которое было проверено в этой определенной асинхронной операции, является ли число простым и значение первый делитель Если не простых чисел. Она также содержит состояние, которое описывает любое исключение, которое было сформировано, и <xref:System.ComponentModel.AsyncOperation> соответствующий этой конкретной задачей.  
  
#### <a name="to-complete-an-asynchronous-operation"></a>Для завершения асинхронной операции:  
  
-   Реализуйте метод завершения. Он принимает шесть параметров, которые используются для заполнения `CalculatePrimeCompletedEventArgs` , возвращаемый клиенту с помощью клиента `CalculatePrimeCompletedEventHandler`. Удаляет маркер идентификатора задачи клиента из внутренней коллекции, после чего завершает время существования асинхронной операции с помощью вызова <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. <xref:System.ComponentModel.AsyncOperation> Маршалирует вызов в поток или контекст, который подходит для модели приложения.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно создать компонент.  
  
#### <a name="to-test-your-component"></a>Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Вы получите предупреждение компилятора:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Это предупреждение будет устранена в следующем разделе.  
  
## <a name="implementing-the-worker-methods"></a>Реализация рабочих методов  
 На данный момент реализован асинхронный код поддержки для `PrimeNumberCalculator` компонента. Теперь можно реализовать код, выполняющий работу. Будет реализовывать три метода: `CalculateWorker`, `BuildPrimeNumberList`, и `IsPrime`. Вместе `BuildPrimeNumberList` и `IsPrime` составляют хорошо известного алгоритма вызывается решета Эратосфена, который определяет, является ли число простым путем нахождения всех простых чисел до квадратного корня из проверяемого числа. Если делители не будут найдены, проверяемое число считается простым.  
  
 Этот компонент были написаны для максимальной эффективности, будет следует помнить простых чисел, обнаруженных при различных вызовах проверки различных чисел. Также будут проверены делители как 2, 3 и 5. Цель этого примера — продемонстрировать как длительные операции могут выполняться асинхронно, тем не менее, поэтому эти оптимизации остаются в качестве упражнения для вас.  
  
 `CalculateWorker` Метод заключается в делегат и вызывается асинхронно с помощью вызова `BeginInvoke`.  
  
> [!NOTE]
>  Отчет о ходе выполнения реализуется в `BuildPrimeNumberList` метод. На быстрых компьютерах `ProgressChanged` события могут возникать в течение короткого промежутка времени. Клиентский поток, на котором эти события вызываются, должен иметь возможность обработки этой ситуации. Код пользовательского интерфейса может быть перегружен сообщениями, с может справиться, приведет к зависанию. Пример пользовательского интерфейса, обрабатывает такую ситуацию, в разделе [как: реализация клиента асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Чтобы асинхронно выполнить вычисление простого числа:  
  
1.  Реализуйте `TaskCanceled` вспомогательный метод. Это проверяет коллекции времени существования задачи для определенного идентификатора задачи и возвращает `true` Если не найден идентификатор задачи.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Выполните метод `CalculateWorker`. Он принимает два параметра: число для тестирования и содержится <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Реализуйте расширение `BuildPrimeNumberList`. Он принимает два параметра: число, которое необходимо протестировать и <xref:System.ComponentModel.AsyncOperation>. Она использует <xref:System.ComponentModel.AsyncOperation> для отображения хода выполнения и добавочных результатов. Это гарантирует, что обработчики событий клиента вызываются в правильном потоке или контексте для модели приложения. Когда `BuildPrimeNumberList` находит a простых чисел, сообщает это как добавочный результат в обработчик событий клиента для `ProgressChanged` события. Для этого класса, производного от <xref:System.ComponentModel.ProgressChangedEventArgs>, который называется `CalculatePrimeProgressChangedEventArgs`, где содержится свойство с именем `LatestPrimeNumber`.  
  
     `BuildPrimeNumberList` Также периодически вызывает метод `TaskCanceled` метод и завершает работу, если метод возвращает `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Реализуйте расширение `IsPrime`. Он принимает три параметра: список известных простых чисел, проверяемое число и выходной параметр для первого найденного делителя. Получает список простых чисел, он определяет, является ли проверяемое число простым.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Производные `CalculatePrimeProgressChangedEventArgs` из <xref:System.ComponentModel.ProgressChangedEventArgs>. Этот класс необходим для предоставления добавочных результатов для обработчика событий клиента для `ProgressChanged` события. Он имеет одно добавленное свойство с именем `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно создать компонент.  
  
#### <a name="to-test-your-component"></a>Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
     Все, что осталось создать представляют собой методы для запуска и отмены асинхронных операций, `CalculatePrimeAsync` и `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Реализация методов запуска и отмены  
 Следует запускать рабочий метод в своем собственном потоке путем вызова `BeginInvoke` на делегат, который инкапсулирует его. Для управления временем жизни конкретную асинхронную операцию, вызовите <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> метод <xref:System.ComponentModel.AsyncOperationManager> вспомогательного класса. Возвращает <xref:System.ComponentModel.AsyncOperation>, которая маршалирует вызовы обработчиков событий клиента в подходящий поток или контекст.  
  
 Отмена либо операцию в очереди, вызвав <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> для соответствующей <xref:System.ComponentModel.AsyncOperation>. Завершен этой операции, а все последующие вызовы к его <xref:System.ComponentModel.AsyncOperation> вызовет исключение.  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>Для начала реализации и Отмена функциональные возможности:  
  
1.  Выполните метод `CalculatePrimeAsync`. Убедитесь, что маркер, предоставленный клиентом (идентификатор задачи) является уникальным в рамках все токены, представляющие в данный момент ожидающих задач. Если клиент передает неуникальный маркер `CalculatePrimeAsync` вызывает исключение. В противном случае маркер добавляется в коллекцию Идентификаторов задач.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Выполните метод `CancelAsync`. Если `taskId` параметр существует в коллекции маркеров, он удаляется. Это предотвращает отмененных задач, которые не начали выполнение. Если задача выполняется, `BuildPrimeNumberList` метод завершает работу, когда обнаруживает, что идентификатор задачи был удален из коллекции жизненных циклов.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе можно создать компонент.  
  
#### <a name="to-test-your-component"></a>Чтобы проверить компонент  
  
-   Скомпилируйте компонент.  
  
 `PrimeNumberCalculator` Компонент теперь будет полным и готова к использованию.  
  
 Пример клиента, который использует `PrimeNumberCalculator` компонента, в разделе [как: реализация клиента асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Дальнейшие действия  
 В этом примере можно сделать, написав `CalculatePrime`, является синхронным эквивалентом `CalculatePrimeAsync` метод. Это сделает `PrimeNumberCalculator` компонент полностью совместим с асинхронной моделью, основанной на событиях.  
  
 Этот пример можно улучшить посредством сохранения списка всех простых чисел, обнаруженных при различных вызовах проверки различных чисел. При таком подходе каждой задачи преимущества работы, выполненной предыдущих задач. Следует соблюдать осторожность защитить этот список с `lock` регионов, чтобы доступ к списку различными потоками был сериализован.  
  
 Этот пример также можно улучшить путем проверки на наличие делители: 2, 3 и 5.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [НЕ в СБОРКЕ: Многопоточность в Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Многопоточное программирование с использованием асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
