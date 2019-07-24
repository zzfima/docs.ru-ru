---
title: 'Оптимизация производительности: Поведение объекта'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 025c8691eb1aaf9483a222530a5590670ede486b
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400464"
---
# <a name="optimizing-performance-object-behavior"></a>Оптимизация производительности: Поведение объекта
Понимание внутреннего поведения объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поможет найти оптимальное сочетание функциональных возможностей и производительности.  

<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>Не удаление обработчиков событий для объектов может поддерживать объекты в активном состоянии  
 Делегат, который объект передает в свое событие, фактически является ссылкой на этот объект. Таким образом, обработчики событий могут поддерживать объекты в активном состоянии дольше, чем планировалось. При выполнении очистки объекта, зарегистрированного для прослушивания события объекта, необходимо удалить этот делегат перед освобождением объекта. Сохранение ненужных объектов в активном состоянии увеличивает потребление памяти. Это особенно важно в тех случаях, когда объект является корневым элементом логического дерева или визуального дерева.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет шаблон прослушивателя слабых событий, который может быть полезен в ситуациях, когда трудно отслеживать отношения между источником и прослушивателем во время существования объекта. Некоторые существующие события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют этот шаблон. При реализации объектов с пользовательскими событиями этот шаблон может вам пригодиться. Дополнительные сведения см. в разделе [Шаблоны слабых событий](weak-event-patterns.md).  
  
 Существует несколько инструментов, таких как профилировщик CLR и Working Set Viewer, которые могут предоставлять сведения об использовании памяти указанным процессом. Профилировщик CLR включает ряд очень полезных представлений профиля выделения, включая гистограмму выделенных типов, диаграммы выделения и вызова, временную шкалу, показывающую сборку мусора разных поколений и итоговое состояние управляемой кучи после этих сборок, а также дерево вызовов, показывающее распределения по методам и загрузки сборок. Дополнительные сведения см. в разделе [Центр разработчиков .NET Framework](https://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Свойства и объекты зависимостей  
 Как правило, доступ к свойству зависимостей объекта <xref:System.Windows.DependencyObject> не медленнее доступа к свойству CLR. Несмотря на небольшое снижение производительности для установки значения свойства, получение значения выполняется так же быстро, как получение значения из свойства CLR. Издержки производительности компенсируются за счет того, что свойства зависимостей поддерживают надежные функции, такие как привязка данных, анимация, наследование и задание стилей. Дополнительные сведения см. в [обзоре свойств зависимостей](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Оптимизация DependencyProperty  
 Свойства зависимостей в приложении следует определять очень внимательно. Если параметр <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>влияет только на параметры метаданных типа прорисовки, а не на другие параметры метаданных, такие как, следует пометить его, переопределив его метаданные. <xref:System.Windows.DependencyProperty> Дополнительные сведения о переопределении и получении метаданных свойства см. в разделе [Метаданные свойств зависимостей](dependency-property-metadata.md).  
  
 Возможно, более рационально использовать обработчик изменений свойств, чтобы аннулировать передачу размера, упорядочения и отображения вручную, если не все изменения свойств фактически влияют на размер, упорядочение и отображение. Например, вы можете решить заново отображать фон, только когда значение выше установленного ограничения. В этом случае обработчик изменений свойств будет аннулировать отображение, только когда значение превышает установленное ограничение.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Наследуемость DependencyProperty не обходится даром  
 По умолчанию зарегистрированные свойства зависимостей не являются наследуемыми. Однако можно явно сделать любое свойство наследуемым. Хотя это полезная возможность, преобразование свойства в наследуемое негативно влияет на производительность, увеличивая интервал времени для аннулирования свойства.  
  
### <a name="use-registerclasshandler-carefully"></a>Используйте RegisterClassHandler с осторожностью  
 Хотя вызов <xref:System.Windows.EventManager.RegisterClassHandler%2A> позволяет сохранить состояние экземпляра, важно помнить, что обработчик вызывается на каждом экземпляре, что может вызвать проблемы с производительностью. Используйте <xref:System.Windows.EventManager.RegisterClassHandler%2A> , только если приложению требуется сохранить состояние экземпляра.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Установка значения по умолчанию для DependencyProperty во время регистрации  
 При создании <xref:System.Windows.DependencyProperty> , для которого требуется значение по умолчанию, задайте значение с помощью метаданных по умолчанию, передаваемых <xref:System.Windows.DependencyProperty.Register%2A> в качестве параметра <xref:System.Windows.DependencyProperty>методу компонента. Рекомендуется использовать именно этот метод вместо настройки значения свойства в конструкторе или в каждом экземпляре элемента.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Установка значения PropertyMetadata с помощью реестра  
 При создании <xref:System.Windows.DependencyProperty>можно <xref:System.Windows.PropertyMetadata> выбрать параметр с помощью <xref:System.Windows.DependencyProperty.Register%2A> методов или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> . Несмотря на то, что объект может иметь статический конструктор <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>для вызова, это не оптимальное решение, которое влияет на производительность. Для лучшей производительности установите <xref:System.Windows.PropertyMetadata> во время <xref:System.Windows.DependencyProperty.Register%2A>вызова.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Объекты Freezable  
 <xref:System.Windows.Freezable> — Это особый тип объекта с двумя состояниями: незамороженный и замороженный. Фиксация объектов везде, где это возможно, улучшает производительность приложения и уменьшает его рабочий набор. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](freezable-objects-overview.md).  
  
 Каждый <xref:System.Windows.Freezable> из<xref:System.Windows.Freezable.Changed> них имеет событие, которое возникает при каждом изменении. Однако уведомления об изменениях обходятся дорого с точки зрения производительности приложения.  
  
 Рассмотрим следующий пример, в котором каждый <xref:System.Windows.Shapes.Rectangle> использует один и <xref:System.Windows.Media.Brush> тот же объект:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет обработчик событий <xref:System.Windows.Media.SolidColorBrush> для <xref:System.Windows.Freezable.Changed> события объекта, чтобы сделать недействительным <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Shapes.Shape.Fill%2A> свойство объекта. В этом случае каждый раз <xref:System.Windows.Media.SolidColorBrush> , когда должен <xref:System.Windows.Freezable.Changed> срабатывать событие, необходимо вызвать функцию обратного вызова для каждой <xref:System.Windows.Shapes.Rectangle>из них — накопление вызовов функций обратного вызова приводит к значительному снижению производительности. Кроме того, довольно затратно с точки зрения производительности добавлять и удалять обработчики на этом этапе, так как приложению потребуется пройти по всему списку, чтобы сделать это. Если сценарий приложения никогда не изменит <xref:System.Windows.Media.SolidColorBrush>, вы будете платить за обслуживание <xref:System.Windows.Freezable.Changed> обработчиков событий без необходимости.  
  
 Замораживание <xref:System.Windows.Freezable> может повысить свою производительность, так как больше не требуется тратить ресурсы на обслуживание уведомлений об изменениях. В таблице ниже показан размер простого <xref:System.Windows.Media.SolidColorBrush> `true`, если его <xref:System.Windows.Freezable.IsFrozen%2A> свойство имеет значение, по сравнению с, если это не так. Это предполагает применение одной кисти к <xref:System.Windows.Shapes.Shape.Fill%2A> свойству десяти <xref:System.Windows.Shapes.Rectangle> объектов.  
  
|**Состояние**|**Size**|  
|---------------|--------------|  
|Крепление<xref:System.Windows.Media.SolidColorBrush>|212 байт|  
|Не заморожено<xref:System.Windows.Media.SolidColorBrush>|972 байта|  
  
 Следующий пример кода демонстрирует эту концепцию.  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Обработчики событий изменений Changed в нефиксированных объектах Freezable могут поддерживать объекты в активном состоянии  
 Делегат, который объект передает в <xref:System.Windows.Freezable> <xref:System.Windows.Freezable.Changed> событие объекта, фактически является ссылкой на этот объект. Таким образом <xref:System.Windows.Freezable.Changed> , обработчики событий могут поддерживать активность объектов дольше, чем ожидалось. При выполнении очистки объекта, зарегистрированного для прослушивания <xref:System.Windows.Freezable> <xref:System.Windows.Freezable.Changed> события объекта, важно удалить этот делегат перед освобождением объекта.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также подключает <xref:System.Windows.Freezable.Changed> события внутренним образом. Например, все свойства зависимостей, которые принимают <xref:System.Windows.Freezable> в качестве значения, будут автоматически <xref:System.Windows.Freezable.Changed> прослушивать события. Свойство, которое <xref:System.Windows.Media.Brush>принимает, иллюстрирует эту концепцию. <xref:System.Windows.Shapes.Shape.Fill%2A>  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 При `myBrush` `myRectangle.Fill`назначении объекту<xref:System.Windows.Shapes.Rectangle>делегат , указывающий обратно на объект, будет добавлен в <xref:System.Windows.Media.SolidColorBrush> событиеобъекта.<xref:System.Windows.Freezable.Changed> Это означает, что следующий код в действительности не разрешает `myRect` сборку мусора.  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 В этом случае `myBrush` `myRectangle` продолжает существовать активность и при срабатывании <xref:System.Windows.Freezable.Changed> события вызывает обратную связь. Обратите внимание `myBrush` , что <xref:System.Windows.Shapes.Shape.Fill%2A> назначение свойству нового <xref:System.Windows.Shapes.Rectangle> объекта приведет к простому добавлению `myBrush`еще одного обработчика событий в.  
  
 Для очистки этих типов объектов рекомендуется удалить <xref:System.Windows.Media.Brush> <xref:System.Windows.Shapes.Shape.Fill%2A> из свойства, которое, в свою очередь <xref:System.Windows.Freezable.Changed> , удалит обработчик событий.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Виртуализация пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также предоставляет вариант <xref:System.Windows.Controls.StackPanel> элемента, который автоматически «виртуализировать» дочернее содержимое с привязкой к данным. В данном контексте слово «виртуализация» означает способ, с помощью которого подмножество объектов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel>(с помощью функций, <xref:System.Windows.Controls.VirtualizingPanel>предоставляемых) вычисляет видимые элементы и работает <xref:System.Windows.Controls.ItemContainerGenerator> с объектом <xref:System.Windows.Controls.ItemsControl> from (например <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.ListView>или), чтобы создавать элементы только для видимых элементов.  
  
 Для оптимизации производительности визуальные объекты для этих элементов создаются или поддерживаются в активном состоянии, только если они будут отображаться на экране. Если они больше не находятся в видимой области элемента управления, визуальные объекты могут быть удалены. Это не следует путать с виртуализацией данных, где не все объекты данных присутствуют в локальной коллекции, а скорее, передаются в потоке при необходимости.  
  
 В таблице ниже показано время, затраченное на добавление и отрисовку элементов <xref:System.Windows.Controls.TextBlock> 5000 <xref:System.Windows.Controls.StackPanel> в и <xref:System.Windows.Controls.VirtualizingStackPanel>. В этом сценарии измерения представляют время между присоединением текстовой строки к <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойству <xref:System.Windows.Controls.ItemsControl> объекта до момента отображения текстовой строки в элементах панели.  
  
|**Главная панель**|**Время отрисовки (мс)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>См. также

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
