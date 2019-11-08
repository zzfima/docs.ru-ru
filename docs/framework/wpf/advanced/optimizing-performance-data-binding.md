---
title: 'Оптимизация производительности: привязка данных'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 9b302be3ed9f01ccd27470063f49966dc7d74708
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740794"
---
# <a name="optimizing-performance-data-binding"></a>Оптимизация производительности: привязка данных
Привязка данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет приложениям простой и последовательный способ представления данных и взаимодействия с ними. Элементы могут быть привязаны к данным из различных источников данных в виде объектов CLR и XML.  
  
 В этом разделе даются рекомендации по повышению производительности привязки данных.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Как разрешаются ссылки для привязки данных  
 Прежде чем обсуждать вопросы производительности привязки данных, стоит изучить, как механизм привязки данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разрешает ссылки на объекты для привязки.  
  
 Источником [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] привязки данных может быть любой объект CLR. Можно выполнить привязку к свойствам, вложенным свойствам или индексаторам объекта CLR. Ссылки привязки разрешаются с помощью Microsoft .NET отражения платформы или <xref:System.ComponentModel.ICustomTypeDescriptor>. Ниже приведены три метода для разрешения ссылок на объекты для привязки.  
  
 Первый метод включает использование отражения. В этом случае объект <xref:System.Reflection.PropertyInfo> используется для обнаружения атрибутов свойства и предоставляет доступ к метаданным свойств. При использовании интерфейса <xref:System.ComponentModel.ICustomTypeDescriptor> механизм привязки данных использует этот интерфейс для доступа к значениям свойств. Интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor> особенно полезен в случаях, когда объект не имеет статического набора свойств.  
  
 Уведомления об изменении свойств можно предоставить либо путем реализации интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>, либо с помощью уведомлений об изменениях, связанных с <xref:System.ComponentModel.TypeDescriptor>. Однако предпочтительной стратегией для реализации уведомлений об изменении свойств является использование <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Если исходный объект является объектом CLR, а свойство Source является свойством CLR, то обработчик привязки данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] должен сначала использовать отражение для исходного объекта, чтобы получить <xref:System.ComponentModel.TypeDescriptor>, а затем запросить <xref:System.ComponentModel.PropertyDescriptor>. Эта последовательность операций отражения может занимать очень много времени с точки зрения производительности.  
  
 Второй метод для разрешения ссылок на объекты включает исходный объект CLR, реализующий интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, и свойство Source, которое является свойством CLR. В этом случае механизм привязки данных использует отражение непосредственно в исходном типе и возвращает необходимое свойство. Это по-прежнему не самый оптимальный метод, но он предъявляет меньше требований к рабочему набору, чем первый метод.  
  
 Третий метод разрешения ссылок на объекты включает исходный объект, который является <xref:System.Windows.DependencyObject>, и исходным свойством <xref:System.Windows.DependencyProperty>. В этом случае механизму привязки данных не нужно использовать отражение. Вместо этого механизм свойства и механизм привязки данных оба разрешают ссылку на свойство независимо. Это оптимальный метод для разрешения ссылок на объекты, используемые для привязки данных.  
  
 В следующей таблице сравнивается скорость привязки данных 1000 свойства <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> элементов с помощью этих трех методов.  
  
|**Привязка свойства Text объекта TextBlock**|**Время привязки (мс)**|**Время отрисовки — включает привязку (мс)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|К свойству объекта CLR|115|314|  
|К свойству объекта CLR, реализующего <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|<xref:System.Windows.DependencyProperty> <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Привязка к большим объектам среды CLR  
 При привязке данных к одному объекту CLR с тысячами свойств возникает значительное влияние на производительность. Это влияние можно уменьшить, разделив один объект на несколько объектов CLR с меньшим числом свойств. В таблице показана привязка и время отрисовки для привязки данных к одному крупному объекту CLR по сравнению с несколькими объектами меньшего размера.  
  
|**Привязка данных 1000 объектов TextBlock**|**Время привязки (мс)**|**Время отрисовки — включает привязку (мс)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|К объекту CLR с 1000 свойствами|950|1200|  
|Для 1000 объектов CLR с одним свойством|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Привязка к ItemsSource  
 Рассмотрим ситуацию, в которой имеется объект CLR <xref:System.Collections.Generic.List%601>, содержащий список сотрудников, которые должны отображаться в <xref:System.Windows.Controls.ListBox>. Чтобы создать соответствие между этими двумя объектами, необходимо привязать список сотрудников к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>. Предположим, что к группе присоединяется новый сотрудник. Вы можете подумать, что для вставки нового человека в привязанные <xref:System.Windows.Controls.ListBox> значения можно просто добавить этого пользователя в список сотрудников и ожидать, что это изменение будет автоматически распознано механизмом привязки данных. Это предположение было бы ложным. в действительности изменения не будут автоматически отражаться в <xref:System.Windows.Controls.ListBox>. Это происходит потому, что объект CLR <xref:System.Collections.Generic.List%601> не создает автоматически событие изменения коллекции. Чтобы получить <xref:System.Windows.Controls.ListBox> для получения изменений, необходимо заново создать список сотрудников и повторно присоединить его к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>. Хотя это решение работает, оно серьезно влияет на производительность. Каждый раз, когда вы переназначаете <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> новому объекту, <xref:System.Windows.Controls.ListBox> сначала выдает его предыдущие элементы и повторно создает весь список. Влияние на производительность будет увеличено, если <xref:System.Windows.Controls.ListBox> сопоставляется со сложным <xref:System.Windows.DataTemplate>.  
  
 Очень эффективным решением этой проблемы является предоставление списка сотрудников <xref:System.Collections.ObjectModel.ObservableCollection%601>. Объект <xref:System.Collections.ObjectModel.ObservableCollection%601> вызывает уведомление об изменении, которое может получить механизм привязки данных. Событие добавляет или удаляет элемент из <xref:System.Windows.Controls.ItemsControl> без необходимости повторно создавать весь список.  
  
 В таблице ниже показано время, необходимое для обновления <xref:System.Windows.Controls.ListBox> (с отключенной виртуализацией пользовательского интерфейса) при добавлении одного элемента. Число в первой строке представляет прошедшее время, когда объект CLR <xref:System.Collections.Generic.List%601> привязан к <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>элемента <xref:System.Windows.Controls.ListBox>. Число во второй строке представляет время, затраченное на привязку <xref:System.Collections.ObjectModel.ObservableCollection%601> к <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>у элемента <xref:System.Windows.Controls.ListBox>. Обратите внимание на значительную экономию времени, используя стратегию привязки данных <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
|**Привязка данных ItemsSource**|**Время обновления для 1 элемента (мс)**|  
|--------------------------------------|---------------------------------------|  
|В объект <xref:System.Collections.Generic.List%601> среды CLR|1656|  
|В <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Привязка IList к ItemsControl не IEnumerable  
 Если имеется выбор между привязкой <xref:System.Collections.Generic.IList%601> или <xref:System.Collections.IEnumerable> к <xref:System.Windows.Controls.ItemsControl> объекту, выберите объект <xref:System.Collections.Generic.IList%601>. Привязка <xref:System.Collections.IEnumerable> к <xref:System.Windows.Controls.ItemsControl> заставляет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создать объект <xref:System.Collections.Generic.IList%601>-оболочки, что означает, что производительность повлияла на ненужные издержки второго объекта.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Не преобразовывайте объекты среды CLR в XML только для привязки данных.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет привязывать данные к XML-содержимому; Однако привязка данных к XML-содержимому выполняется медленнее, чем привязка данных к объектам CLR. Не преобразуйте данные объекта CLR в XML, если единственной целью является привязка данных.  
  
## <a name="see-also"></a>См. также

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Текст](optimizing-performance-text.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Пошаговое руководство. Кэширование данных приложения WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
