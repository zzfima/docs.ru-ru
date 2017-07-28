---
title: "Новые возможности WPF версии 4.5 | Microsoft Docs"
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
  - "Windows Presentation Foundation, новые возможности"
  - "WPF, новые возможности"
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
caps.latest.revision: 55
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 55
---
# Новые возможности WPF версии 4.5
<a name="introduction"></a> В этой теме содержатся сведения о новых и дополнительных возможностях в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] версии 4.5.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Элемент управления ленты](#ribbon_control)  
  
-   [Повышенная производительность при отображении больших наборов сгруппированных данных](#grouped_virtualization)  
  
-   [Новые функции для VirtualizingPanel](#VirtualizingPanel)  
  
-   [Привязка к статическим свойствам](#static_properties)  
  
-   [Доступ к коллекции в потоках, отличный от пользовательского интерфейса](#xthread_access)  
  
-   [Синхронно и асинхронно проверка данных](#INotifyDataErrorInfo)  
  
-   [Автоматическое обновление источника привязки данных](#delay)  
  
-   [Привязка к типам, которые реализуют ICustomTypeProvider](#ICustomTypeProvider)  
  
-   [Получение сведений о привязке из выражения привязки данных](#binding_state)  
  
-   [Проверка допустимого объекта DataContext](#DisconnectedSource)  
  
-   [Перемещающ данные в виде значения данных измените \(формирование Live\)](#live_shaping)  
  
-   [Улучшенная поддержка устанавливать слабую ссылку на событие](#weak_event_pattern)  
  
-   [Новые методы класса диспетчера](#async)  
  
-   [Расширения разметки для событий](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## Элемент управления ленты  
 WPF 4,5 поставки с <xref:System.Windows.Controls.Ribbon.Ribbon> контролирует, что узлы панели инструментов быстрого доступа в меню приложения и вкладки.  Дополнительные сведения см. в разделе [Обзор ленты](../Topic/Ribbon%20Overview.md).  
  
<a name="grouped_virtualization"></a>   
## Повышенная производительность при отображении больших наборов сгруппированных данных  
 Виртуализация пользовательского интерфейса происходит, когда подмножество элементов пользовательского интерфейса \(пользовательского интерфейса\) создается из большего количества элементов данных, основываясь на элементы, которые отображаются на экране.  <xref:System.Windows.Controls.VirtualizingPanel> определяет присоединенное свойство <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>, включающее виртуализации пользовательского интерфейса для сгруппированных данных.  Дополнительные сведения о группирования данных см. в разделах Практическое руководство. Сортировка и данные о группе, используя представление в языке XAML.  Дополнительные сведения о виртуализировать группированные данные см. в разделе присоединенное свойство <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>.  
  
<a name="VirtualizingPanel"></a>   
## Новые функции для VirtualizingPanel  
  
1.  Можно указать указывающее, является ли <xref:System.Windows.Controls.VirtualizingPanel>, как <xref:System.Windows.Controls.VirtualizingStackPanel> частично элементы с помощью присоединенного свойства <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>.  Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> установлено в <xref:System.Windows.Controls.ScrollUnit>, то <xref:System.Windows.Controls.VirtualizingPanel> равна только папки отображения, которые полностью видимым.  Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> установлено в <xref:System.Windows.Controls.ScrollUnit>, то <xref:System.Windows.Controls.VirtualizingPanel> может отображать частично видимые элементы.  
  
2.  Можно указать размер кэша до и после окне просмотра при <xref:System.Windows.Controls.VirtualizingPanel> виртуализирует с помощью присоединенного свойства <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A>.  Кэш отступ выше или ниже является окном просмотра, в котором элементы не виртуализироватьы.  Использование кэша избежать создания элементов пользовательского интерфейса по мере их прокручены в представление может улучшить производительность.  Кэш заполнения на более низком уровне приоритета, так что приложение не станет безответный во время операции.  Свойство <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=fullName> задает единицу измерения, используемую <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=fullName>.  
  
<a name="static_properties"></a>   
## Привязка к статическим свойствам  
 Можно использовать статические свойства, как источник привязки данных.  Механизм привязки данных распознает при изменении значения этого свойства, если статическое возникновении события.  Например, если класс `SomeClass` задает статическое свойство с именем `MyProperty`, то `SomeClass` может указать статическое событие, которое возникает при изменении значения `MyProperty`.  Статическое событие может использовать любую из следующих сигнатур.  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Обратите внимание, что в первом случае открыто разоблачениях класса *PropertyName*`Changed` статическое именованное событие, которое передает <xref:System.EventArgs> в обработчик событий.  Во втором случае класс предоставляет статическое `StaticPropertyChanged` именованное событие, которое передает <xref:System.ComponentModel.PropertyChangedEventArgs> в обработчик событий.  Класс, реализующий статическое свойство может создавать уведомления свойство\- изменения с помощью любого метода.  
  
<a name="xthread_access"></a>   
## Доступ к коллекции в потоках, отличный от пользовательского интерфейса  
 WPF позволяет получить доступ и изменения коллекций данных в потоках, кроме одного, которая создала коллекции.  Это позволяет использовать фонового потока получить данные из внешнего источника, например из базы данных, и отображает данные в потоке пользовательского интерфейса.  С помощью другого потока для изменения коллекции, пользовательский интерфейс остается отзывчивым на действия пользователя.  
  
<a name="INotifyDataErrorInfo"></a>   
## Синхронно и асинхронно проверка данных  
 Интерфейс <xref:System.ComponentModel.INotifyDataErrorInfo> разрешает классы сущностей данных для реализации пользовательских правил проверки и представить результаты проверки в асинхронном режиме.  Этот интерфейс также поддерживает пользовательские объекты ошибок несколько ошибок в свойство крест\- свойства, ошибки и ошибки сущность\- уровня.  Дополнительные сведения см. в разделе <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## Автоматическое обновление источника привязки данных  
 При использовании привязки данных для обновления источника данных, можно использовать свойство <xref:System.Windows.Data.BindingBase.Delay%2A> чтобы определить время передачи после изменении свойства целевого объекта до обновления источника.  Например, предположим, что имеется <xref:System.Windows.Controls.Slider>, есть границы сведения о свойстве <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> двусторонние к свойству объекта данных и <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство установлено в <xref:System.Windows.Data.UpdateSourceTrigger>.  В данном примере, когда пользователь перемещает <xref:System.Windows.Controls.Slider> обновления источника для каждого пикселя, <xref:System.Windows.Controls.Slider>.  Исходный объект обычно требуется значение "ползунок" только при <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> ползунка останавливает изменить.  Чтобы предотвратить обновление источника слишком часто, используйте <xref:System.Windows.Data.BindingBase.Delay%2A> чтобы указать, что источник не должен быть обновлен до тех пор, пока некоторое время времени после того как бегунок останавливает перемещения.  
  
<a name="ICustomTypeProvider"></a>   
## Привязка к типам, которые реализуют ICustomTypeProvider  
 WPF поддерживают привязку данных к объектам, реализующим <xref:System.Reflection.ICustomTypeProvider>, также известного как пользовательские типы.  Пользовательские типы можно использовать в следующих случаях.  
  
1.  Как <xref:System.Windows.PropertyPath> в привязке данных.  Например, свойство <xref:System.Windows.Data.Binding.Path%2A><xref:System.Windows.Data.Binding> может ссылаться на свойство пользовательского типа.  
  
2.  В качестве значения свойства <xref:System.Windows.DataTemplate.DataType%2A>.  
  
3.  Как тип, который определяет автоматически созданные столбцы в <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## Получение сведений о привязке из выражения привязки данных  
 В некоторых случаях может потребоваться получить <xref:System.Windows.Data.BindingExpression><xref:System.Windows.Data.Binding> и сведения об источнике и целевых объектов привязки.  Новые api\-интерфейсы были добавлены, чтобы пользователь мог для получения источником или целевой объект или связанное свойство.  При наличии <xref:System.Windows.Data.BindingExpression>, используйте следующие api\-интерфейсы для получения сведений о целевом объекте и источнике.  
  
|Найти это значение привязки|Используйте данный API|  
|---------------------------------|----------------------------|  
|Целевой объект|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=fullName>|  
|Свойство целевого объекта|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=fullName>|  
|Исходный объект|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=fullName>|  
|Свойство источника|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=fullName>|  
|Принадлежность к <xref:System.Windows.Data.BindingGroup><xref:System.Windows.Data.BindingExpression>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=fullName>|  
|Владелец <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## Проверка допустимого объекта DataContext  
 Случаи, когда <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элемента в <xref:System.Windows.Controls.ItemsControl> отключается.  Контейнер элементов элемент пользовательского интерфейса, указывающий элемент в <xref:System.Windows.Controls.ItemsControl>.  При <xref:System.Windows.Controls.ItemsControl> данные, привязанные к коллекции, контейнер элемента создается для каждого элемента.  В некоторых случаях контейнеров элементов удалены от визуального дерева.  2 Типичных варианта, когда контейнер элементов удалить, когда элемент удаляется из базовой коллекции и, если виртуализация включена в <xref:System.Windows.Controls.ItemsControl>.  В таких случаях свойство <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элемента будет установлено на объект часового, возвращаемый статическим свойством <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=fullName>.  Следует проверить, является ли <xref:System.Windows.FrameworkElement.DataContext%2A> равен объекту <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> до получения доступа к <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элемента.  
  
<a name="live_shaping"></a>   
## Перемещающ данные в виде значения данных измените \(формирование Live\)  
 Сбор данных можно группировать, сортировать и фильтровать.  WPF 4,5 включает данные для изменения порядка при изменении данных.  Например, пусть приложение использует <xref:System.Windows.Controls.DataGrid> для перечисления запасы в фондовой бирже и запасы отсортированы стандартное значение.  Если сортировка в реальном времени включена в <xref:System.Windows.Data.CollectionView> запасов, то положение акций в <xref:System.Windows.Controls.DataGrid> перемещает, когда стандартное значение будет больше, чем значение другого или биржевых.  Дополнительные сведения см. в описании интерфейса <xref:System.ComponentModel.ICollectionViewLiveShaping>.  
  
<a name="weak_event_pattern"></a>   
## Улучшенная поддержка устанавливать слабую ссылку на событие  
 Реализация шаблона слабых событий теперь проще, поскольку подписчики на события могут участвовать в нем без реализации дополнительного интерфейса.  Универсальный класс <xref:System.Windows.WeakEventManager> также позволяет подписчикам для участия в слабом шаблоне события, если выделенный <xref:System.Windows.WeakEventManager> не существует для достоверного события.  Дополнительные сведения см. в разделе [Шаблоны слабых событий](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## Новые методы класса диспетчера  
 Новые методы класса диспетчера определяет синхронные и асинхронные операции.  Определяет синхронный метод <xref:System.Windows.Threading.Dispatcher.Invoke%2A> перегруженных методов, принимающих параметр <xref:System.Action> или <xref:System.Func%601>.  Новый асинхронный метод, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, также принимает <xref:System.Action> или <xref:System.Func%601> в качестве параметра обратного вызова и возвращает <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>.  Классы <xref:System.Windows.Threading.DispatcherOperation> и <xref:System.Windows.Threading.DispatcherOperation%601> определяют свойства <xref:System.Threading.Tasks.Task>.  При вызове <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, можно использовать ключевое слово `await` с <xref:System.Windows.Threading.DispatcherOperation> или связанным <xref:System.Threading.Tasks.Task>.  Если необходимо дождаться одновременно для <xref:System.Threading.Tasks.Task>, которое возвращается <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, вызовите метод расширения <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>.  Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> приведет к взаимоблокировке, если операция в очереди в вызывающем потоке.  Дополнительные сведения об использовании <xref:System.Threading.Tasks.Task> выполнять асинхронные операции просмотра [Параллелизм задач \(библиотека параллельных задач\)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## Расширения разметки для событий  
 Расширения разметки WPF 4,5 обозреватель событий.  В WPF не определяет расширение разметки, используемый для событий, сторонние разработчики могут создать расширение разметки, можно использовать с событиями.  
  
## См. также  
 [Новые возможности .NET Framework](../../../../docs/framework/whats-new/index.md)