---
title: "Общие сведения о панелях | Microsoft Docs"
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
  - "элементы управления, Panel"
  - "Panel - элемент управления [WPF], об элементе управления Panel"
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: 48
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 45
---
# Общие сведения о панелях
Элементы <xref:System.Windows.Controls.Panel> являются компонентами, которые управляют отрисовкой элементов — их размер и измерения, их положение и расположение их дочернего содержимого.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет ряд стандартных элементов <xref:System.Windows.Controls.Panel> элементов, а также возможность создания пользовательских элементов <xref:System.Windows.Controls.Panel>.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Класс Panel](#Panels_view_from_10000_feet)  
  
-   [Общие члены элемента Panel](#Panels_declared_members)  
  
-   [Производные элементы Panel](#Panels_derived_elements)  
  
-   [Панели пользовательского интерфейса](#Panels_main_UI_elements)  
  
-   [Вложенные элементы Panel](#Panels_nested_panel_elements)  
  
-   [Пользовательские элементы Panel](#Panels_custom_panel_elements)  
  
-   [Поддержка локализации\/глобализации](#Panels_global_localization)  
  
-   [Связанные разделы](#seeAlsoToggle)  
  
<a name="Panels_view_from_10000_feet"></a>   
## Класс Panel  
 <xref:System.Windows.Controls.Panel> является базовым классом для всех элементов, поддерживающих макет приложения [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Производные элементы <xref:System.Windows.Controls.Panel> используются для размещения и упорядочивания элементов в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и коде.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает полный набор реализаций производной панели, позволяющий множество сложных макетов.  Эти производные классы предоставляют свойства и методы, допускающие наиболее стандартные сценарии [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Разработчики, которым не удается найти дочернее упорядочение поведение, удовлетворяющее их требованиям, могут создать новый макет, переопределив методы <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  Дополнительные сведения о поведении пользовательского макета содержатся в разделе [Пользовательские элементы Panel](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## Общие члены Panel  
 Все элементы <xref:System.Windows.Controls.Panel> поддерживают базовые изменения размеров и положения свойств, определенные в <xref:System.Windows.FrameworkElement>, в том числе <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  Дополнительные сведения о позиционировании свойств, определенных в <xref:System.Windows.FrameworkElement>, содержатся в разделе [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> предоставляет дополнительные свойства, которые очень важны в понимании и использовании макета.  Свойство <xref:System.Windows.Controls.Panel.Background%2A> используется для заполнения области между границами производного элемента панели и элементом <xref:System.Windows.Media.Brush>.  Свойство <xref:System.Windows.Controls.Panel.Children%2A> представляет дочернюю коллекцию элементов относительно элементов <xref:System.Windows.Controls.Panel>.  Свойство <xref:System.Windows.Controls.Panel.InternalChildren%2A> представляет содержимое коллекции <xref:System.Windows.Controls.Panel.Children%2A>, а также элементы, созданные привязкой данных.  Оба состоят из <xref:System.Windows.Controls.UIElementCollection> дочерних элементов, расположенных внутри родительского элемента <xref:System.Windows.Controls.Panel>.  
  
 Панель также предоставляет вложенное свойство <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName>, которое может быть использовано для достижения многослойного размещения в производном элементе <xref:System.Windows.Controls.Panel>.  Члены коллекции <xref:System.Windows.Controls.Panel.Children%2A> панели с более высоким значением <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> отображаются перед членами с более низким значением <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName>.  Это полезно для таких панелей, как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.Grid>, позволяющих потомкам совместно использовать одно и то же пространство координат.  
  
 <xref:System.Windows.Controls.Panel> также определяет метод <xref:System.Windows.Controls.Panel.OnRender%2A>, который может использоваться для переопределения поведения представления <xref:System.Windows.Controls.Panel> по умолчанию.  
  
#### Вложенные свойства зависимостей  
 Производные элементы панели широко используют [вложенные свойства](GTMT).  Вложенное свойство представляет собой особую форму [свойства зависимости](GTMT), у которого нет обычной "оболочки" свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  Вложенные свойства имеют специализированный синтаксис в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который можно увидеть в следующих нескольких примерах.  
  
 Одним из предназначений вложенного свойства является разрешение дочерним элементам хранения уникальных значений свойства, фактически определенного родительским элементом.  Приложение этой функциональности содержит дочерние элементы, информирующие родителей, как они должны быть представлены в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что очень полезно для макета приложения.  Дополнительные сведения см. в разделе [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## Производные элементы Panel  
 Многие объекты являются производными от <xref:System.Windows.Controls.Panel>, но не все из них предназначены для использования в качестве поставщиков корневого макета.  Существует шесть определенных классов панелей \(<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> и <xref:System.Windows.Controls.WrapPanel>\), которые предназначены специально для создания приложений [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Каждый элемент панели инкапсулирует свои собственные специальные функциональные возможности, как показано в следующей таблице.  
  
|Имя элемента|Панель пользовательского интерфейса?|Описание|  
|------------------|------------------------------------------|--------------|  
|<xref:System.Windows.Controls.Canvas>|Да|Определяет область, внутри которой можно явным образом разместить дочерние элементы при помощи относительных координат в области <xref:System.Windows.Controls.Canvas>.|  
|<xref:System.Windows.Controls.DockPanel>|Да|Определяет область, внутри которой можно упорядочить дочерние элементы по горизонтали или по вертикали друг относительно друга.|  
|<xref:System.Windows.Controls.Grid>|Да|Определяет гибкую область сетки, состоящей из строк и столбцов.  Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть расположены с помощью свойства <xref:System.Windows.FrameworkElement.Margin%2A>.|  
|<xref:System.Windows.Controls.StackPanel>|Да|Располагает дочерние элементы в одну строку, которую можно ориентировать по горизонтали или по вертикали.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Нет|Обрабатывает макет кнопок вкладки в <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Нет|Выравнивает содержимое элемента управления <xref:System.Windows.Controls.ToolBar>.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Нет|<xref:System.Windows.Controls.Primitives.UniformGrid> используется для упорядочивания дочерних элементов в сетке со ячейками одинакового размера.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Нет|Предоставляет базовый класс для панелей, который может "виртуализировать" их дочернюю коллекцию.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Да|Упорядочивает и виртуализирует содержимое в отдельной строке, ориентированной горизонтально или вертикально.|  
|<xref:System.Windows.Controls.WrapPanel>|Да|<xref:System.Windows.Controls.WrapPanel> размещает дочерние элементы в последовательности слева направо, перенося содержимое на следующую строку на границе содержащего поля.  Дельнейшее упорядочивание происходит последовательно сверху вниз или справа налево в зависимости от значения свойства <xref:System.Windows.Controls.WrapPanel.Orientation%2A>.|  
  
<a name="Panels_main_UI_elements"></a>   
## Панели пользовательского интерфейса  
 Существуют шесть классов панелей, доступных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] которые оптимизированы для поддержки скриптов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, и <xref:System.Windows.Controls.WrapPanel>:  Эти элементы панели являются простыми в использовании, универсальными и достаточно расширяемыми для большинства приложений.  
  
 Каждый производный элемент <xref:System.Windows.Controls.Panel> рассматривает ограничения размеров по\-разному.  Понимание того, как <xref:System.Windows.Controls.Panel> обрабатывает ограничения в горизонтальном или вертикальном направлении, может сделать макет более прогнозируемым.  
  
|**Имя панели**|**Размерность x**|**Размерность y**|  
|--------------------|-----------------------|-----------------------|  
|<xref:System.Windows.Controls.Canvas>|Ограничения содержимого|Ограничения содержимого|  
|<xref:System.Windows.Controls.DockPanel>|Ограниченный.|Ограниченный.|  
|<xref:System.Windows.Controls.StackPanel> \(вертикальная ориентация\)|Ограниченный.|Ограничения содержимого|  
|<xref:System.Windows.Controls.StackPanel> \(горизонтальная ориентация\)|Ограничения содержимого|Ограниченный.|  
|<xref:System.Windows.Controls.Grid>|Ограниченный.|Ограниченные, кроме случаев, когда <xref:System.Windows.GridUnitType> применяется к строкам и столбцам|  
|<xref:System.Windows.Controls.WrapPanel>|Ограничения содержимого|Ограничения содержимого|  
  
 Более подробное описание и примеры использования каждого из этих элементов можно найти ниже.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### Canvas  
 Элемент <xref:System.Windows.Controls.Canvas> позволяет размещение содержимого в соответствие с абсолютными  *x*  и *y* координатами.  Элементы могут быть нарисованы в уникальном месте; или, если элементы занимают те же координаты, порядок, в котором они появляются в разметке, определяет порядок, в котором элементы отображаются.  
  
 <xref:System.Windows.Controls.Canvas> предоставляет самый гибкий макет поддержки любых <xref:System.Windows.Controls.Panel>.  Свойства высоты и ширины используются для определения области canvas, и элементам внутри назначаются абсолютные координаты относительно области родительского <xref:System.Windows.Controls.Canvas>.  Четыре вложенных свойства, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=fullName> и <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=fullName>, допускают точное управление расположением объекта в <xref:System.Windows.Controls.Canvas>, позволяемому разработчику поместить и расположить элементы на экране.  
  
#### ClipToBounds в пределах Canvas  
 <xref:System.Windows.Controls.Canvas> может поместить дочерние элементы в любое положение на экране, даже с координатами, находящимися за пределами определенных <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A>.  Кроме того, на <xref:System.Windows.Controls.Canvas> не влияет размер его дочерних элементов.  В результате имеется возможность для дочернего элемента перерисовывать другие элементы за пределами ограничивающего прямоугольника родительского <xref:System.Windows.Controls.Canvas>.  Поведением <xref:System.Windows.Controls.Canvas> по умолчанию является разрешение прорисовки потомков вне границ родительского <xref:System.Windows.Controls.Canvas>.  Если такое поведение нежелательно, значение свойства <xref:System.Windows.UIElement.ClipToBounds%2A> может быть установлено в `true`.  В результате <xref:System.Windows.Controls.Canvas> обрезается по собственным размерам.  <xref:System.Windows.Controls.Canvas> — единственный элемент макета, который позволяет дочерним элементам отображаться вне своих границ.  
  
 Это поведение показано графически на странице [Пример сравнения свойств ширины](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
#### Определение и использование Canvas  
 <xref:System.Windows.Controls.Canvas> может быть легко создан с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или в коде.  В следующем примере демонстрируется использование <xref:System.Windows.Controls.Canvas> для абсолютного расположения содержимого.  Этот код формирует три 100\-пиксельных квадрата.  Первый квадрат красного цвета, и его левый верхний угол \(*x, y*\) задан как \(0, 0\).  Второй квадрат зеленого цвета, и его левый верхний угол задан как \(100, 100\), ниже и правее первого квадрата.  Третий квадрат — синий, и координаты его левого верхнего угла равны \(50, 50\), таким образом, он перекрывает правый нижний квадрант первого квадрата и левый верхний квадрант второго.  Так как третий накладывается последним, он расположен поверх других двух квадратов — следовательно, перекрывающиеся фрагменты принимают цвет третьего квадрата.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Обычный элемент холста.](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.png "panel\_intro\_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### DockPanel  
 Элемент <xref:System.Windows.Controls.DockPanel> использует вложенное свойство <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>, как оно задано в дочерних элементах содержимого, для размещения содержимого на границах контейнера.  Когда <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> имеет значение <xref:System.Windows.Controls.Dock> или <xref:System.Windows.Controls.Dock>, она располагает дочерние элементы выше или ниже друг друга.  Если свойство <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> установлено в значение <xref:System.Windows.Controls.Dock> или <xref:System.Windows.Controls.Dock>, дочерние элементы размещаются слева или справа друг от друга.  Свойство <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> определяет положение окончательного элемента, добавляемого в качестве дочернего элемента <xref:System.Windows.Controls.DockPanel>.  
  
 Можно использовать <xref:System.Windows.Controls.DockPanel> для размещения группы связанных элементов управления, например, набора кнопок.  Кроме того, можно использовать его для создания "разделенного" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], аналогично найденному в [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### Изменение размеров в зависимости от содержимого  
 Если свойства <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> элемента управления <xref:System.Windows.Controls.DockPanel> не указаны, она подстраивается по размеру к содержимому.  Размер может увеличиваться или уменьшаться, чтобы вместить дочерние элементы.  Однако, если заданы эти свойства и больше нет свободного места для следующего указанного дочернего элемента, <xref:System.Windows.Controls.DockPanel> не отображает этот дочерний элемент или последующие дочерние элементы и не принимает размер последующих дочерних элементов.  
  
#### LastChildFill  
 По умолчанию, последний дочерний элемент <xref:System.Windows.Controls.DockPanel> заполняет оставшееся незанятое пространство.  Если такое поведение не требуется, присвойте свойству <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> значение `false`.  
  
#### Определение и использование DockPanel  
 В следующем примере демонстрируется разделение пространства с помощью <xref:System.Windows.Controls.DockPanel>.  Пять элементов <xref:System.Windows.Controls.Border> добавляются в качестве дочерних элементов родительской <xref:System.Windows.Controls.DockPanel>.  Каждый использует свое свойство размещения <xref:System.Windows.Controls.DockPanel> для разделения пространства.  Последний элемент "заполняет" оставшееся, незанятое пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### Сетка  
 Элемент <xref:System.Windows.Controls.Grid> объединяет возможности абсолютного позиционирования и управления табличными данными.  Элемент управления <xref:System.Windows.Controls.Grid> позволяет удобно размещать элементы и менять их стиль.  Элемент управления <xref:System.Windows.Controls.Grid> позволяет определить гибкие группы столбцов и строк и предоставляет возможность распространять информацию о размере между несколькими элементами <xref:System.Windows.Controls.Grid>.  
  
#### Чем сетка отличается от таблицы?  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> совместно используют некоторые общие функциональные возможности, но каждый наилучшим образом подходит для различных скриптов.  <xref:System.Windows.Documents.Table> предназначена для использования внутри содержимого потока \(см. раздел [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md) для получения дополнительных сведений о содержимом потока\).  Сетку лучше всего использовать внутри форм \(главным образом, где\-либо вне содержимого потока\).  Внутри <xref:System.Windows.Documents.FlowDocument> элемент <xref:System.Windows.Documents.Table> поддерживает такие возможности, как разбиение на страницы, обратный порядок столбцов и выделение содержимого, в то время как <xref:System.Windows.Controls.Grid> их не поддерживает.  С другой стороны элемент <xref:System.Windows.Controls.Grid> лучше всего использовать вне <xref:System.Windows.Documents.FlowDocument> по многим причинам, включая то, что <xref:System.Windows.Controls.Grid> добавляет элементы на основе индексов строки и столбца, в то время как <xref:System.Windows.Documents.Table> ― нет.  Элемент <xref:System.Windows.Controls.Grid> позволяет послойно размещать дочернее содержимое, что дает возможность разместить в одной "ячейке" несколько элементов. Элемент <xref:System.Windows.Documents.Table> не поддерживает послойное размещение.  Дочерние элементы элемента управления <xref:System.Windows.Controls.Grid> могут быть расположены относительно границы "ячейки" абсолютно.  Элемент <xref:System.Windows.Documents.Table> не поддерживает эту возможность.  Наконец, <xref:System.Windows.Controls.Grid> легковеснее, чем <xref:System.Windows.Documents.Table>.  
  
#### Изменение размера столбцов и строк  
 Столбцы и строки, определенные в <xref:System.Windows.Controls.Grid>, могут воспользоваться преимуществами изменения размера <xref:System.Windows.GridUnitType>, чтобы пропорционально распределить оставшееся пространство.  При выборе <xref:System.Windows.GridUnitType> в качестве высота или ширина строки или столбца, столбец или строка получает взвешенные пропорции оставшегося доступного пространства.  В этом заключается отличие от <xref:System.Windows.GridUnitType>, при котором распределение пространства будет равномерным, в зависимости от содержимого столбца или строки.  Данный параметр измеряется как `*` или `2*` при использовании [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  В первом случае строка или столбец получают однократное доступное пространство, во втором случае — двукратное и т.д.  При объединении этой методики пропорционального распределения пространства с установкой для свойств <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> значения `Stretch` появляется возможность разделения пространства макета в процентах от пространства экрана.  Элемент управления <xref:System.Windows.Controls.Grid> является единственной панелью макета, которая может распределять пространство таким образом.  
  
#### Определение и использование сетки  
 В следующем примере демонстрируется построение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], аналогичного обнаруженному в диалоговом окне Run, доступном через меню [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Пуск.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Обычный элемент сетки.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.png "avalon\_run\_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### StackPanel  
 <xref:System.Windows.Controls.StackPanel> позволяет "выстраивать" элементы в определенном направлении.  По умолчанию, направление стека является вертикальным.  Свойство <xref:System.Windows.Controls.StackPanel.Orientation%2A> может использоваться для потока содержимого элемента управления.  
  
#### Сравнение StackPanel иDockPanel  
 Несмотря на то, что <xref:System.Windows.Controls.DockPanel> может также содержать дочерние элементы, <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel> не дают аналогичных результатов в некоторых случаях использования.  Например, последовательность дочерних элементов может повлиять на их размер в <xref:System.Windows.Controls.DockPanel>, но не в <xref:System.Windows.Controls.StackPanel>.  Это происходит потому, что <xref:System.Windows.Controls.StackPanel> имеет размер, зависящий от направлении стека на <xref:System.Double.PositiveInfinity>, тогда как <xref:System.Windows.Controls.DockPanel> обладает только доступным размером.  
  
 Следующий пример демонстрирует ключевые различия.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 Разница в поведении отрисовки показана на этом рисунке.  
  
 ![Снимок экрана: сравнение StackPanel Снимок экрана DockPanel](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.png "layout\_smiley\_stackpanel")  
  
#### Определение и использование StackPanel  
 В следующем примере демонстрируется использование <xref:System.Windows.Controls.StackPanel> для создания набора вертикально расположенных кнопок.  Для горизонтального расположения присвойте свойству <xref:System.Windows.Controls.StackPanel.Orientation%2A> значение <xref:System.Windows.Controls.Orientation>.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Обычный элемент StackPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.png "panel\_intro\_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет разновидность элемента <xref:System.Windows.Controls.StackPanel>, который автоматически "делает виртуальным" содержимое дочернего элемента, привязанного к данным.  В данном контексте слово "виртуализация" означает способ, с помощью которого подмножество элементов создается из большого количества данных на основе видимых на экране элементов.  Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(с помощью функций, предоставляемых <xref:System.Windows.Controls.VirtualizingPanel>\) подсчитывает видимые элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> из <xref:System.Windows.Controls.ItemsControl> \(как, например, <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ListView>\) лишь для того, чтобы создать элементы для видимых элементов.  
  
 Элемент <xref:System.Windows.Controls.VirtualizingStackPanel> автоматически устанавливается в качестве ведущего элемента для элементов управления, например <xref:System.Windows.Controls.ListBox>.  При размещении присоединенной коллекции данных содержимое будет автоматически виртуализировано, пока содержимое находится в пределах <xref:System.Windows.Controls.ScrollViewer>.  Это значительно повышает быстродействие при размещении большого числа дочерних элементов.  
  
 Следующая разметка демонстрируется использование <xref:System.Windows.Controls.VirtualizingStackPanel> в качестве узла элементов.  <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> [вложенное свойство](GTMT) должно быть установлено в `true` \(по умолчанию\) для осуществления виртуализации.  
  
 [!code-xml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> используется для расположения дочерних элементов в последовательную слева направо, разрывая содержимое для перехода на следующую строку при достижении границы родительского контейнера.  Содержимое может быть ориентировано горизонтально или вертикально.  Элемент <xref:System.Windows.Controls.WrapPanel> полезен, когда [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] создается потоком элементов.  Она может также использоваться для установления единого размера для всех дочерних элементов.  
  
 В следующем примере демонстрируется создание <xref:System.Windows.Controls.WrapPanel> для отображения элементов управления <xref:System.Windows.Controls.Button>, которые переносятся при достижении границы контейнера.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Обычный элемент WrapPanel.](../../../../docs/framework/wpf/controls/media/wrappanel-element.png "WrapPanel\_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## Вложенные элементы Panel  
 Элементы <xref:System.Windows.Controls.Panel> могут быть вложены друг в друга для возможности создания сложных макетов.  Это может быть очень полезным в ситуациях, когда одна <xref:System.Windows.Controls.Panel> идеально подходит для фрагмента [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], но не может удовлетворить потребности различных частей [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Практически не существует ограничений в объема вложения, которое приложение может поддерживать, однако лучше всего ограничить приложение использованием только тех панелей, которые действительно необходимы для макета.  В большинстве случаев элемент <xref:System.Windows.Controls.Grid> может использоваться вместо вложенных панелей из\-за его гибкости в качестве контейнера макета.  Это может повысить производительность в приложении, убирая ненужные элементы из дерева.  
  
 В следующем примере демонстрируется создание [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], использующего преимущества вложенных элементов <xref:System.Windows.Controls.Panel>, чтобы добиться определенного макета.  В этом конкретном случае элемент <xref:System.Windows.Controls.DockPanel> используется для предоставления структуры [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], и вложенные элементы <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.Canvas> используются для размещения дочерних элементов внутри родительской <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], выглядящий следующим образом.  
  
 ![Пользовательский интерфейс, использующий вложенные панели.](../../../../docs/framework/wpf/controls/media/nested-panels.png "nested\_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## Пользовательские элементы Panel  
 В то время как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет массив гибкий элементов управления макетом, поведение пользовательского макета также можно достичь путем переопределения методов <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  Пользовательские изменения размеров и положения могут быть выполнены путем определения нового поведения размещения в этих переопределенных методах.  
  
 Аналогично, поведение пользовательского макета, основанное на производных классах \(например, <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.Grid>\), может быть задано путем переопределения их методов <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
 Следующая разметка демонстрирует способы создания пользовательского элемента <xref:System.Windows.Controls.Panel>.  Новый элемент <xref:System.Windows.Controls.Panel>, определенный как `PlotPanel`, поддерживает размещение дочерних элементов с использованием жестко закодированных координат *x* и *y*.  В этом примере элемент <xref:System.Windows.Shapes.Rectangle> \(не показано\) находится в точке с координатами 50 \( *x*\) и 50 \( *y* \).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Реализации более сложных пользовательских панелей можно найти на странице [Пример создания пользовательской панели с переносом содержимого](http://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## Поддержка локализации\/глобализации  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает ряд возможностей для создании локализуемого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Все элементы panel изначально поддерживают свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A>, которое может использоваться для динамического содержимого, основанного на параметрах локализации или языка пользователя.  Дополнительные сведения см. в разделе <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Свойство <xref:System.Windows.Window.SizeToContent%2A> предоставляет механизм, позволяющий разработчикам приложений предвидеть потребности локализованного [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  С использованием значения <xref:System.Windows.SizeToContent> этого свойства родительское <xref:System.Windows.Window> всегда изменяет свой размер динамически по размеру содержимого и не ограничивается искусственно высотой или шириной.  
  
 Элементы <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.StackPanel> — хороший выбор, если нужно создать локализуемый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Элемент <xref:System.Windows.Controls.Canvas> не удобен, поскольку он размещает содержимое абсолютно, делая локализацию затруднительной.  
  
 Дополнительные сведения о создании приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с локализуемыми [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] содержатся в разделе [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md).  
  
## См. также  
 [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [WPF Layout Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160054)   
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)   
 [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Create a Custom Content\-Wrapping Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159979)   
 [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)