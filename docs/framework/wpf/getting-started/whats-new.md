---
title: Новые возможности WPF версии 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 8eff8da7746047c450b2e23af63d43b13f3b970c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746921"
---
# <a name="whats-new-in-wpf-version-45"></a>Новые возможности WPF версии 4.5
<a name="introduction"></a>В этом разделе содержатся сведения о новых и улучшенных возможностях в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] версии 4,5.  
  
 В этом разделе содержатся следующие подразделы.  
  
- [Элемент управления ленты](#ribbon_control)  
  
- [Повышение производительности при отображении больших наборов сгруппированных данных](#grouped_virtualization)  
  
- [Новые возможности VirtualizingPanel](#VirtualizingPanel)  
  
- [Привязка к статическим свойствам](#static_properties)  
  
- [Доступ к коллекциям в потоках без пользовательского интерфейса](#xthread_access)  
  
- [Синхронная и асинхронная проверка данных](#INotifyDataErrorInfo)  
  
- [Автоматическое обновление источника привязки данных](#delay)  
  
- [Привязки к типам, реализующим ICustomTypeProvider](#ICustomTypeProvider)  
  
- [Получение сведений о привязке данных из выражения привязки](#binding_state)  
  
- [Проверка наличия допустимого объекта DataContext](#DisconnectedSource)  
  
- [Изменение расположения данных по мере изменение их значений (формирование данных в реальном времени)](#live_shaping)  
  
- [Улучшенная поддержка установления слабой ссылки на событие](#weak_event_pattern)  
  
- [Новые методы для класса Dispatcher](#async)  
  
- [Расширения разметки для событий](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>Элемент управления ленты  
 В состав WPF 4,5 входит элемент управления <xref:System.Windows.Controls.Ribbon.Ribbon>, в котором размещается панель быстрого доступа, меню приложения и вкладки.  Дополнительные сведения см. в разделе [Общие сведения об ленте](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Повышение производительности при отображении больших наборов сгруппированных данных  
 Когда подмножество элементов пользовательского интерфейса создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране, происходит виртуализация пользовательского интерфейса. <xref:System.Windows.Controls.VirtualizingPanel> определяет присоединенное <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> свойство, которое позволяет реализовать виртуализацию пользовательского интерфейса для сгруппированных данных.  Дополнительные сведения о группировании данных см. в разделе "Практическое руководство. Сортировка и группы данных с помощью представления в XAML".  Дополнительные сведения о виртуализации сгруппированных данных см. в разделе присоединенное свойство <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Новые возможности VirtualizingPanel  
  
1. Можно указать, будет ли <xref:System.Windows.Controls.VirtualizingPanel>, например <xref:System.Windows.Controls.VirtualizingStackPanel>, отображать частичные элементы с помощью вложенного свойства <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> имеет значение <xref:System.Windows.Controls.ScrollUnit.Item>, <xref:System.Windows.Controls.VirtualizingPanel> будут отображаться только полностью видимые элементы. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> имеет значение <xref:System.Windows.Controls.ScrollUnit.Pixel>, <xref:System.Windows.Controls.VirtualizingPanel> может отображать частично видимые элементы.  
  
2. Можно указать размер кэша до и после окна просмотра, когда <xref:System.Windows.Controls.VirtualizingPanel> будет виртуализироваться с помощью <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> присоединенного свойства.  Кэш — это объем области, расположенной выше или ниже окна просмотра, элементы в котором не являются виртуальными.  Используя кэш, чтобы предотвратить создание элементов пользовательского интерфейса по мере их прокрутки, можно повысить производительность. Кэш заполняется с низким приоритетом, так что приложение не перестает отвечать на запросы во время этой операции. Свойство <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> определяет единицу измерения, используемую <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Привязка к статическим свойствам  
 Статические свойства могут служить источником привязки данных. Когда возникает статическое событие, механизм привязки данных распознает изменение в значении подобного свойства.  Например, если класс `SomeClass` определяет статическое свойство с именем `MyProperty`, `SomeClass` может определять статическое событие, которое вызывается при изменении значения `MyProperty`.  Статическое событие может использовать одну из следующих сигнатур.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Обратите внимание, что в первом случае класс предоставляет статическое событие с именем *PropertyName*`Changed`, которое передает <xref:System.EventArgs> обработчику событий.  Во втором случае класс предоставляет статическое событие с именем `StaticPropertyChanged`, которое передает <xref:System.ComponentModel.PropertyChangedEventArgs> обработчику событий. Класс, реализующий статическое свойство, может выдавать уведомления об изменениях в свойства, используя любой из этих методов.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Доступ к коллекциям в потоках без пользовательского интерфейса  
 WPF позволяет получать доступ к коллекциям данных в потоках, отличных от потоков, создавших эти коллекции, и вносить в них изменения.  Это позволяет получать данные из внешнего источника, например базы данных, в фоновый поток и отображать данные в потоке пользовательского интерфейса.  Если для изменения коллекции используется другой поток, пользовательский интерфейс продолжает отвечать на команды пользователя.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Синхронная и асинхронная проверка данных  
 Интерфейс <xref:System.ComponentModel.INotifyDataErrorInfo> позволяет классам сущностей данных реализовывать пользовательские правила проверки и предоставлять результаты проверки в асинхронном режиме. Этот интерфейс также поддерживает объекты специальных ошибок, нескольких ошибок для каждого свойства, ошибок нескольких свойств и ошибок на уровне сущности.  Для получения дополнительной информации см. <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Автоматическое обновление источника привязки данных  
 При использовании привязки данных для обновления источника данных можно использовать свойство <xref:System.Windows.Data.BindingBase.Delay%2A>, чтобы указать количество времени, которое будет передаваться после изменения свойства на целевом объекте перед обновлением источника.  Например, предположим, что у вас есть <xref:System.Windows.Controls.Slider>, имеющий <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> свойства, двусторонняя привязка к свойству объекта данных, а свойству <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> — значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  В этом примере, когда пользователь перемещает <xref:System.Windows.Controls.Slider>, источник обновляется для каждого пикселя, который перемещает <xref:System.Windows.Controls.Slider>.  Исходный объект обычно нуждается в значении ползунка, только когда <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> ползунка перестает изменяться.  Чтобы предотвратить слишком частое обновление источника, используйте <xref:System.Windows.Data.BindingBase.Delay%2A>, чтобы указать, что источник не должен обновляться до истечения определенного промежутка времени после того, как бегунок прекратит двигаться.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Привязка к типам, реализующим ICustomTypeProvider  
 WPF поддерживает привязку данных к объектам, которые реализуют <xref:System.Reflection.ICustomTypeProvider>, также известные как пользовательские типы.  Пользовательские типы можно использовать в следующих случаях:  
  
1. В качестве <xref:System.Windows.PropertyPath> привязки данных. Например, свойство <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding> может ссылаться на свойство пользовательского типа.  
  
2. В качестве значения свойства <xref:System.Windows.DataTemplate.DataType%2A>.  
  
3. Как тип, определяющий автоматически создаваемые столбцы в <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Получение сведений о привязке данных из выражения привязки  
 В некоторых случаях может возникнуть <xref:System.Windows.Data.BindingExpression> <xref:System.Windows.Data.Binding> и требуются сведения об исходном и целевом объектах привязки.  Новые интерфейсы API позволят вам получить исходный и целевой объект или связанное свойство.  При наличии <xref:System.Windows.Data.BindingExpression>используйте следующие интерфейсы API для получения сведений о целевом и исходном источнике.  
  
|Чтобы найти это значение привязки|Используйте этот API|  
|---------------------------------------|------------------|  
|Целевой объект|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Целевое свойство|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Исходный объект|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Исходное свойство|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Относится ли <xref:System.Windows.Data.BindingExpression> к <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Владелец <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Проверка наличия допустимого объекта DataContext  
 Бывают случаи, когда <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элементов в <xref:System.Windows.Controls.ItemsControl> отключается.  Контейнер элемента — это элемент пользовательского интерфейса, который отображает элемент в <xref:System.Windows.Controls.ItemsControl>.  Если <xref:System.Windows.Controls.ItemsControl> данные привязаны к коллекции, для каждого элемента создается контейнер элементов. В некоторых случаях контейнеры элементов удаляются из визуального дерева. Два типичных случая удаления контейнера элементов — при удалении элемента из базовой коллекции и при включении виртуализации на <xref:System.Windows.Controls.ItemsControl>. В этих случаях свойству <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элемента будет присвоено значение объекта Sentinel, возвращаемого статическим свойством <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType>.  Перед доступом к <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элементов следует проверить, равен ли <xref:System.Windows.FrameworkElement.DataContext%2A> объекту <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A>.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Изменение расположения данных по мере изменения их значений (формирование данных в реальном времени)  
 Коллекцию данных можно группировать, сортировать и фильтровать. WPF 4.5 позволяет изменять порядок данных при их изменении. Например, предположим, что приложение использует <xref:System.Windows.Controls.DataGrid> для составления списка акций на биржевом рынке, а акции сортируются по стоимости запасов. Если в <xref:System.Windows.Data.CollectionView>акции включена Динамическая сортировка, то в <xref:System.Windows.Controls.DataGrid> перемещается значение склада на бумаге, когда стоимость акций становится больше или меньше значения другого запаса.   Дополнительные сведения см. в описании интерфейса <xref:System.ComponentModel.ICollectionViewLiveShaping>.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Улучшенная поддержка установления слабой ссылки на событие  
 Реализация шаблона слабых событий стала проще, поскольку подписчики на события теперь могут принимать в ней участие без реализации дополнительного интерфейса.  Универсальный класс <xref:System.Windows.WeakEventManager> также позволяет подписчикам участвовать в шаблоне слабых событий, если для определенного события не существует выделенного <xref:System.Windows.WeakEventManager>.  Дополнительные сведения см. в разделе [Шаблоны слабых событий](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Новые методы для класса Dispatcher  
 Класс Dispatcher определяет новые методы для синхронных и асинхронных операций.  Синхронный <xref:System.Windows.Threading.Dispatcher.Invoke%2A> метод определяет перегрузки, принимающие параметр <xref:System.Action> или <xref:System.Func%601>. Новый асинхронный метод <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>также принимает <xref:System.Action> или <xref:System.Func%601> в качестве параметра обратного вызова и возвращает <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>.   Классы <xref:System.Windows.Threading.DispatcherOperation> и <xref:System.Windows.Threading.DispatcherOperation%601> определяют свойство <xref:System.Threading.Tasks.Task>.  При вызове <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>можно использовать ключевое слово `await` с <xref:System.Windows.Threading.DispatcherOperation> или связанным <xref:System.Threading.Tasks.Task>. Если необходимо выполнить синхронное ожидание <xref:System.Threading.Tasks.Task>, возвращаемого <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, вызовите метод расширения <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>. Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> приведет к взаимоблокировке, если операция помещается в очередь вызывающего потока. Дополнительные сведения об использовании <xref:System.Threading.Tasks.Task> для выполнения асинхронных операций см. в разделе [параллелизм задач (библиотека параллельных задач)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Расширения разметки для событий  
 WPF 4.5 поддерживает расширения разметки для событий.  Несмотря на то, что WPF не определяет расширение разметки для применения с событиями, третьи стороны могут создавать расширение разметки, которое можно использовать с событиями.  
  
## <a name="see-also"></a>См. также:

- [Новые возможности .NET Framework](../../whats-new/index.md)
