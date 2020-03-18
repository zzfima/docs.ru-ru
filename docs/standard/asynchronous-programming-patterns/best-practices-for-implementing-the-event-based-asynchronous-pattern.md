---
title: Рекомендации по реализации асинхронной модели, основанной на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 4acd2094-4f46-4eff-9190-92d0d9ff47db
ms.openlocfilehash: 439b862612d7997c9277ffb2cf4f15b14bd0b106
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156053"
---
# <a name="best-practices-for-implementing-the-event-based-asynchronous-pattern"></a>Рекомендации по реализации асинхронной модели, основанной на событиях
Асинхронная модель на основе событий является эффективным средством для обеспечения асинхронной работы в классах на базе привычной семантики делегатов и событий. Чтобы внедрить асинхронную модель на основе событий, необходимо выполнить определенные требования относительно поведения. В следующих разделах описываются требования и рекомендации, которые следует учитывать при реализации класса, поддерживающего асинхронную модель на основе событий.  
  
 Общие сведения см. в разделе [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="required-behavioral-guarantees"></a>Обеспечение требуемого поведения  
 Если вы внедряете асинхронную модель на основе событий, необходимо выполнить несколько условий, чтобы класс работал правильно, а клиенты вашего класса могли положиться на его работу.  
  
### <a name="completion"></a>Завершение  
 После успешного завершения, отмены или в случае ошибки всегда вызывайте обработчик событий <em>имя_метода</em>**Completed**. Приложения никогда не должны попадать в ситуацию, в которой они остаются неактивными, а завершение не выполняется. Единственным исключением из этого правила является такая асинхронная операция, которая намеренно разработана таким образом, чтобы никогда не завершаться.  
  
### <a name="completed-event-and-eventargs"></a>Событие Completed и EventArgs  
 Для каждого отдельного метода <em>имя_метода</em>**Async** придерживайтесь следующих требований:  
  
- Определите событие <em>имя_метода</em>**Completed** в том же классе, что и этот метод.  
  
- Определите класс <xref:System.EventArgs> и сопроводительный делегат для события <em>имя_метода</em>**Completed**, наследованного от класса <xref:System.ComponentModel.AsyncCompletedEventArgs>. Имя класса по умолчанию должно быть представлено в таком формате: <em>имя_метода</em>**CompletedEventArgs**.  
  
- Убедитесь, что класс <xref:System.EventArgs> связан с возвращаемыми значениями метода <em>имя_метода</em>. При использовании класса <xref:System.EventArgs> вы никогда не должны требовать от разработчиков выполнить приведение результата.  
  
     В следующем примере кода показана хорошая и плохая реализация этого требования к разработке.  
  
```csharp  
// Good design  
private void Form1_MethodNameCompleted(object sender, xxxCompletedEventArgs e)
{
    DemoType result = e.Result;  
}  
  
// Bad design  
private void Form1_MethodNameCompleted(object sender, MethodNameCompletedEventArgs e)
{
    DemoType result = (DemoType)(e.Result);  
}  
```  
  
- Не определяйте класс <xref:System.EventArgs> для возвратных методов, которые возвращают `void`. Вместо этого следует использовать экземпляр класса <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
- Следите за тем, чтобы всегда создавалось событие <em>имя_метода</em>**Completed**. Это событие должно возникать при успешном завершении, ошибке или отмене. Приложения никогда не должны попадать в ситуацию, в которой они остаются неактивными, а завершение не выполняется.  
  
- Обязательно перехватывайте любые исключения, возникающие в асинхронной операции, и назначайте их свойству <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>.  
  
- Если при выполнении задачи возникла ошибка, результаты должны быть недоступны. Когда свойство <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> имеет значение, отличное от `null`, убедитесь, что обращение к любому свойству в структуре <xref:System.EventArgs> вызывает исключение. Для выполнения этой проверки используйте метод <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A>.  
  
- Смоделируйте истечение времени ожидания в качестве ошибки. Когда время ожидания истечет, вызовите событие <em>имя_метода</em>**Completed** и назначьте свойству <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> значение <xref:System.TimeoutException>.  
  
- Если класс поддерживает несколько одновременных вызовов, убедитесь, что событие <em>имя_метода</em>**Completed** содержит соответствующий объект `userSuppliedState`.  
  
- Убедитесь, что событие <em>имя_метода</em>**Completed** создается в правильном потоке и в правильном периоде жизненного цикла приложения. Дополнительные сведения см. в разделе "Потоки и контексты".  
  
### <a name="simultaneously-executing-operations"></a>Одновременное выполнение операций  
  
- Если класс поддерживает несколько одновременных вызовов, предоставьте разработчику возможность отслеживать каждый вызов по отдельности, определив перегрузку <em>имя_метода</em>**Async**, которая принимает объект состояния или идентификатор задачи в параметре с именем `userSuppliedState`. Этот параметр должен всегда стоять последним в сигнатуре метода <em>имя_метода</em>**Async**.  
  
- Если класс определяет перегрузку <em>имя_метода</em>**Async**, которая принимает параметр с объектом состояния или идентификатором задачи, обязательно отслеживайте время существования операции с этим идентификатором задачи и возвращайте его в завершающий обработчик. Можно использовать доступные вспомогательные классы. Дополнительные сведения об управлении параллелизмом см. в разделе [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
- Если класс определяет метод <em>имя_метода</em>**Async** без параметра состояния и не поддерживает несколько одновременных вызовов, обязательно создавайте исключение <xref:System.InvalidOperationException> при любой попытке вызова <em>имя_метода</em>**Async** до завершения предыдущего вызова <em>имя_метода</em>**Async**.  
  
- Обычно не нужно создавать исключение, если метод <em>имя_метода</em>**Async** вызывается несколько раз без параметра `userSuppliedState`, то есть создает несколько операций, ожидающих выполнения. Вы можете создать исключение, когда ваш класс явным образом не может разрешить возникшую ситуацию, но вы предполагаете, что разработчики могут обработать несколько этих неразличимых обратных вызовов.  
  
### <a name="accessing-results"></a>Доступ к результатам  
  
- Если во время выполнения асинхронной операции возникла ошибка, результаты должны быть недоступны. Убедитесь, что при обращении к любому свойству в <xref:System.ComponentModel.AsyncCompletedEventArgs>, когда <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> имеет значение, отличное от `null`, возникает исключение, на которое ссылается <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>. Для этой цели класс <xref:System.ComponentModel.AsyncCompletedEventArgs> предоставляет метод <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A>.  
  
- Убедитесь, что любая попытка доступа к результату вызывает исключение <xref:System.InvalidOperationException>, указывающее на отмену операции. Для выполнения этой проверки используйте метод <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType>.  
  
### <a name="progress-reporting"></a>Отчет о ходе выполнения  
  
- По возможности реализуйте поддержку отчетов о ходе выполнения. Это позволяет разработчикам улучшить взаимодействие приложения с пользователем при использовании вашего класса.  
  
- Если вы реализуете событие **ProgressChanged** или <em>имя_метода</em>**ProgressChanged**, убедитесь, что такие события не создаются для конкретной асинхронной операции после того, как было создано событие <em>имя_метода</em>**Completed**.  
  
- Если выполняется заполнение стандартного <xref:System.ComponentModel.ProgressChangedEventArgs>, убедитесь, что <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> всегда можно интерпретировать как процент. Этот процент может быть неточным, однако он всегда должен представлять именно процент. Если ваша метрика отчетов о ходе выполнения должна отличаться от процента, создайте производный класс от класса <xref:System.ComponentModel.ProgressChangedEventArgs> и оставьте для <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> значение 0. Старайтесь не использовать метрику отчетов, отличную от процента.  
  
- Убедитесь, что событие `ProgressChanged` возникает в соответствующем потоке и в соответствующее время жизненного цикла приложения. Дополнительные сведения см. в разделе "Потоки и контексты".  
  
### <a name="isbusy-implementation"></a>Реализация IsBusy  
  
- Не предоставляйте свойство `IsBusy`, если ваш класс поддерживает несколько одновременных вызовов. Например, прокси-серверы XML-веб-службы не предоставляют свойство `IsBusy`, так как поддерживают несколько одновременных вызовов асинхронных методов.  
  
- Свойство `IsBusy` должно возвращать `true` после того, как был вызван метод <em>имя_метода</em>**Async**, но еще не было создано событие <em>имя_метода</em>**Completed**. В противном случае оно должно возвратить `false`. Компоненты <xref:System.ComponentModel.BackgroundWorker> и <xref:System.Net.WebClient> являются примерами классов, которые предоставляют свойство `IsBusy`.  
  
### <a name="cancellation"></a>Отмена  
  
- По возможности реализуйте поддержку отмены. Это позволяет разработчикам улучшить взаимодействие приложения с пользователем при использовании вашего класса.  
  
- В случае отмены установите флаг <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> в объекте <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
- Убедитесь, что любая попытка доступа к результату вызывает исключение <xref:System.InvalidOperationException>, указывающее на отмену операции. Для выполнения этой проверки используйте метод <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType>.  
  
- Убедитесь, что вызовы метода отмены всегда возвращаются и никогда не вызывают исключение. В общем случае клиент не получает уведомление о том, можно ли отменить операцию в любой заданный момент времени и была ли успешной выданная ранее команда отмены. Однако приложение всегда получает уведомление об успешной отмене, так как оно принимает участие в установке состояния завершения.  
  
- При отмене операции создайте событие <em>имя_метода</em>**Completed**.  
  
### <a name="errors-and-exceptions"></a>Ошибки и исключения  
  
- Перехватывайте любые исключения, возникающие в асинхронной операции, и назначайте их в качестве значения свойства <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>.  
  
### <a name="threading-and-contexts"></a>Потоки и контексты  
 Для правильной работы вашего класса крайне важно, чтобы обработчики событий клиента вызывались в правильном потоке или контексте для заданной модели приложения, включая приложения Windows Forms и ASP.NET. Доступно два важных вспомогательных класса, позволяющих проверить, правильно ли себя ведет ваш асинхронный класс при любой модели приложения: <xref:System.ComponentModel.AsyncOperation> и <xref:System.ComponentModel.AsyncOperationManager>.  
  
 <xref:System.ComponentModel.AsyncOperationManager> предоставляет один метод <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>, который возвращает <xref:System.ComponentModel.AsyncOperation>. Метод <em>имя_метода</em>**Async** вызывает <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>, а класс использует возвращенное значение <xref:System.ComponentModel.AsyncOperation>, чтобы отследить время существования асинхронной задачи.  
  
 Чтобы сообщить клиенту о ходе выполнения, добавочных результатах и завершении, выполните вызов методов <xref:System.ComponentModel.AsyncOperation.Post%2A> и <xref:System.ComponentModel.AsyncOperation.OperationCompleted%2A> для <xref:System.ComponentModel.AsyncOperation>. <xref:System.ComponentModel.AsyncOperation> отвечает за маршалинг вызовов обработчиков событий клиента в подходящий поток или контекст.  
  
> [!NOTE]
> Вы можете не соблюдать эти правила, если хотите явно нарушить политику модели приложения, но при этом воспользоваться другими преимуществами асинхронной модели на основе событий. Например, вам может понадобиться, чтобы класс, работающий в Windows Forms, был со свободным потоком. Вы можете создать класс со свободным потоком, если разработчики осознают накладываемые этим ограничения. Консольные приложения не синхронизируют выполнение вызовов <xref:System.ComponentModel.AsyncOperation.Post%2A>. Это может вызвать беспорядочное возникновение событий `ProgressChanged`. Если вы хотите получить сериализованное выполнение вызовов <xref:System.ComponentModel.AsyncOperation.Post%2A>, реализуйте и установите класс <xref:System.Threading.SynchronizationContext?displayProperty=nameWithType>.  
  
 Дополнительные сведения об использовании <xref:System.ComponentModel.AsyncOperation> и <xref:System.ComponentModel.AsyncOperationManager> для включения асинхронных операций см. в разделе [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="guidelines"></a>Рекомендации  
  
- В идеале каждый вызов метода должен быть независимым от остальных. Вам следует избегать установления взаимозависимости вызовов посредством общих ресурсов. Если требуется общий доступ вызовов к ресурсам, в реализации необходимо обеспечить подходящий механизм синхронизации.  
  
- Варианты, в которых клиенту требуется реализовать синхронизацию, использовать не рекомендуется. Например, у вас может быть асинхронный метод, принимающий в качестве параметра глобальный статический объект; несколько одновременных вызовов такого метода могут привести к повреждению данных или взаимоблокировкам.  
  
- Если вы реализуете метод с перегрузкой с несколькими вызовами (`userState` в сигнатуре), вашему классу потребуется управлять коллекцией пользовательских состояний (или идентификаторов задачи) и соответствующих им ожидающих операций. Эту коллекцию следует защитить областями `lock`, так как различные вызовы добавляют и удаляют объекты `userState` в ней.  
  
- Рекомендуется повторно использовать классы `CompletedEventArgs`, когда это возможно и уместно. В этом случае именование не соответствует имени метода, так как заданный делегат и тип <xref:System.EventArgs> не привязаны к одному методу. Однако ни в коем случае нельзя принуждать разработчиков выполнить приведение значения, полученного из свойства в <xref:System.EventArgs>.  
  
- Если вы создаете класс, являющийся производным от <xref:System.ComponentModel.Component>, не реализуйте и не устанавливайте свой собственный класс <xref:System.Threading.SynchronizationContext>. Используемый <xref:System.Threading.SynchronizationContext> определяют модели приложения, а не компоненты.  
  
- При использовании любого вида многопоточности вы создаете условия для возникновения очень серьезных и сложных ошибок. Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Рекомендации по работе с потоками](../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- [Реализация асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)
- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Определение, когда следует реализовать асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
