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
ms.openlocfilehash: 64e567cd28e9458b483b0963e0dedd924ad23bab
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094492"
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
 Как правило, доступ к свойству зависимостей <xref:System.Windows.DependencyObject> не медленнее доступа к свойству CLR. Несмотря на небольшое снижение производительности для установки значения свойства, получение значения выполняется так же быстро, как получение значения из свойства CLR. Издержки производительности компенсируются за счет того, что свойства зависимостей поддерживают надежные функции, такие как привязка данных, анимация, наследование и задание стилей. Дополнительные сведения см. в [обзоре свойств зависимостей](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Оптимизация DependencyProperty  
 Свойства зависимостей в приложении следует определять очень внимательно. Если <xref:System.Windows.DependencyProperty> влияет только на параметры метаданных типа прорисовки, а не на другие параметры метаданных, такие как <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, следует пометить его как таковое, переопределив его метаданные. Дополнительные сведения о переопределении и получении метаданных свойства см. в разделе [Метаданные свойств зависимостей](dependency-property-metadata.md).  
  
 Возможно, более рационально использовать обработчик изменений свойств, чтобы аннулировать передачу размера, упорядочения и отображения вручную, если не все изменения свойств фактически влияют на размер, упорядочение и отображение. Например, вы можете решить заново отображать фон, только когда значение выше установленного ограничения. В этом случае обработчик изменений свойств будет аннулировать отображение, только когда значение превышает установленное ограничение.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Наследуемость DependencyProperty не обходится даром  
 По умолчанию зарегистрированные свойства зависимостей не являются наследуемыми. Однако можно явно сделать любое свойство наследуемым. Хотя это полезная возможность, преобразование свойства в наследуемое негативно влияет на производительность, увеличивая интервал времени для аннулирования свойства.  
  
### <a name="use-registerclasshandler-carefully"></a>Используйте RegisterClassHandler с осторожностью  
 При вызове <xref:System.Windows.EventManager.RegisterClassHandler%2A> позволяет сохранить состояние экземпляра, важно помнить, что обработчик вызывается на каждом экземпляре, что может вызвать проблемы с производительностью. Используйте <xref:System.Windows.EventManager.RegisterClassHandler%2A> только в том случае, если приложению требуется сохранить состояние экземпляра.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Установка значения по умолчанию для DependencyProperty во время регистрации  
 При создании <xref:System.Windows.DependencyProperty>, для которого требуется значение по умолчанию, задайте значение с помощью метаданных по умолчанию, передаваемых в качестве параметра методу <xref:System.Windows.DependencyProperty.Register%2A> <xref:System.Windows.DependencyProperty>. Рекомендуется использовать именно этот метод вместо настройки значения свойства в конструкторе или в каждом экземпляре элемента.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Установка значения PropertyMetadata с помощью реестра  
 При создании <xref:System.Windows.DependencyProperty>можно задать <xref:System.Windows.PropertyMetadata> с помощью методов <xref:System.Windows.DependencyProperty.Register%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Хотя у объекта может быть статический конструктор для вызова <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, это не оптимальное решение, которое влияет на производительность. Для лучшей производительности задайте <xref:System.Windows.PropertyMetadata> во время вызова <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Объекты Freezable  
 <xref:System.Windows.Freezable> — это особый тип объекта с двумя состояниями: незамороженный и замороженный. Фиксация объектов везде, где это возможно, улучшает производительность приложения и уменьшает его рабочий набор. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](freezable-objects-overview.md).  
  
 Каждый <xref:System.Windows.Freezable> имеет событие <xref:System.Windows.Freezable.Changed>, которое возникает при каждом изменении. Однако уведомления об изменениях обходятся дорого с точки зрения производительности приложения.  
  
 Рассмотрим следующий пример, в котором каждый <xref:System.Windows.Shapes.Rectangle> использует один и тот же объект <xref:System.Windows.Media.Brush>:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет обработчик для события <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Media.SolidColorBrush>, чтобы сделать недействительным свойство <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Rectangle>. В этом случае каждый раз, когда <xref:System.Windows.Media.SolidColorBrush> должен запустить свое <xref:System.Windows.Freezable.Changed> событие, необходимо вызвать функцию обратного вызова для каждого <xref:System.Windows.Shapes.Rectangle>— накопление вызовов функций обратного вызова приводит к значительному снижению производительности. Кроме того, довольно затратно с точки зрения производительности добавлять и удалять обработчики на этом этапе, так как приложению потребуется пройти по всему списку, чтобы сделать это. Если сценарий приложения никогда не изменяет <xref:System.Windows.Media.SolidColorBrush>, вы оплачиваете затраты на поддержание <xref:System.Windows.Freezable.Changed> обработчиков событий без необходимости.  
  
 Замораживание <xref:System.Windows.Freezable> может повысить его производительность, так как больше не требуется тратить ресурсы на обслуживание уведомлений об изменениях. В таблице ниже показан размер простого <xref:System.Windows.Media.SolidColorBrush>, если его свойство <xref:System.Windows.Freezable.IsFrozen%2A> имеет значение `true`, по сравнению с, если это не так. Это предполагает применение одной кисти к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> десяти <xref:System.Windows.Shapes.Rectangle> объектов.  
  
|**Состояние**|**Размер**|  
|---------------|--------------|  
|Замороженный <xref:System.Windows.Media.SolidColorBrush>|212 байт|  
|Незамороженная <xref:System.Windows.Media.SolidColorBrush>|972 байта|  
  
 Следующий пример кода демонстрирует эту концепцию.  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Обработчики событий изменений Changed в нефиксированных объектах Freezable могут поддерживать объекты в активном состоянии  
 Делегат, который объект передает в событие <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Freezable>, фактически является ссылкой на этот объект. Таким образом, <xref:System.Windows.Freezable.Changed> обработчики событий могут поддерживать активность объектов дольше, чем ожидалось. При выполнении очистки объекта, зарегистрированного для прослушивания события <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Freezable>, важно удалить этот делегат перед освобождением объекта.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также привязывает события <xref:System.Windows.Freezable.Changed> внутренним образом. Например, все свойства зависимостей, которые принимают <xref:System.Windows.Freezable> в качестве значения, будут автоматически прослушивать <xref:System.Windows.Freezable.Changed> события. Эта концепция показана в свойстве <xref:System.Windows.Shapes.Shape.Fill%2A>, которое принимает <xref:System.Windows.Media.Brush>.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 При назначении `myBrush` `myRectangle.Fill`делегат, указывающий обратно на <xref:System.Windows.Shapes.Rectangle> объект, будет добавлен в событие <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Media.SolidColorBrush>. Это означает, что следующий код в действительности не разрешает `myRect` сборку мусора.  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 В этом случае `myBrush` продолжает поддерживать `myRectangle` в активном состоянии и при срабатывании события <xref:System.Windows.Freezable.Changed> вызовет обратно. Обратите внимание, что при назначении `myBrush` свойству <xref:System.Windows.Shapes.Shape.Fill%2A> нового <xref:System.Windows.Shapes.Rectangle> будет просто добавлен еще один обработчик событий `myBrush`.  
  
 Для очистки этих типов объектов рекомендуется удалить <xref:System.Windows.Media.Brush> из свойства <xref:System.Windows.Shapes.Shape.Fill%2A>, которое, в свою очередь, удалит обработчик событий <xref:System.Windows.Freezable.Changed>.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Виртуализация пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет вариант элемента <xref:System.Windows.Controls.StackPanel>, который автоматически "виртуализировать" дочернее содержимое с привязкой к данным. В данном контексте слово «виртуализация» означает способ, с помощью которого подмножество объектов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том, что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel> (с помощью функций, предоставляемых <xref:System.Windows.Controls.VirtualizingPanel>) вычисляет видимые элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> из <xref:System.Windows.Controls.ItemsControl> (например, <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ListView>), чтобы создавать элементы только для видимых элементов.  
  
 Для оптимизации производительности визуальные объекты для этих элементов создаются или поддерживаются в активном состоянии, только если они будут отображаться на экране. Если они больше не находятся в видимой области элемента управления, визуальные объекты могут быть удалены. Это не следует путать с виртуализацией данных, где не все объекты данных присутствуют в локальной коллекции, а скорее, передаются в потоке при необходимости.  
  
 В таблице ниже показано время, затраченное на добавление и отрисовку элементов 5000 <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.VirtualizingStackPanel>. В этом сценарии измерения представляют время между присоединением текстовой строки к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> объекта <xref:System.Windows.Controls.ItemsControl>, в то время как элементы панели отображают текстовую строку.  
  
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
- [Привязка данных](optimizing-performance-data-binding.md)
- [Дополнительные рекомендации по повышению производительности](optimizing-performance-other-recommendations.md)
