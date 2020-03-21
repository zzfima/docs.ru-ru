---
title: 'Оптимизация производительности: поведение объекта'
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
ms.openlocfilehash: 67184db7fc1459e83ac7b1e6ff09ef56e43f0ca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187079"
---
# <a name="optimizing-performance-object-behavior"></a>Оптимизация производительности: поведение объекта
Понимание внутреннего поведения объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поможет найти оптимальное сочетание функциональных возможностей и производительности.  

<a name="Not_Removing_Event_Handlers"></a>
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>Не удаление обработчиков событий для объектов может поддерживать объекты в активном состоянии  
 Делегат, который объект передает в свое событие, фактически является ссылкой на этот объект. Таким образом, обработчики событий могут поддерживать объекты в активном состоянии дольше, чем планировалось. При выполнении очистки объекта, зарегистрированного для прослушивания события объекта, необходимо удалить этот делегат перед освобождением объекта. Сохранение ненужных объектов в активном состоянии увеличивает потребление памяти. Это особенно важно в тех случаях, когда объект является корневым элементом логического дерева или визуального дерева.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет шаблон прослушивателя слабых событий, который может быть полезен в ситуациях, когда трудно отслеживать отношения между источником и прослушивателем во время существования объекта. Некоторые существующие события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют этот шаблон. При реализации объектов с пользовательскими событиями этот шаблон может вам пригодиться. Дополнительные сведения см. в разделе [Шаблоны слабых событий](weak-event-patterns.md).  
  
 Существует несколько инструментов, таких как профилировщик CLR и Working Set Viewer, которые могут предоставлять сведения об использовании памяти указанным процессом. Профилировщик CLR включает ряд очень полезных представлений профиля выделения, включая гистограмму выделенных типов, диаграммы выделения и вызова, временную шкалу, показывающую сборку мусора разных поколений и итоговое состояние управляемой кучи после этих сборок, а также дерево вызовов, показывающее распределения по методам и загрузки сборок. Дополнительные сведения см. в разделе [Производительность](https://docs.microsoft.com/previous-versions/aa497289(v=msdn.10)).  
  
<a name="DPs_and_Objects"></a>
## <a name="dependency-properties-and-objects"></a>Свойства и объекты зависимостей  
 Как правило, доступ к свойству <xref:System.Windows.DependencyObject> зависимости не медленнее, чем доступ к свойству CLR. В то время как есть небольшие накладные расходы производительности для установки значения свойства, получение значения так же быстро, как получение значения от свойства CLR. Издержки производительности компенсируются за счет того, что свойства зависимостей поддерживают надежные функции, такие как привязка данных, анимация, наследование и задание стилей. Дополнительные сведения см. в [обзоре свойств зависимостей](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Оптимизация DependencyProperty  
 Свойства зависимостей в приложении следует определять очень внимательно. Если <xref:System.Windows.DependencyProperty> влияет только на параметры метаданных типа, а не <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>на другие параметры метаданных, такие как, вы должны пометить его как таковой, переопределив его метаданные. Дополнительные сведения о переопределении или получении метаданных свойства см. в разделе [Метаданные свойств зависимостей](dependency-property-metadata.md).  
  
 Возможно, более рационально использовать обработчик изменений свойств, чтобы аннулировать передачу размера, упорядочения и отображения вручную, если не все изменения свойств фактически влияют на размер, упорядочение и отображение. Например, вы можете решить заново отображать фон, только когда значение выше установленного ограничения. В этом случае обработчик изменений свойств будет аннулировать отображение, только когда значение превышает установленное ограничение.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Наследуемость DependencyProperty не обходится даром  
 По умолчанию зарегистрированные свойства зависимостей не являются наследуемыми. Тем не менее, вы можете явно сделать любое свойство наследуемым. Хотя это полезная возможность, преобразование свойства в наследуемое негативно влияет на производительность, увеличивая интервал времени для аннулирования свойства.  
  
### <a name="use-registerclasshandler-carefully"></a>Используйте RegisterClassHandler с осторожностью  
 В <xref:System.Windows.EventManager.RegisterClassHandler%2A> то время как вызов позволяет сохранить состояние экземпляра, важно знать, что обработчик вызывается на каждом экземпляре, что может вызвать проблемы с производительностью. Используйте <xref:System.Windows.EventManager.RegisterClassHandler%2A> только тогда, когда приложение требует сохранения состояния экземпляра.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Установка значения по умолчанию для DependencyProperty во время регистрации  
 При создании <xref:System.Windows.DependencyProperty> значения по умолчанию установите значение с использованием метаданных <xref:System.Windows.DependencyProperty.Register%2A> по <xref:System.Windows.DependencyProperty>умолчанию, передаваемых в качестве параметра методу . Рекомендуется использовать именно этот метод вместо настройки значения свойства в конструкторе или в каждом экземпляре элемента.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Установка значения PropertyMetadata с помощью реестра  
 При <xref:System.Windows.DependencyProperty>создании, у вас есть <xref:System.Windows.PropertyMetadata> возможность настройки использования либо <xref:System.Windows.DependencyProperty.Register%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> методы. Хотя ваш объект может иметь статический конструктор для вызова, <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>это не является оптимальным решением и повлияет на производительность. Для лучшей производительности <xref:System.Windows.PropertyMetadata> установите <xref:System.Windows.DependencyProperty.Register%2A>во время вызова.  
  
<a name="Freezable_Objects"></a>
## <a name="freezable-objects"></a>Объекты Freezable  
 A <xref:System.Windows.Freezable> — это особый тип объекта, который имеет два состояния: размороженные и замороженные. Фиксация объектов везде, где это возможно, улучшает производительность приложения и уменьшает его рабочий набор. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](freezable-objects-overview.md).  
  
 Каждый из них <xref:System.Windows.Freezable> имеет <xref:System.Windows.Freezable.Changed> событие, которое возникает всякий раз, когда оно изменяется. Однако уведомления об изменениях обходятся дорого с точки зрения производительности приложения.  
  
 Рассмотрим следующий пример, в котором каждый использует один <xref:System.Windows.Shapes.Rectangle> и тот же <xref:System.Windows.Media.Brush> объект:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 По [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] умолчанию предоставляет обработчик события для <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Freezable.Changed> события объекта, <xref:System.Windows.Shapes.Rectangle> чтобы <xref:System.Windows.Shapes.Shape.Fill%2A> аннулировать свойство объекта. В этом случае каждый раз, когда <xref:System.Windows.Media.SolidColorBrush> он должен запустить свое <xref:System.Windows.Freezable.Changed> событие, <xref:System.Windows.Shapes.Rectangle>он обязан вызвать функцию обратного вызова для каждого - накопление этих вызовов функции обратного вызова налагает значительный штраф производительности. Кроме того, довольно затратно с точки зрения производительности добавлять и удалять обработчики на этом этапе, так как приложению потребуется пройти по всему списку, чтобы сделать это. Если сценарий приложения <xref:System.Windows.Media.SolidColorBrush>никогда не изменяется, <xref:System.Windows.Freezable.Changed> вы будете оплачивать расходы на обслуживание обработчиков событий необоснованно.  
  
 Замораживание <xref:System.Windows.Freezable> может улучшить его производительность, поскольку ему больше не нужно изысклучать ресурсы на поддержание уведомлений об изменениях. В таблице ниже показан размер <xref:System.Windows.Media.SolidColorBrush> простого, когда его <xref:System.Windows.Freezable.IsFrozen%2A> свойство установлено на, `true`по сравнению с когда это не так. Это предполагает применение одной кисти к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> десяти <xref:System.Windows.Shapes.Rectangle> объектов.  
  
|**Состояние**|**Размер**|  
|---------------|--------------|  
|Замороженные<xref:System.Windows.Media.SolidColorBrush>|212 байт|  
|Незамороженные<xref:System.Windows.Media.SolidColorBrush>|972 байта|  
  
 Следующий пример кода демонстрирует эту концепцию.  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Обработчики событий изменений Changed в нефиксированных объектах Freezable могут поддерживать объекты в активном состоянии  
 Делегат, который объект передает <xref:System.Windows.Freezable> сяруху к событию <xref:System.Windows.Freezable.Changed> объекта, фактически является ссылкой на этот объект. Таким <xref:System.Windows.Freezable.Changed> образом, обработчики событий могут сохранять жизнь объектов дольше, чем ожидалось. При выполнении очистки объекта, зарегистрированного <xref:System.Windows.Freezable> для прослушивания <xref:System.Windows.Freezable.Changed> события объекта, необходимо удалить делегата перед выпуском объекта.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также подключает <xref:System.Windows.Freezable.Changed> события внутренне. Например, все свойства зависимости, которые принимаются <xref:System.Windows.Freezable> в качестве значения, будут автоматически слушать <xref:System.Windows.Freezable.Changed> события. Свойство, <xref:System.Windows.Shapes.Shape.Fill%2A> которое <xref:System.Windows.Media.Brush>принимает, иллюстрирует эту концепцию.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 При назначении `myBrush` `myRectangle.Fill`к, делегат, указывающий <xref:System.Windows.Shapes.Rectangle> на объект, <xref:System.Windows.Media.SolidColorBrush> будет <xref:System.Windows.Freezable.Changed> добавлен к событию объекта. Это означает, что следующий код в действительности не разрешает `myRect` сборку мусора.  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 В этом `myBrush` случае `myRectangle` все еще остается в живых <xref:System.Windows.Freezable.Changed> и будет перезвонить ему, когда он запускает свое событие. Обратите внимание, `myBrush` что <xref:System.Windows.Shapes.Shape.Fill%2A> назначение в <xref:System.Windows.Shapes.Rectangle> свойство нового просто `myBrush`добавит еще один обработчик событий.  
  
 Рекомендуемый способ очистки этих типов объектов <xref:System.Windows.Media.Brush> заключается в удалении из <xref:System.Windows.Shapes.Shape.Fill%2A> свойства, что, в свою очередь, удалит обработчик <xref:System.Windows.Freezable.Changed> событий.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>
## <a name="user-interface-virtualization"></a>Виртуализация пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также обеспечивает вариацию <xref:System.Windows.Controls.StackPanel> элемента, который автоматически "виртуализирует" содержимое ребенка, привязанное к данным. В данном контексте слово «виртуализация» означает способ, с помощью которого подмножество объектов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel>(через функциональность, <xref:System.Windows.Controls.VirtualizingPanel>предоставляемую ) вычисляет видимые <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> <xref:System.Windows.Controls.ItemsControl> (например, или ) только создавать элементы для видимых элементов.  
  
 Для оптимизации производительности визуальные объекты для этих элементов создаются или поддерживаются в активном состоянии, только если они будут отображаться на экране. Если они больше не находятся в видимой области элемента управления, визуальные объекты могут быть удалены. Это не следует путать с виртуализацией данных, где не все объекты данных присутствуют в локальной коллекции, а скорее, передаются в потоке при необходимости.  
  
 В приведенной ниже таблице показано прошедшее время добавления и визуализации 5000 <xref:System.Windows.Controls.TextBlock> элементов <xref:System.Windows.Controls.StackPanel> в . <xref:System.Windows.Controls.VirtualizingStackPanel> В этом сценарии измерения представляют время между прикреплением <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> строки <xref:System.Windows.Controls.ItemsControl> текста к свойству объекта к времени, когда элементы панели отображают строку текста.  
  
|**Главная панель**|**Время отрисовки (мс)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>См. также раздел

- [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md)
- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Ресурсы приложения](optimizing-performance-application-resources.md)
- [Текст](optimizing-performance-text.md)
- [Связывание данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
