---
title: "Оптимизация производительности: поведение объекта | Microsoft Docs"
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
  - "свойства зависимостей, производительность"
  - "обработчики событий [WPF]"
  - "Freezable - объекты, производительность"
  - "вопросы производительности объектов"
  - "визуализация пользовательского интерфейса"
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Оптимизация производительности: поведение объекта
Понимание внутреннего поведения объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поможет найти оптимальное сочетание функциональных возможностей и производительности.  
  
   
  
<a name="Not_Removing_Event_Handlers"></a>   
## Сохранение обработчиков событий для объектов может поддерживать объекты в активном состоянии  
 Делегат, который объект передает своему событию, является в сущности ссылкой на этот объект.  Поэтому обработчики событий могут поддерживать объекты в активном состоянии дольше, чем обычно.  При выполнении очистки объекта, зарегистрированного для прослушивания события объекта, необходимо удалить этот делегат перед освобождением объекта.  Сохранение ненужных объектов в активном состоянии увеличивает объем используемой приложением памяти.  Это особенно заметно, когда объект является корневым элементом [логического дерева](GTMT) или [визуального дерева](GTMT).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет шаблон прослушивателя событий, который может быть полезен в ситуациях, когда трудно отслеживать отношения между источником и прослушивателем во время существования объекта.  Некоторые существующие события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют этот шаблон.  Этот шаблон можно использовать при реализации объектов с пользовательскими событиями.  Дополнительные сведения см. в разделе [Шаблоны слабых событий](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
 Существует несколько средств, таких как CLR Profiler и Working Set Viewer, которые могут предоставить информацию об использовании памяти указанным процессом.  CLR Profiler включает ряд очень полезных представлений профиля распределения, включая гистограмму выделенных типов, диаграмму выделения памяти и вызовов, шкала времени, показывающая сборку мусора различных поколений, результирующее состояние управляемой кучи после этих сборок и дерево вызовов, показывающее нагрузку на сборку и распределение для каждого метода.  Дополнительные сведения см. в [Центре разработчиков Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## Объекты и свойства зависимостей  
 Как правило, доступ к [свойству зависимостей](GTMT) из <xref:System.Windows.DependencyObject> происходит не медленнее, чем доступ к свойству [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Хотя существуют небольшие издержки производительности при задании значения свойства, получение значения происходит так же быстро, как получение значения из свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Издержки производительности компенсируются за счет того, что [свойства зависимостей](GTMT) поддерживают устойчивые к ошибкам функции, такие как привязка данных, анимация, наследование и стилизация.  Дополнительные сведения см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
### Оптимизация свойств зависимостей  
 [Свойства зависимостей](GTMT) в приложении следует определять очень осторожно.  Если <xref:System.Windows.DependencyProperty> затрагивает только отображение параметров метаданных типа вместо других параметров метаданных, таких как <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, то следует пометить его как таковое путем переопределения его метаданных.  Дополнительные сведения о переопределении или получении метаданных свойства содержатся в разделе [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Возможно, более рационально использовать обработчик изменений свойств для передачи размера, упорядочения и отображения, если в действительности не все изменения свойства влияют на размер, упорядочение и отображение.  Например, можно заново отобразить фон, только если значение больше, чем установленный предел.  В этом случае обработчик изменений свойств только объявил бы отображение недействительным, когда значение превышает установленный предел.  
  
### Создание наследуемого DependencyProperty  
 По умолчанию зарегистрированные [свойства зависимостей](GTMT) являются ненаследуемыми.  Однако можно явным образом сделать любое свойство наследуемым.  Хотя это полезная возможность, преобразование свойства к наследуемому типу влияет на производительность, увеличивая интервал времени для аннулирования свойства.  
  
### Следует осторожно использовать RegisterClassHandler  
 Хотя вызов <xref:System.Windows.EventManager.RegisterClassHandler%2A> позволяет сохранить состояние экземпляра, важно иметь в виду, что обработчик вызывается для каждого экземпляра, что может вызвать снижение производительности.  Используйте <xref:System.Windows.EventManager.RegisterClassHandler%2A>, только если приложению требуется сохранять состояние экземпляра.  
  
### Установка значения по умолчанию для DependencyProperty во время регистрации  
 При создании <xref:System.Windows.DependencyProperty>, требующего значение по умолчанию, задайте значение с помощью метаданных по умолчанию, переданных в качестве параметра методу <xref:System.Windows.DependencyProperty.Register%2A> для <xref:System.Windows.DependencyProperty>.  Следует использовать этот способ вместо задания значения свойства в конструкторе или для каждого экземпляра элемента.  
  
### Задание значения PropertyMetadata с помощью элемента Register  
 При создании <xref:System.Windows.DependencyProperty> имеется возможность задания <xref:System.Windows.PropertyMetadata> с помощью метода <xref:System.Windows.DependencyProperty.Register%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.  Хотя объект может иметь статический конструктор для вызова <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, его использование не является оптимальным решением и повлияет на производительность.  Для достижения наилучшей производительности задайте <xref:System.Windows.PropertyMetadata> во время вызова <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## Объекты Freezable  
 <xref:System.Windows.Freezable> представляет сосбой особый тип объекта, имеющий два состояния: фиксированное и нефиксированное.  Замораживание объектов, когда это доступно, повышает производительность приложения и уменьшает его рабочее множество.  Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Каждый <xref:System.Windows.Freezable> имеет событие <xref:System.Windows.Freezable.Changed>, возникающее при каждом его изменении.  Однако уведомления об изменениях являются дорогостоящими в терминах производительности приложения.  
  
 Рассмотрим следующий пример, в котором каждый <xref:System.Windows.Shapes.Rectangle> использует один и тот же объект <xref:System.Windows.Media.Brush>:  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 По умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет обработчик событий для события <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Media.SolidColorBrush>, делающий недействительным свойство <xref:System.Windows.Shapes.Shape.Fill%2A> объекта <xref:System.Windows.Shapes.Rectangle>.  В этом случае каждый раз, когда <xref:System.Windows.Media.SolidColorBrush> вынуждена вызывать событие <xref:System.Windows.Freezable.Changed>, необходимо вызывать функцию обратного вызова для каждого <xref:System.Windows.Shapes.Rectangle> — накопление вызовов этих функций значительно снижает производительность.  Кроме того, достаточно затратно добавлять и удалять обработчики на этом этапе, поскольку для этого приложению потребуется пройти по всему списку.  Если скрипт приложения никогда не изменяет <xref:System.Windows.Media.SolidColorBrush>, то последует "расплата" за обслуживание вызываемых без необходимости обработчиков событий <xref:System.Windows.Freezable.Changed>.  
  
 Замораживание элементов <xref:System.Windows.Freezable> может повысить быстродействие, поскольку больше не требуется тратить ресурсы на уведомления об изменениях.  В нижеприведенной таблице показано сравнение размера простого <xref:System.Windows.Media.SolidColorBrush>, когда его свойство <xref:System.Windows.Freezable.IsFrozen%2A> установлено в `true`, и когда нет.  Это предполагает применение одной кисти к свойству <xref:System.Windows.Shapes.Shape.Fill%2A> десяти объектов <xref:System.Windows.Shapes.Rectangle>.  
  
|**Состояние**|**Размер**|  
|-------------------|----------------|  
|Замороженная <xref:System.Windows.Media.SolidColorBrush>|212 байтов|  
|Незамороженная <xref:System.Windows.Media.SolidColorBrush>|972 байта|  
  
 Эта концепция демонстрируется в следующем примере кода.  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### Обработчики изменений для размороженных объектов Freezable могут поддерживать объекты в активном состоянии  
 Делегат, который объект передает в событие <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Freezable>, является в сущности ссылкой на этот объект.  Поэтому обработчики событий <xref:System.Windows.Freezable.Changed> могут поддерживать объекты в активном состоянии дольше, чем обычно.  При выполнении очистки объекта, зарегистрированного для прослушивания события <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Freezable>, необходимо удалить этот делегат перед освобождением объекта.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также внутренне подключается к событиям <xref:System.Windows.Freezable.Changed>.  Например, все [свойства зависимостей](GTMT), которые принимают <xref:System.Windows.Freezable> в качестве значения, будут автоматически прослушивать события <xref:System.Windows.Freezable.Changed>.  Свойство <xref:System.Windows.Shapes.Shape.Fill%2A>, которое принимает <xref:System.Windows.Media.Brush>, иллюстрирует эту концепцию.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 При присваивании элемента `myBrush` для `myRectangle.Fill` делегат, указывающий обратно на объект <xref:System.Windows.Shapes.Rectangle>, будет добавлен к событию <xref:System.Windows.Freezable.Changed> объекта <xref:System.Windows.Media.SolidColorBrush>.  Это означает, что следующий код фактически не помечает `myRect` для сборки мусора:  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 В этом случае `myBrush` по\-прежнему сохраняет `myRectangle` в активном состоянии и снова вызовет его при возникновении события <xref:System.Windows.Freezable.Changed>.  Обратите внимание, что присваивание `myBrush` свойству <xref:System.Windows.Shapes.Shape.Fill%2A> нового <xref:System.Windows.Shapes.Rectangle> просто добавит еще один обработчик событий к `myBrush`.  
  
 Рекомендуемый способ очистки этих типов объектов — удаление <xref:System.Windows.Media.Brush> из свойства <xref:System.Windows.Shapes.Shape.Fill%2A>, которое в свою очередь удалит обработчик событий <xref:System.Windows.Freezable.Changed>.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## Визуализация пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет разновидность элемента <xref:System.Windows.Controls.StackPanel>, который автоматически "делает виртуальным" содержимое дочернего элемента, привязанного к данным.  В данном контексте слово "виртуализация" означает способ, с помощью которого подмножество объектов создается из большего количества элементов данных на основе видимых на экране элементов.  Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(с помощью функций, предоставляемых <xref:System.Windows.Controls.VirtualizingPanel>\) подсчитывает видимые элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> из <xref:System.Windows.Controls.ItemsControl> \(как, например, <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ListView>\) лишь для того, чтобы создать элементы для видимых элементов.  
  
 Для оптимизации производительности визуальные объекты для этих элементов создаются или поддерживаются в активном состоянии, только если они отображаются на экране.  Если визуальные объекты больше не находятся в видимой области элемента управления, то их можно удалить.  Необходимо отличать этот процесс от виртуализации данных, при которой не все объекты данных присутствуют в локальной коллекции, а направляются потоками как вложенные.  
  
 В таблице ниже показано время, затраченное на добавление и отрисовку 5 000 элементов <xref:System.Windows.Controls.TextBlock> к <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.VirtualizingStackPanel>.  В этом случае измеряется время между временем присоединения текстовой строки к свойству <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> объекта <xref:System.Windows.Controls.ItemsControl> и временем отображения текстовой строки элементами панели.  
  
|**Главная панель**|**Время отображения \(мс\)**|  
|------------------------|----------------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## См. также  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Дополнительные рекомендации по повышению производительности](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)