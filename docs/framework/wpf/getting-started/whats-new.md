---
title: Новые возможности WPF версии 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 708b2fc231bfe7a9bc1f52872a0ec41c91931f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174710"
---
# <a name="whats-new-in-wpf-version-45"></a>Новые возможности WPF версии 4.5
<a name="introduction"></a>Эта тема содержит информацию о [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] новых и расширенных функциях в версии 4.5.  
  
 Этот раздел состоит из следующих подразделов.  
  
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
  
- [Изменение расположения данных по мере изменения их значений (формирование данных в реальном времени)](#live_shaping)  
  
- [Улучшенная поддержка установления слабой ссылки на событие](#weak_event_pattern)  
  
- [Новые методы для класса Dispatcher](#async)  
  
- [Расширения разметки для событий](#events_markup_extenions)  
  
<a name="ribbon_control"></a>
## <a name="ribbon-control"></a>Элемент управления ленты  
 WPF 4.5 поставляется <xref:System.Windows.Controls.Ribbon.Ribbon> с управлением, в котором размещается панель инструментов быстрого доступа, меню приложений и вкладки.  Дополнительные сведения см. в разделе [Общие сведения об ленте](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Повышение производительности при отображении больших наборов сгруппированных данных  
 Когда подмножество элементов пользовательского интерфейса создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране, происходит виртуализация пользовательского интерфейса. Определяет <xref:System.Windows.Controls.VirtualizingPanel> прилагаемое <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> свойство, позволяющее виртуализацию uI для сгруппированных данных.  Дополнительные сведения о группировании данных см. в разделе "Практическое руководство. Сортировка и группы данных с помощью представления в XAML".  Для получения дополнительной информации о виртуализации группированных данных см. <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>  
  
<a name="VirtualizingPanel"></a>
## <a name="new-features-for-the-virtualizingpanel"></a>Новые возможности VirtualizingPanel  
  
1. Вы можете указать, <xref:System.Windows.Controls.VirtualizingPanel>отображает <xref:System.Windows.Controls.VirtualizingStackPanel>ли, например, <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> элементы частичного использования прилагаемого свойства. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> установлен <xref:System.Windows.Controls.ScrollUnit.Item>на, <xref:System.Windows.Controls.VirtualizingPanel> будет отображать только элементы, которые полностью видны. Если <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> <xref:System.Windows.Controls.ScrollUnit.Pixel>установлен, может <xref:System.Windows.Controls.VirtualizingPanel> отображать частично видимые элементы.  
  
2. Можно указать размер кэша до и после <xref:System.Windows.Controls.VirtualizingPanel> просмотра, когда он <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> виртуализируется с помощью прилагаемого свойства.  Кэш — это объем области, расположенной выше или ниже окна просмотра, элементы в котором не являются виртуальными.  Используя кэш, чтобы предотвратить создание элементов пользовательского интерфейса по мере их прокрутки, можно повысить производительность. Кэш заполняется с низким приоритетом, так что приложение не перестает отвечать на запросы во время этой операции. Свойство <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> определяет единицу измерения, которая <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>используется .  
  
<a name="static_properties"></a>
## <a name="binding-to-static-properties"></a>Привязка к статическим свойствам  
 Статические свойства могут служить источником привязки данных. Когда возникает статическое событие, механизм привязки данных распознает изменение в значении подобного свойства.  Например, если класс `SomeClass` определяет статическое свойство с именем `MyProperty`, `SomeClass` может определять статическое событие, которое вызывается при изменении значения `MyProperty`.  Статическое событие может использовать одну из следующих сигнатур.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Обратите внимание, что в первом случае класс предоставляет статическое <xref:System.EventArgs> событие под названием *PropertyName,* `Changed` которое передается обработчику событий.  Во втором случае класс предоставляет статическое `StaticPropertyChanged` событие, <xref:System.ComponentModel.PropertyChangedEventArgs> названное, которое переходит к обработчику событий. Класс, реализующий статическое свойство, может выдавать уведомления об изменениях в свойства, используя любой из этих методов.  
  
<a name="xthread_access"></a>
## <a name="accessing-collections-on-non-ui-threads"></a>Доступ к коллекциям в потоках без пользовательского интерфейса  
 WPF позволяет получать доступ к коллекциям данных в потоках, отличных от потоков, создавших эти коллекции, и вносить в них изменения.  Это позволяет получать данные из внешнего источника, например базы данных, в фоновый поток и отображать данные в потоке пользовательского интерфейса.  Если для изменения коллекции используется другой поток, пользовательский интерфейс продолжает отвечать на команды пользователя.  
  
<a name="INotifyDataErrorInfo"></a>
## <a name="synchronously-and-asynchronously-validating-data"></a>Синхронная и асинхронная проверка данных  
 Интерфейс <xref:System.ComponentModel.INotifyDataErrorInfo> позволяет классам сущности данных реализовать пользовательские правила проверки и выставлять результаты проверки асинхронно. Этот интерфейс также поддерживает объекты специальных ошибок, нескольких ошибок для каждого свойства, ошибок нескольких свойств и ошибок на уровне сущности.  Дополнительные сведения см. в разделе <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Автоматическое обновление источника привязки данных  
 Если вы используете привязку данных для <xref:System.Windows.Data.BindingBase.Delay%2A> обновления источника данных, можно использовать свойство, чтобы указать время, чтобы пройти после изменения свойства на цели до обновления источника.  Например, предположим, <xref:System.Windows.Controls.Slider> что у <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> вас есть данные о свойствах, двусторонние, связанные с свойством объекта данных, и <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство настроено на то, чтобы <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  В этом примере, когда <xref:System.Windows.Controls.Slider>пользователь перемещает, источник обновляет <xref:System.Windows.Controls.Slider> для каждого пикселя, который перемещается.  Объект у источника обычно нуждается в значении ползунка только тогда, когда ползунок <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> перестает меняться.  Чтобы предотвратить слишком частое <xref:System.Windows.Data.BindingBase.Delay%2A> обновление источника, используйте, чтобы указать, что источник не должен обновляться до тех пор, пока определенное количество времени не истечится после того, как большой палец перестает двигаться.  
  
<a name="ICustomTypeProvider"></a>
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Привязки к типам, реализующим ICustomTypeProvider  
 WPF поддерживает привязку <xref:System.Reflection.ICustomTypeProvider>данных к объектам, которые реализуют, также известный как пользовательские типы.  Пользовательские типы можно использовать в следующих случаях:  
  
1. Как <xref:System.Windows.PropertyPath> в связке данных. Например, <xref:System.Windows.Data.Binding.Path%2A> свойство <xref:System.Windows.Data.Binding> может ссылаться на свойство пользовательского типа.  
  
2. Как стоимость <xref:System.Windows.DataTemplate.DataType%2A> имущества.  
  
3. Как тип, определяющий автоматически генерируемые столбцы в <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Получение сведений о привязке данных из выражения привязки  
 В некоторых случаях вы <xref:System.Windows.Data.BindingExpression> можете <xref:System.Windows.Data.Binding> получить и нужна информация об источнике и целевых объектов связывания.  Новые интерфейсы API позволят вам получить исходный и целевой объект или связанное свойство.  Если у <xref:System.Windows.Data.BindingExpression>вас есть, используйте следующие AIS, чтобы получить информацию о цели и источнике.  
  
|Чтобы найти это значение привязки|Используйте этот API|  
|---------------------------------------|------------------|  
|Целевой объект|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Целевое свойство|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Исходный объект|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Исходное свойство|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Принадлежит <xref:System.Windows.Data.BindingExpression> ли принадлежность к<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Владелец<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>
## <a name="checking-for-a-valid-datacontext-object"></a>Проверка наличия допустимого объекта DataContext  
 Есть случаи, <xref:System.Windows.FrameworkElement.DataContext%2A> когда контейнер элемента в <xref:System.Windows.Controls.ItemsControl> становится отключенным.  Контейнер элемента — это элемент uI, <xref:System.Windows.Controls.ItemsControl>отображаемый элементом в .  Когда <xref:System.Windows.Controls.ItemsControl> данные связаны с коллекцией, для каждого элемента создается контейнер элемента. В некоторых случаях контейнеры элементов удаляются из визуального дерева. Два типичных случая, когда контейнер элемента удаляется, когда элемент удаляется из <xref:System.Windows.Controls.ItemsControl>базовой коллекции и когда включена виртуализация на . В этих случаях <xref:System.Windows.FrameworkElement.DataContext%2A> свойство контейнера элемента будет установлено на объект <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> дозорного, который возвращается статическим свойством.  Перед доступом <xref:System.Windows.FrameworkElement.DataContext%2A> к контейнеру <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> <xref:System.Windows.FrameworkElement.DataContext%2A> элемента следует проверить, равен ли объект объекту.  
  
<a name="live_shaping"></a>
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Изменение расположения данных по мере изменения их значений (формирование данных в реальном времени)  
 Коллекцию данных можно группировать, сортировать и фильтровать. WPF 4.5 позволяет изменять порядок данных при их изменении. Например, предположим, что <xref:System.Windows.Controls.DataGrid> приложение использует список акций на фондовом рынке, и акции сортируются по стоимости акций. Если живая сортировка <xref:System.Windows.Data.CollectionView>включена на акции ,, положение акций в <xref:System.Windows.Controls.DataGrid> движениях, когда стоимость акций становится больше или меньше, чем стоимость другого запаса.   Для получения дополнительной <xref:System.ComponentModel.ICollectionViewLiveShaping> информации, см.  
  
<a name="weak_event_pattern"></a>
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Улучшенная поддержка установления слабой ссылки на событие  
 Реализация шаблона слабых событий стала проще, поскольку подписчики на события теперь могут принимать в ней участие без реализации дополнительного интерфейса.  Общий <xref:System.Windows.WeakEventManager> класс также позволяет подписчикам участвовать <xref:System.Windows.WeakEventManager> в слабой схеме событий, если выделение не существует для определенного события.  Дополнительные сведения см. в разделе [Шаблоны слабых событий](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>
## <a name="new-methods-for-the-dispatcher-class"></a>Новые методы для класса Dispatcher  
 Класс Dispatcher определяет новые методы для синхронных и асинхронных операций.  Синхронный <xref:System.Windows.Threading.Dispatcher.Invoke%2A> метод определяет перегрузки, <xref:System.Func%601> которые принимают или <xref:System.Action> параметр. Новый асинхронный <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>метод, <xref:System.Action> , <xref:System.Func%601> также принимает или как <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601>параметр обратного вызова и возвращает или .   <xref:System.Windows.Threading.DispatcherOperation> Классы <xref:System.Windows.Threading.DispatcherOperation%601> определяют <xref:System.Threading.Tasks.Task> свойство.  При <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>вызове, вы `await` можете использовать ключевое слово либо с <xref:System.Windows.Threading.DispatcherOperation> или связанных с ними <xref:System.Threading.Tasks.Task>. Если вам нужно синхронно <xref:System.Threading.Tasks.Task> ждать, который <xref:System.Windows.Threading.DispatcherOperation> возвращается или, <xref:System.Windows.Threading.DispatcherOperation%601>позвоните <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> в метод расширения. Вызов <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> приведет к тупику, если операция стоит в очереди на потоке вызовов. Для получения дополнительной <xref:System.Threading.Tasks.Task> информации об использовании асинхронных операций [см.](../../../standard/parallel-programming/task-based-asynchronous-programming.md)  
  
<a name="events_markup_extenions"></a>
## <a name="markup-extensions-for-events"></a>Расширения разметки для событий  
 WPF 4.5 поддерживает расширения разметки для событий.  Несмотря на то, что WPF не определяет расширение разметки для применения с событиями, третьи стороны могут создавать расширение разметки, которое можно использовать с событиями.  
  
## <a name="see-also"></a>См. также раздел

- [Что нового в рамочной программе .NET](../../whats-new/index.md)
