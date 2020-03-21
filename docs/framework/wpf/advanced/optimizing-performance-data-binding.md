---
title: 'Оптимизация производительности: привязка данных'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186757"
---
# <a name="optimizing-performance-data-binding"></a>Оптимизация производительности: привязка данных
Привязка данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет приложениям простой и последовательный способ представления данных и взаимодействия с ними. Элементы могут быть привязаны к данным из различных источников данных в виде объектов CLR и XML.  
  
 В этом разделе даются рекомендации по повышению производительности привязки данных.  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>Как разрешаются ссылки для привязки данных  
 Прежде чем обсуждать вопросы производительности привязки данных, стоит изучить, как механизм привязки данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] разрешает ссылки на объекты для привязки.  
  
 Источником связывания [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] данных может быть любой объект CLR. Можно связываться с свойствами, субсвойствами или индексаторами объекта CLR. Обязательные ссылки решаются с помощью либо <xref:System.ComponentModel.ICustomTypeDescriptor>отражения Microsoft .NET Framework, либо . Ниже приведены три метода для разрешения ссылок на объекты для привязки.  
  
 Первый метод включает использование отражения. В этом случае <xref:System.Reflection.PropertyInfo> объект используется для обнаружения атрибутов свойства и обеспечивает доступ к метаданным свойств. При использовании интерфейса <xref:System.ComponentModel.ICustomTypeDescriptor> движок связывания данных использует этот интерфейс для доступа к значениям свойств. Интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor> особенно полезен в тех случаях, когда объект не имеет статического набора свойств.  
  
 Уведомления об изменении свойств могут быть <xref:System.ComponentModel.INotifyPropertyChanged> предоставлены либо путем реализации <xref:System.ComponentModel.TypeDescriptor>интерфейса, либо с помощью уведомлений об изменении, связанных с . Однако предпочтительной стратегией для реализации уведомлений об изменении свойств является использование. <xref:System.ComponentModel.INotifyPropertyChanged>  
  
 Если исходный объект является объектом CLR, а исходное свойство свойством CLR свойство, движок связывания [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] данных должен сначала использовать отражение на исходном <xref:System.ComponentModel.TypeDescriptor>объекте, чтобы получить, а затем запрос на <xref:System.ComponentModel.PropertyDescriptor>. Эта последовательность операций отражения может занимать очень много времени с точки зрения производительности.  
  
 Второй метод решения ссылок объектов включает в себя исходный объект CLR, который реализует <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс, и свойство источника, которое является свойством CLR. В этом случае механизм привязки данных использует отражение непосредственно в исходном типе и возвращает необходимое свойство. Это по-прежнему не самый оптимальный метод, но он предъявляет меньше требований к рабочему набору, чем первый метод.  
  
 Третий метод для решения ссылок объектов включает <xref:System.Windows.DependencyObject> исходный объект, <xref:System.Windows.DependencyProperty>который является свойством источника, и свойством источника, который является . В этом случае механизму привязки данных не нужно использовать отражение. Вместо этого механизм свойства и механизм привязки данных оба разрешают ссылку на свойство независимо. Это оптимальный метод для разрешения ссылок на объекты, используемые для привязки данных.  
  
 В таблице ниже сравнивается скорость <xref:System.Windows.Controls.TextBlock.Text%2A> передачи данных в свойство тысячи <xref:System.Windows.Controls.TextBlock> элементов с использованием этих трех методов.  
  
|**Привязка свойства Text объекта TextBlock**|**Время привязки (мс)**|**Время отрисовки — включает привязку (мс)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|К свойству объекта CLR|115|314|  
|К свойству объекта CLR, который реализует<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|<xref:System.Windows.DependencyProperty> К <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>Привязка к большим объектам среды CLR  
 При связывании данных с одним объектом CLR с тысячами свойств наблюдается значительное влияние на производительность. Это воздействие можно свести к минимуму, разделив один объект на несколько объектов CLR с меньшим количеством свойств. В таблице отображается время связывания и визуализации для привязки данных к одному крупному объекту CLR по сравнению с несколькими более мелкими объектами.  
  
|**Привязка данных 1000 объектов TextBlock**|**Время привязки (мс)**|**Время отрисовки — включает привязку (мс)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|Объекту CLR со 1000 свойствами|950|1200|  
|До 1000 объектов CLR с одним свойством|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>Привязка к ItemsSource  
 Рассмотрим сценарий, в котором <xref:System.Collections.Generic.List%601> у вас есть объект CLR, который <xref:System.Windows.Controls.ListBox>содержит список сотрудников, которые вы хотите отобразить в. Чтобы создать корреспонденцию между этими <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> двумя объектами, вы привязываете список сотрудников к свойству <xref:System.Windows.Controls.ListBox>. Предположим, что к группе присоединяется новый сотрудник. Вы можете подумать, что для того, <xref:System.Windows.Controls.ListBox> чтобы вставить этого нового человека в связанные значения, вы просто добавите этого человека в список сотрудников и ожидаете, что это изменение будет распознано движком связывания данных автоматически. Это предположение окажется ложным; в действительности, изменение не будет отражено в <xref:System.Windows.Controls.ListBox> автоматически. Это связано с <xref:System.Collections.Generic.List%601> тем, что объект CLR не собирает автоматически измененное событие коллекции. Для того, <xref:System.Windows.Controls.ListBox> чтобы получить, чтобы забрать изменения, вам придется воссоздать список <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> сотрудников <xref:System.Windows.Controls.ListBox>и повторно прикрепить его к свойству . Хотя это решение работает, оно серьезно влияет на производительность. Каждый раз, когда <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> вы переназначаете <xref:System.Windows.Controls.ListBox> новый объект, первый выбрасывает свои предыдущие элементы и регенерирует весь список. Влияние производительности увеличивается, <xref:System.Windows.Controls.ListBox> если ваши <xref:System.Windows.DataTemplate>карты до сложного.  
  
 Очень эффективное решение этой проблемы, чтобы <xref:System.Collections.ObjectModel.ObservableCollection%601>сделать ваш список сотрудников . Объект <xref:System.Collections.ObjectModel.ObservableCollection%601> поднимает уведомление об изменении, которое может получить движок связывания данных. Событие добавляет или удаляет элемент <xref:System.Windows.Controls.ItemsControl> из элемента без необходимости регенерации всего списка.  
  
 В приведенной ниже таблице показано <xref:System.Windows.Controls.ListBox> время, необходимое для обновления (с выключенной виртуализацией uI) при добавлении одного элемента. Число в первом ряду представляет собой прошедшее время, <xref:System.Collections.Generic.List%601> когда объект <xref:System.Windows.Controls.ListBox> CLR <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>привязан к элементу. Номер во втором ряду представляет собой прошедшее <xref:System.Collections.ObjectModel.ObservableCollection%601> время, когда <xref:System.Windows.Controls.ListBox> он <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>привязан к элементу. Обратите внимание на значительную экономию времени, используя стратегию <xref:System.Collections.ObjectModel.ObservableCollection%601> связывания данных.  
  
|**Привязка данных ItemsSource**|**Время обновления для 1 элемента (мс)**|  
|--------------------------------------|---------------------------------------|  
|Объекту CLR <xref:System.Collections.Generic.List%601>|1656|  
|Для<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Привязка IList к ItemsControl не IEnumerable  
 Если у вас есть <xref:System.Collections.Generic.IList%601> выбор <xref:System.Collections.IEnumerable> между <xref:System.Windows.Controls.ItemsControl> привязкой <xref:System.Collections.Generic.IList%601> объекта или объекта, выберите объект. <xref:System.Collections.IEnumerable> Привязка <xref:System.Windows.Controls.ItemsControl> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к силам для <xref:System.Collections.Generic.IList%601> создания объекта обертки, что означает, что на производительность влияет ненужные накладные расходы второго объекта.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Не преобразовывайте объекты среды CLR в XML только для привязки данных.  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]позволяет связывать данные с содержанием XML; однако привязка данных к содержимому XML происходит медленнее, чем привязка данных к объектам CLR. Не преобразовывайте данные объектов CLR в XML, если целью является привязка данных.  
  
## <a name="see-also"></a>См. также раздел

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложения](optimizing-performance-application-resources.md)
- [Текст](optimizing-performance-text.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Пошаговое руководство. Кэширование данных приложения WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
