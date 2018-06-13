---
title: Новые возможности WPF версии 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 4e022f75808de36666e53d3e58a0806e4f6d15ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558100"
---
# <a name="what39s-new-in-wpf-version-45"></a>Новые возможности WPF версии 4.5
<a name="introduction"></a> Этот раздел содержит сведения о новых и усовершенствованных возможностях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] версии 4.5.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Элемент управления ленты](#ribbon_control)  
  
-   [Повышение производительности при отображении больших наборов сгруппированных данных](#grouped_virtualization)  
  
-   [Новые возможности VirtualizingPanel](#VirtualizingPanel)  
  
-   [Привязка к статическим свойствам](#static_properties)  
  
-   [Доступ к коллекциям в потоках без пользовательского интерфейса](#xthread_access)  
  
-   [Синхронная и асинхронная проверка данных](#INotifyDataErrorInfo)  
  
-   [Автоматическое обновление источника привязки данных](#delay)  
  
-   [Привязки к типам, реализующим ICustomTypeProvider](#ICustomTypeProvider)  
  
-   [Получение сведений о привязке данных из выражения привязки](#binding_state)  
  
-   [Проверка наличия допустимого объекта DataContext](#DisconnectedSource)  
  
-   [Изменение расположения данных по мере изменение их значений (формирование данных в реальном времени)](#live_shaping)  
  
-   [Улучшенная поддержка установления слабой ссылки на событие](#weak_event_pattern)  
  
-   [Новые методы для класса Dispatcher](#async)  
  
-   [Расширения разметки для событий](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>Элемент управления ленты  
 WPF 4.5 поставляется с <xref:System.Windows.Controls.Ribbon.Ribbon> элемента управления, в которой размещаются панель быстрого доступа, меню приложения и вкладки.  Дополнительные сведения см. в разделе [Общие сведения об ленте](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Повышение производительности при отображении больших наборов сгруппированных данных  
 Когда подмножество элементов пользовательского интерфейса создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране, происходит виртуализация пользовательского интерфейса. <xref:System.Windows.Controls.VirtualizingPanel> Определяет <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> вложенное свойство, которое включает виртуализации пользовательского интерфейса для сгруппированных данных.  Дополнительные сведения о группировании данных см. в разделе "Практическое руководство. Сортировка и группы данных с помощью представления в XAML".  Дополнительные сведения о виртуализации сгруппированных данных, см. в разделе <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> вложенное свойство.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Новые возможности VirtualizingPanel  
  
1.  Можно указать ли <xref:System.Windows.Controls.VirtualizingPanel>, такие как <xref:System.Windows.Controls.VirtualizingStackPanel>, отображение с использованием частичного <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> вложенное свойство. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> равно <xref:System.Windows.Controls.ScrollUnit.Item>, <xref:System.Windows.Controls.VirtualizingPanel> отображает только полностью видимых элементов. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> равно <xref:System.Windows.Controls.ScrollUnit.Pixel>, <xref:System.Windows.Controls.VirtualizingPanel> можно отобразить элементы частично видимой.  
  
2.  Можно указать размер кэша до и после просмотра при <xref:System.Windows.Controls.VirtualizingPanel> виртуализации с помощью <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> вложенное свойство.  Кэш — это объем области, расположенной выше или ниже окна просмотра, элементы в котором не являются виртуальными.  Используя кэш, чтобы предотвратить создание элементов пользовательского интерфейса по мере их прокрутки, можно повысить производительность. Кэш заполняется с низким приоритетом, так что приложение не перестает отвечать на запросы во время этой операции. <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> Свойство определяет единицы измерения, используемый <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Привязка к статическим свойствам  
 Статические свойства могут служить источником привязки данных. Когда возникает статическое событие, механизм привязки данных распознает изменение в значении подобного свойства.  Например, если класс `SomeClass` определяет статическое свойство с именем `MyProperty`, `SomeClass` может определять статическое событие, которое вызывается при изменении значения `MyProperty`.  Статическое событие может использовать одну из следующих сигнатур.  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Обратите внимание, что в первом случае класс предоставляет статическое событие с именем *PropertyName* `Changed` , проходящего <xref:System.EventArgs> обработчику событий.  Во втором случае класс предоставляет статическое событие с именем `StaticPropertyChanged` , проходящего <xref:System.ComponentModel.PropertyChangedEventArgs> обработчику событий. Класс, реализующий статическое свойство, может выдавать уведомления об изменениях в свойства, используя любой из этих методов.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Доступ к коллекциям в потоках без пользовательского интерфейса  
 WPF позволяет получать доступ к коллекциям данных в потоках, отличных от потоков, создавших эти коллекции, и вносить в них изменения.  Это позволяет получать данные из внешнего источника, например базы данных, в фоновый поток и отображать данные в потоке пользовательского интерфейса.  Если для изменения коллекции используется другой поток, пользовательский интерфейс продолжает отвечать на команды пользователя.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Синхронная и асинхронная проверка данных  
 <xref:System.ComponentModel.INotifyDataErrorInfo> Интерфейс позволяет классами сущностей данных для реализации пользовательских правил проверки и предоставляют результаты проверки асинхронно. Этот интерфейс также поддерживает объекты специальных ошибок, нескольких ошибок для каждого свойства, ошибок нескольких свойств и ошибок на уровне сущности.  Дополнительные сведения см. в разделе <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Автоматическое обновление источника привязки данных  
 При использовании привязки данных для обновления источника данных можно использовать <xref:System.Windows.Data.BindingBase.Delay%2A> свойство, чтобы указать дополнительное время для передачи после изменения свойств на целевом сервере перед обновлением источника.  Предположим, что имеется <xref:System.Windows.Controls.Slider> с его <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> данные свойства двустороннее связаны со свойством объекта данных и <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойству <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  В этом примере, когда пользователь перемещает <xref:System.Windows.Controls.Slider>, обновления источника для каждой точки, <xref:System.Windows.Controls.Slider> перемещение.  Исходный объект обычно требуется значение ползунка только если ползунок <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> останавливает изменение.  Чтобы предотвратить обновление источника слишком часто, используйте <xref:System.Windows.Data.BindingBase.Delay%2A> для указания, источник не должны обновляться, пока определенное время, прошедшее после бегунка останавливает перемещение.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Привязки к типам, реализуйте ICustomTypeProvider  
 WPF поддерживает привязку данных к объектам, реализующим <xref:System.Reflection.ICustomTypeProvider>, известного также как пользовательские типы.  Пользовательские типы можно использовать в следующих случаях:  
  
1.  Как <xref:System.Windows.PropertyPath> в привязке данных. Например <xref:System.Windows.Data.Binding.Path%2A> свойство <xref:System.Windows.Data.Binding> могут ссылаться на свойство пользовательского типа.  
  
2.  В качестве значения <xref:System.Windows.DataTemplate.DataType%2A> свойство.  
  
3.  Как тип, который определяет, автоматически созданные столбцы в <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Получение сведений о привязке данных из выражения привязки  
 В некоторых случаях может появиться <xref:System.Windows.Data.BindingExpression> из <xref:System.Windows.Data.Binding> о исходных и целевых объектов привязки.  Новые интерфейсы API позволят вам получить исходный и целевой объект или связанное свойство.  При наличии <xref:System.Windows.Data.BindingExpression>, используйте следующие интерфейсы API для получения сведений об исходной и целевой.  
  
|Чтобы найти это значение привязки|Используйте этот API|  
|---------------------------------------|------------------|  
|Целевой объект|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Целевое свойство|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Исходный объект|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Исходное свойство|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Ли <xref:System.Windows.Data.BindingExpression> принадлежит <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Владелец <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Проверка наличия допустимого объекта DataContext  
 Существуют случаи где <xref:System.Windows.FrameworkElement.DataContext%2A> элемента контейнера в <xref:System.Windows.Controls.ItemsControl> будет отключен.  Контейнер элементов является элементом пользовательского интерфейса, который отображает элемент в <xref:System.Windows.Controls.ItemsControl>.  Когда <xref:System.Windows.Controls.ItemsControl> данные связаны с коллекцией контейнера элемента создается для каждого элемента. В некоторых случаях контейнеры элементов удаляются из визуального дерева. Два типичных случаев, где удалить контейнер элементов, при удалении элемента из коллекции и при включении виртуализации на <xref:System.Windows.Controls.ItemsControl>. В этих случаях <xref:System.Windows.FrameworkElement.DataContext%2A> свойство контейнера элементов будет присвоено sentinel объект, возвращаемый <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> статическое свойство.  Стоит ли <xref:System.Windows.FrameworkElement.DataContext%2A> равен <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> объекта перед обращением к <xref:System.Windows.FrameworkElement.DataContext%2A> контейнера элемента.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Изменение расположения данных по мере изменения их значений (формирование данных в реальном времени)  
 Коллекцию данных можно группировать, сортировать и фильтровать. WPF 4.5 позволяет изменять порядок данных при их изменении. Например, предположим, что приложение использует <xref:System.Windows.Controls.DataGrid> списка акций на фондовой биржи и акции сортируются по стоимость запасов. Если включена динамическая сортировка на акции <xref:System.Windows.Data.CollectionView>, биржевая позиции в <xref:System.Windows.Controls.DataGrid> перемещений, когда значение акций станет больше или значение меньше другого stock.   Дополнительные сведения см. в разделе <xref:System.ComponentModel.ICollectionViewLiveShaping> интерфейса.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Улучшенная поддержка установления слабой ссылки на событие  
 Реализация шаблона слабых событий стала проще, поскольку подписчики на события теперь могут принимать в ней участие без реализации дополнительного интерфейса.  Универсальный <xref:System.Windows.WeakEventManager> класса также позволяет подписчикам участвовать в шаблон слабых событий, если выделенное <xref:System.Windows.WeakEventManager> не существует для определенного события.  Дополнительные сведения см. в разделе [Шаблоны слабых событий](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Новые методы для класса Dispatcher  
 Класс Dispatcher определяет новые методы для синхронных и асинхронных операций.  Синхронный <xref:System.Windows.Threading.Dispatcher.Invoke%2A> метод определяет перегрузки, использующие <xref:System.Action> или <xref:System.Func%601> параметра. Новый асинхронный метод <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, также принимает <xref:System.Action> или <xref:System.Func%601> параметр обратного вызова и возвращающую <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>.   <xref:System.Windows.Threading.DispatcherOperation> И <xref:System.Windows.Threading.DispatcherOperation%601> классы определяют <xref:System.Threading.Tasks.Task> свойство.  При вызове <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, можно использовать `await` ключевого слова with либо <xref:System.Windows.Threading.DispatcherOperation> или связанного <xref:System.Threading.Tasks.Task>. Если необходимо подождать синхронно <xref:System.Threading.Tasks.Task> , возвращаемый <xref:System.Windows.Threading.DispatcherOperation> или <xref:System.Windows.Threading.DispatcherOperation%601>, вызовите <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> метода расширения. Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> приведет к взаимоблокировке, если операция помещается в очередь в вызывающий поток. Дополнительные сведения об использовании <xref:System.Threading.Tasks.Task> для выполнения асинхронных операций, в разделе [параллелизм задач (библиотека параллельных задач)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Расширения разметки для событий  
 WPF 4.5 поддерживает расширения разметки для событий.  Несмотря на то, что WPF не определяет расширение разметки для применения с событиями, третьи стороны могут создавать расширение разметки, которое можно использовать с событиями.  
  
## <a name="see-also"></a>См. также  
 [Новые возможности .NET Framework](../../../../docs/framework/whats-new/index.md)
