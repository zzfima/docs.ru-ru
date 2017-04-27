---
title: "Оптимизация производительности: привязка данных | Microsoft Docs"
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
  - "привязка данных, производительность"
  - "привязка данных, производительность"
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Оптимизация производительности: привязка данных
Привязка данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает простой и согласованный способ представления данных и взаимодействия с ними в приложениях.  Можно связывать элементы с данными из разнообразных источников данных в форме объектов [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 В этом разделе содержатся рекомендации по оптимизации производительности привязки данных.  
  
   
  
<a name="HowDataBindingReferencesAreResolved"></a>   
## Как разрешаются ссылки для привязки данных  
 Прежде чем обсуждать вопросы производительности привязки данных, стоит рассмотреть, как ядро связывания данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разрешает ссылки на объекты для привязки.  
  
 Источником привязки данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может быть любой объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Можно выполнять привязку к свойствам, подсвойствам или индексаторам объекта [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Ссылки привязки разрешаются с помощью отражения [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] или <xref:System.ComponentModel.ICustomTypeDescriptor>.  Существуют три метода для разрешения ссылок на объекты для привязки:  
  
 Первый метод включает использование отражения.  В этом случае объект <xref:System.Reflection.PropertyInfo> используется для просмотра атрибутов свойства и обеспечивает доступ к метаданным свойства.  При использовании интерфейса <xref:System.ComponentModel.ICustomTypeDescriptor>, ядро привязки данных использует этот интерфейс для доступа к значениям свойств.  Интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor> является особенно полезным в случае, когда объект не имеет постоянного набора свойств.  
  
 Свойство уведомления об изменениях может быть предоставлено с помощью реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>, либо с помощью уведомлений об изменениях, связанных с <xref:System.ComponentModel.TypeDescriptor>.  Однако основной стратегией использования уведомлений об изменениях свойств является использование <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Если исходным объектом является объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], а исходным свойством является свойство [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], ядро привязки данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] должно сначала использовать отражение для исходного объекта, чтобы получить <xref:System.ComponentModel.TypeDescriptor>, а затем запросить <xref:System.ComponentModel.PropertyDescriptor>.  Эта последовательность операций отражения потенциально занимает очень много времени с точки зрения производительности.  
  
 Второй метод разрешения ссылок на объекты включает исходный объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], реализующий интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и исходное свойство, которое является свойством [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  В этом случае ядро привязки данных использует отражение непосредственно для исходного типа и возвращает необходимое свойство.  Это не самый оптимальный метод, но он менее трудозатратный, чем первый метод.  
  
 Третий метод для разрешения ссылок на объекты включает исходный объект <xref:System.Windows.DependencyObject> и исходное свойство <xref:System.Windows.DependencyProperty>.  В этом случае для использования отражения ядро привязки данных не требуется.  Вместо этого свойство ядра и ядро привязки данных независимо друг от друга разрешают ссылку на свойство.  Это оптимальный метод для разрешения ссылок на объекты, используемые для привязки данных.  
  
 Ниже в таблице сравнивается скорость привязки данных свойства <xref:System.Windows.Controls.TextBlock.Text%2A> для одной тысячи <xref:System.Windows.Controls.TextBlock> элементов с помощью этих трех методов.  
  
|**Связывание свойства Text элемента TextBlock**|**Время привязки \(мс\)**|**Время отображения — включает привязку \(мс\)**|  
|-----------------------------------------------------|-------------------------------|------------------------------------------------------|  
|К свойству объекта [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]|115|314|  
|К свойству объекта [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], который реализует <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|К <xref:System.Windows.DependencyProperty> для <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## Привязка к большим объектам среды CLR  
 Привязка данных к одному объекту [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с тысячами свойств значительно влияет на производительность.  Это влияние можно минимизировать путем деления одного объекта на несколько объектов [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с меньшим количеством свойств.  В таблице показана привязка и время отрисовки при связывании данных с одним большим объектом [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и несколькими небольшими объектами.  
  
|**Привязка данных к 1000 объектов TextBlock**|**Время привязки \(мс\)**|**Время отображения — включает привязку \(мс\)**|  
|---------------------------------------------------|-------------------------------|------------------------------------------------------|  
|К объекту [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с 1 000 свойств|950|1200|  
|К 1 000 объектов [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с одним свойством|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## Привязка к ItemsSource  
 Рассмотрим сценарий, в котором имеется объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601>, содержащий список сотрудников, который требуется отобразить в <xref:System.Windows.Controls.ListBox>.  Чтобы установить соответствие между этими двумя объектами, можно привязать список сотрудников к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListBox>.  Предположим, к группе присоединяется новый сотрудник.  Может показаться, что чтобы вставить этого человека в список связанных значений <xref:System.Windows.Controls.ListBox>, нужно просто добавить его в список сотрудников и ожидать, что это изменение автоматически распознается ядром привязки данных.  Это предположение оказалось бы ложным. В действительности изменения не будут отражаться в <xref:System.Windows.Controls.ListBox> автоматически.  Это происходит потому, что объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> не вызывает автоматически измененное событие коллекции.  Чтобы изменения отражались в <xref:System.Windows.Controls.ListBox>, необходимо повторно создать список сотрудников и присоединить его к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListBox>.  Данное решение оказывает существенное воздействие на производительность.  Каждый раз при присваивании <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListBox> новому объекту <xref:System.Windows.Controls.ListBox> сначала отбрасывает предыдущие элементы, а потом заново создает весь список.  Влияние на производительность усиливается, если <xref:System.Windows.Controls.ListBox> сопоставляется со сложным <xref:System.Windows.DataTemplate>.  
  
 Эффективным решением этой проблемы является преобразование списка сотрудников в <xref:System.Collections.ObjectModel.ObservableCollection%601>.  Объект <xref:System.Collections.ObjectModel.ObservableCollection%601> вызывает уведомление об изменении, которое может получать ядро привязки данных.  Событие добавляет или удаляет элемент из <xref:System.Windows.Controls.ItemsControl> без необходимости восстановления всего списка.  
  
 В нижеприведенной таблице показано время, необходимое для обновления <xref:System.Windows.Controls.ListBox> \(с отключенной виртуализацией пользовательского интерфейса\) при добавлении элемента.  Число в первой строке представляет собой затраченное время, когда объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> привязывается к <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента <xref:System.Windows.Controls.ListBox>.  Число во второй строке представляет собой затраченное время, когда <xref:System.Collections.ObjectModel.ObservableCollection%601> привязывается к <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента <xref:System.Windows.Controls.ListBox>.  Обратите внимание на экономию времени, полученную от использования стратегии привязки данных <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
|**Привязка данных к ItemsSource**|**Время обновления для 1 элемента \(мс\)**|  
|---------------------------------------|------------------------------------------------|  
|К объекту <xref:System.Collections.Generic.List%601> в [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].|1656|  
|К <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## Связывание IList с ItemsControl не является IEnumerable  
 Если имеется выбор между привязкой <xref:System.Collections.Generic.IList%601> или <xref:System.Collections.IEnumerable> к объекту <xref:System.Windows.Controls.ItemsControl>, следует выбрать объект <xref:System.Collections.Generic.IList%601>.  Привязка <xref:System.Collections.IEnumerable> к <xref:System.Windows.Controls.ItemsControl> приводит к тому, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создает обертку объекта <xref:System.Collections.Generic.IList%601>, что означает ненужную нагрузку на производительность от второго объекта.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## Не следует преобразовывать объекты среды CLR в XML только для связывания данных.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет связать данные с содержимым [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]. Привязка к содержимому [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] выполняется медленнее, чем привязка данных к объектам [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Не следует преобразовывать данные объекта [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] в XML только для связывания данных.  
  
## См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Пошаговое руководство. Кэширование данных приложения WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)