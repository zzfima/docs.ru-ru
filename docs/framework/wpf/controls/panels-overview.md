---
title: Общие сведения о панелях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 65f5fa9eeffdeb6e7bc869d159b4b33d75fd7570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="panels-overview"></a>Общие сведения о панелях
<xref:System.Windows.Controls.Panel> элементы являются компонентами, которые управляют отображением элементов — их размер и измерения, их положение и расположение их дочернего содержимого. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Предоставляет ряд предопределенных <xref:System.Windows.Controls.Panel> элементы, а также возможность создания пользовательских <xref:System.Windows.Controls.Panel> элементов.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Класс Panel](#Panels_view_from_10000_feet)  
  
-   [Общие члены элементов Panel](#Panels_declared_members)  
  
-   [Производные элементы Panel](#Panels_derived_elements)  
  
-   [Панели пользовательского интерфейса](#Panels_main_UI_elements)  
  
-   [Вложенные элементы Panel](#Panels_nested_panel_elements)  
  
-   [Пользовательские элементы Panel](#Panels_custom_panel_elements)  
  
-   [Поддержка локализации и глобализации](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Класс Panel  
 <xref:System.Windows.Controls.Panel> является базовым классом для всех элементов, предоставляющих макет поддерживает в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Производный <xref:System.Windows.Controls.Panel> элементы используются для размещения и упорядочения элементов в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и код.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает полный набор реализаций производных панели, позволяющих использовать множество сложных макетов. Эти производные классы предоставляют свойства и методы, с помощью которых реализуется большинство стандартных сценариев [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Разработчики, не удается найти поведение упорядочение дочерних со своими требованиями можно создать новые макеты, переопределив <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A> методы. Дополнительные сведения о поведении пользовательских макетов см. в разделе [Пользовательские элементы Panel](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Общие члены элементов Panel  
 Все <xref:System.Windows.Controls.Panel> элементы поддерживают базовые изменения размеров и положения свойств, определенных <xref:System.Windows.FrameworkElement>, в том числе <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, и <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Дополнительные сведения о свойства позиционирования, определенные для <xref:System.Windows.FrameworkElement>, в разделе [выравнивание, поля и заполнение Обзор](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> предоставляет дополнительные свойства, которые очень важны в понимании и использовании макета. <xref:System.Windows.Controls.Panel.Background%2A> Свойство используется для заполнения области между границами производной панели элементов с <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A> Представляет коллекцию дочерних элементов, <xref:System.Windows.Controls.Panel> включает в себя. <xref:System.Windows.Controls.Panel.InternalChildren%2A> представляет содержимое <xref:System.Windows.Controls.Panel.Children%2A> коллекции, а также те элементы, формируемые службами привязки данных. Оба состоят из <xref:System.Windows.Controls.UIElementCollection> из дочерних элементов, расположенных в родительском элементе <xref:System.Windows.Controls.Panel>.  
  
 Панель также предоставляет <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> присоединенное свойство, которое можно использовать для достижения многослойного размещения в производном <xref:System.Windows.Controls.Panel>. Элементы панели <xref:System.Windows.Controls.Panel.Children%2A> коллекции с более высоким <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> значения отображаются перед элементами с более низким <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> значение. Это особенно полезно для панелей например <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.Grid> позволяющих потомкам совместно использовать то же пространство координат.  
  
 <xref:System.Windows.Controls.Panel> также определяет <xref:System.Windows.Controls.Panel.OnRender%2A> метод, который может использоваться для переопределения поведения по умолчанию представления <xref:System.Windows.Controls.Panel>.  
  
#### <a name="attached-properties"></a>Вложенные свойства  
 Производные элементы панели широко используют вложенные свойства. Вложенное свойство представляет собой особую форму свойства зависимости, не имеющего обычной "оболочки" свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. Вложенные свойства имеют специальный синтаксис в языке [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], с которым можно познакомиться в некоторых из следующих примеров.  
  
 Одной из целей вложенного свойства является предоставление возможности дочерним элементам хранить уникальные значения свойства, фактически определенные в родительском элементе. Случаем применения данной возможности является уведомление родительского элемента со стороны дочерних элементов о способе их представления в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что очень полезно при создании макета приложения. Дополнительные сведения см. в разделе [Общие сведения о вложенных свойствах](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Производные элементы Panel  
 Многие объекты являются производными от <xref:System.Windows.Controls.Panel>, но не все из них предназначены для использования в качестве поставщиков корневого макета. Существует шесть определенных классов панелей (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, и <xref:System.Windows.Controls.WrapPanel>), которые созданы специально для создания приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Каждый элемент панели имеет собственные специальные возможности, представленные в следующей таблице.  
  
|Имя элемента|Панель пользовательского интерфейса?|Описание|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Да|Определяет область, внутри которой можно явным образом разместить дочерние элементы при помощи относительных координат в <xref:System.Windows.Controls.Canvas> области.|  
|<xref:System.Windows.Controls.DockPanel>|Да|Определяет область, в которой можно горизонтально либо вертикально упорядочивать дочерние элементы относительно друг друга.|  
|<xref:System.Windows.Controls.Grid>|Да|Определяет область с таблицей переменного размера, состоящей из столбцов и строк. Дочерние элементы <xref:System.Windows.Controls.Grid> расположены с помощью <xref:System.Windows.FrameworkElement.Margin%2A> свойство.|  
|<xref:System.Windows.Controls.StackPanel>|Да|Выравнивает дочерние элементы в одну линию, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Нет|Обрабатывает макет кнопок вкладки в <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Нет|Упорядочивает содержимое в <xref:System.Windows.Controls.ToolBar> элемента управления.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Нет|<xref:System.Windows.Controls.Primitives.UniformGrid> используется для упорядочивания дочерних элементов в сетке с ячейками одинакового размера.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Нет|Предоставляет базовый класс для панелей, которые могут "виртуализировать" дочерние коллекции.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Да|Упорядочивает и виртуализирует одну строку содержимого, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.WrapPanel>|Да|<xref:System.Windows.Controls.WrapPanel> размещает дочерние элементы в последовательности слева направо, перенося содержимое на следующую строку на границе содержащего поля. Дополнительное упорядочение происходит последовательно сверху вниз или справа налево, в зависимости от значения <xref:System.Windows.Controls.WrapPanel.Orientation%2A> свойство.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Панели пользовательского интерфейса  
 Существует шесть классов панелей, доступных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , оптимизированы для поддержки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сценариев: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, и <xref:System.Windows.Controls.WrapPanel>. Эти элементы панели являются простыми в использовании, гибкими и достаточно широкими для большинства приложений.  
  
 Каждый производный <xref:System.Windows.Controls.Panel> элемент рассматривает ограничения размеров по-разному. Основные сведения о том, как <xref:System.Windows.Controls.Panel> обрабатывает ограничения в горизонтальном или вертикальном направлении, может сделать макет более предсказуемыми.  
  
|**Имя панели**|**Размеры по оси x**|**Размеры по оси y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Ограничено содержимым|Ограничено содержимым|  
|<xref:System.Windows.Controls.DockPanel>|Ограничено|Ограничено|  
|<xref:System.Windows.Controls.StackPanel> (Вертикальная ориентация)|Ограничено|Ограничено содержимым|  
|<xref:System.Windows.Controls.StackPanel> (Горизонтальная ориентация)|Ограничено содержимым|Ограничено|  
|<xref:System.Windows.Controls.Grid>|Ограничено|Ограниченные, кроме случаев где <xref:System.Windows.GridUnitType.Auto> применяется к строкам и столбцам|  
|<xref:System.Windows.Controls.WrapPanel>|Ограничено содержимым|Ограничено содержимым|  
  
 С более подробными описаниями и примерами использования каждого из этих элементов можно ознакомиться ниже.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 <xref:System.Windows.Controls.Canvas> Элемент позволяет размещение содержимого в соответствии с абсолютным *x -* и *y -* координаты. Элементы могут быть нарисованы в уникальном месте или, если элементы занимают одни координаты, порядок, в котором они отображаются в разметке, определяется порядком, в котором нарисованы эти элементы.  
  
 <xref:System.Windows.Controls.Canvas> предоставляет самый гибкий макет поддержки любых <xref:System.Windows.Controls.Panel>. Высота и ширина используются для определения области canvas, и элементам внутри назначаются абсолютные координаты относительно области родительского <xref:System.Windows.Controls.Canvas>. Четыре вложенных свойства, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, допускают точное управление расположением объекта в <xref:System.Windows.Controls.Canvas>, позволяющий разработчику размещения и упорядочения элементов на экране.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Свойство ClipToBounds в элементе Canvas  
 <xref:System.Windows.Controls.Canvas> можно разместить дочерние элементы в любом месте на экране, даже с координатами, которые находятся вне определены собственные <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A>. Кроме того <xref:System.Windows.Controls.Canvas> не влияет на размер его дочерних элементов. В результате возможна для дочернего элемента перерисовывать другие элементы за пределами ограничивающего прямоугольника родительского <xref:System.Windows.Controls.Canvas>. Поведение по умолчанию <xref:System.Windows.Controls.Canvas> позволяет дочерним элементам отображаться за пределами границ родительского <xref:System.Windows.Controls.Canvas>. Если такое поведение нежелательно, <xref:System.Windows.UIElement.ClipToBounds%2A> свойству можно присвоить значение `true`. В результате <xref:System.Windows.Controls.Canvas> ролика собственный размер. <xref:System.Windows.Controls.Canvas> является элементом только макет, который позволяет дочерним элементам отображаться вне границ элемента.  
  
 Такое поведение графически показано в [примере сравнения свойств ширины](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
#### <a name="defining-and-using-a-canvas"></a>Определение и использование Canvas  
 Объект <xref:System.Windows.Controls.Canvas> может быть создан при помощи [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода. В следующем примере демонстрируется использование <xref:System.Windows.Controls.Canvas> для абсолютного расположения содержимого. Этот код рисует три квадрата со стороной в 100 пикселей. Первый квадрат — красный и координаты (*x, y*) его левого верхнего угла имеют значение (0, 0). Второй квадрат — зеленый, и его левый верхний угол имеет координаты (100, 100). Он находится ниже и правее первого квадрата. Третий квадрат — синий, его левый верхний угол имеет координаты (50, 50); таким образом, он пересекается с правым нижним углом первого квадрата и левым верхним углом второго. Так как третий квадрат накладывается последним, он будет отображаться поверх первых двух квадратов — то есть пересекающиеся участки принимают цвет третьей фигуры.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент Canvas.] (../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 <xref:System.Windows.Controls.DockPanel> Элемент использует <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> вложенного свойства, заданные в дочерних элементах содержимого, для размещения содержимого на границах контейнера. Когда <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> равно <xref:System.Windows.Controls.Dock.Top> или <xref:System.Windows.Controls.Dock.Bottom>, она располагает дочерние элементы выше или ниже друг с другом. Когда <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> равно <xref:System.Windows.Controls.Dock.Left> или <xref:System.Windows.Controls.Dock.Right>, он размещает дочерние элементы слева или справа от друг с другом. <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Свойство определяет позицию последнего элемента, который добавлен в качестве дочернего элемента <xref:System.Windows.Controls.DockPanel>.  
  
 Можно использовать <xref:System.Windows.Controls.DockPanel> для размещения группы связанных элементов управления, такие как набор кнопок. Кроме того, можно использовать его для создания разделенного на панели [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], похожего на интерфейс [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### <a name="sizing-to-content"></a>Изменение размеров в зависимости от содержимого  
 Если его <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства не заданы, <xref:System.Windows.Controls.DockPanel> размеры на его содержимое. Размер может увеличиваться или уменьшаться, чтобы вместить его дочерние элементы. Тем не менее, если заданы эти свойства и больше нет свободного места для следующего указанного дочернего элемента <xref:System.Windows.Controls.DockPanel> не отображает этот дочерний элемент или последующие дочерние элементы и не принимает размер последующих дочерних элементов.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 По умолчанию, последний дочерний <xref:System.Windows.Controls.DockPanel> элемент «заполнит» оставшееся нераспределенное пространство. Если такое поведение нежелательно, задайте <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> свойства `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Определение и использование DockPanel  
 Следующий пример демонстрирует разделение пространства с помощью <xref:System.Windows.Controls.DockPanel>. Пять <xref:System.Windows.Controls.Border> элементы добавляются как дочерние элементы родительского <xref:System.Windows.Controls.DockPanel>. Каждый использует свое свойство размещения <xref:System.Windows.Controls.DockPanel> для разделения пространства. Последний элемент "заполняет" оставшееся незанятое пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 <xref:System.Windows.Controls.Grid> Элемент объединяет возможности абсолютного позиционирования и управления табличными данными. Объект <xref:System.Windows.Controls.Grid> позволяет легко расположения и стиля элементов. <xref:System.Windows.Controls.Grid> позволяет определить группы столбцов и строк, гибкий и предоставляет возможность распространять информацию о размере между несколькими <xref:System.Windows.Controls.Grid> элементов.  
  
#### <a name="how-is-grid-different-from-table"></a>Чем Grid отличается от Table?  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> совместно используют некоторые общие функциональные возможности, но каждый из них лучше всего подходят для различных сценариев. Объект <xref:System.Windows.Documents.Table> предназначен для использования в содержимом нефиксированного формата (см. [Обзор передачи документа](../../../../docs/framework/wpf/advanced/flow-document-overview.md) Дополнительные сведения о содержимом потока). Сетки лучше всего использовать внутри форм (по сути в любом месте вне потокового содержимого). В пределах <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> поддерживает потока такие возможности, как разбиение на страницы, обратный порядок столбцов и Выбор содержимого во время <xref:System.Windows.Controls.Grid> — нет. Объект <xref:System.Windows.Controls.Grid> с другой стороны лучше всего использовать за пределами <xref:System.Windows.Documents.FlowDocument> по многим причинам, в том числе <xref:System.Windows.Controls.Grid> добавляет элементы на основе строк и столбцов индекса, <xref:System.Windows.Documents.Table> — нет. <xref:System.Windows.Controls.Grid> Элемент позволяет слоев дочернее содержимое, что позволяет более одного элемента в одной «ячейки». <xref:System.Windows.Documents.Table> не поддерживает иерархическое представление. Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть расположены абсолютно относительно границы «ячейки». <xref:System.Windows.Documents.Table> не поддерживает эту функцию. Наконец <xref:System.Windows.Controls.Grid> легкую чем <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Поведение столбцов и строк при изменении их размера  
 Столбцы и строки, определенные в <xref:System.Windows.Controls.Grid> могут воспользоваться преимуществами <xref:System.Windows.GridUnitType.Star> изменения размера, чтобы пропорционально распределить оставшееся пространство. Когда <xref:System.Windows.GridUnitType.Star> выбран в качестве высота или ширина строки или столбца, столбец или строка получает взвешенные пропорции оставшегося доступного пространства. Это отличается от <xref:System.Windows.GridUnitType.Auto>, которой будет распределять пространство равномерно на основе размера содержимого столбца или строки. Это значение выражается как `*` или `2*` при использовании языка [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. В первом случае строка или столбец будет получать определенное доступное пространство, а во втором случае — в два раза больше. При объединении этой методики для пропорционально распределения пространства с <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> значение `Stretch` имеется возможность разделения пространства макета в процентах от места на экране. <xref:System.Windows.Controls.Grid> является единственной панелью макета, распределяющий пространство таким образом.  
  
#### <a name="defining-and-using-a-grid"></a>Определение и использование Grid  
 В следующем примере демонстрируется построение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] аналогичного используемому в диалоговом окне Run, доступном в меню "Пуск" [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент сетки.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Объект <xref:System.Windows.Controls.StackPanel> позволяет «выстраивать» элементы в определенном направлении. По умолчанию направление стека является вертикальным. <xref:System.Windows.Controls.StackPanel.Orientation%2A> Свойство может использоваться для управления передачей содержимого.  
  
#### <a name="stackpanel-vs-dockpanel"></a>Сравнение StackPanel и DockPanel  
 Несмотря на то что <xref:System.Windows.Controls.DockPanel> можно также «наложение» дочерних элементов, <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel> не дают аналогичных результатов в некоторых сценариях использования. Например, порядок дочерних элементов может повлиять на их размер в <xref:System.Windows.Controls.DockPanel> , но не в <xref:System.Windows.Controls.StackPanel>. Это вызвано <xref:System.Windows.Controls.StackPanel> стека в направлении <xref:System.Double.PositiveInfinity>, тогда как <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.  
  
 Следующий пример демонстрирует это ключевое различие.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 На этом рисунке видна разница в поведении отрисовки.  
  
 ![Снимок экрана: сравнение StackPanel и снимок экрана DockPanel](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Определение и использование StackPanel  
 В следующем примере демонстрируется использование <xref:System.Windows.Controls.StackPanel> для создания набора вертикально расположенных кнопок. Для горизонтального расположения задать <xref:System.Windows.Controls.StackPanel.Orientation%2A> свойства <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент StackPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет разновидность <xref:System.Windows.Controls.StackPanel> элемент, который автоматически «виртуализирует» с привязкой к данным дочернего содержимого. В данном контексте слово "виртуализация" означает способ, с помощью которого подмножество элементов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel> (через функциональные возможности, предоставляемые <xref:System.Windows.Controls.VirtualizingPanel>) подсчитывает видимые элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> из <xref:System.Windows.Controls.ItemsControl> (такие как <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ListView>) создавать только элементы для видимых элементов.  
  
 <xref:System.Windows.Controls.VirtualizingStackPanel> Элемент автоматически устанавливается как ведущих элементов для элементов управления, например <xref:System.Windows.Controls.ListBox>. При размещении данных присоединенной коллекции, содержимое будет автоматически виртуализировано, при условии, что содержимое находится в границах <xref:System.Windows.Controls.ScrollViewer>. Это значительно повышает производительность при размещении большого числа дочерних элементов.  
  
 Приведенный ниже код демонстрирует использование <xref:System.Windows.Controls.VirtualizingStackPanel> как узел элементов. <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> Вложенное свойство должно быть присвоено `true` (по умолчанию) для виртуализации или делать это.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> используется для размещения дочерних элементов в последовательности слева направо, перенося содержимое на следующую строку при достижении границы родительского контейнера. Содержимое может быть ориентировано горизонтально или вертикально. <xref:System.Windows.Controls.WrapPanel> полезно, когда [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев. Его также можно использовать для установления единого размера для всех его дочерних элементов.  
  
 Следующий пример демонстрирует создание <xref:System.Windows.Controls.WrapPanel> для отображения <xref:System.Windows.Controls.Button> элементов управления, которые переносятся при достижении границы контейнера.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент WrapPanel.](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Вложенные элементы Panel  
 <xref:System.Windows.Controls.Panel> элементы могут быть вложены друг с другом для создания сложных макетов. Это может оказаться очень полезным в ситуациях, где одно <xref:System.Windows.Controls.Panel> идеально подходит для части [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], но не может удовлетворить потребности в другую часть [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Практически не существует ограничения объема вложения, которое может поддерживать приложение, но лучше ограничить приложение использованием только тех панелей, которые действительно необходимы для макета. Во многих случаях <xref:System.Windows.Controls.Grid> элемент может использоваться вместо вложенных панелей из-за его гибкости в качестве контейнера макета. Это может повысить производительность приложения, убирая ненужные элементы из дерева.  
  
 Следующий пример демонстрирует создание [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , использующего преимущества вложенных <xref:System.Windows.Controls.Panel> элементы для достижения определенного макета. В данном случае <xref:System.Windows.Controls.DockPanel> элемент используется для предоставления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] структуры и вложенными <xref:System.Windows.Controls.StackPanel> элементов, <xref:System.Windows.Controls.Grid>и <xref:System.Windows.Controls.Canvas> используются для размещения дочерних элементов внутри родительской <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Пользовательский интерфейс, использующий вложенные панели.](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Пользовательские элементы Panel  
 Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет массив гибкий макет элементов управления, пользовательский макет поведения также может осуществляться путем переопределения <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A> методы. Пользовательские изменения размеров и положения могут быть выполнены путем определения нового поведения размещения с помощью этих методов переопределения.  
  
 Аналогично, на основе поведения пользовательского макета производные классы (такие как <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.Grid>) можно определить путем переопределения их <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A> методы.  
  
 Приведенный ниже код демонстрирует создание пользовательского <xref:System.Windows.Controls.Panel> элемента. Этот новый <xref:System.Windows.Controls.Panel>, определенный как `PlotPanel`, поддерживает размещение дочерних элементов с использованием жестко *x -* и *y -* координаты. В этом примере <xref:System.Windows.Shapes.Rectangle> (не показано) элемент располагается в точке с координатами 50 (*x*) до 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Более сложные реализации пользовательских панелей можно найти в разделе [примера создания пользовательской панели с переносом содержимого](http://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Поддержка локализации и глобализации  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает ряд возможностей для создания локализуемого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Все элементы panel изначально поддерживают <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство, которое может использоваться для динамического содержимого на основе параметров пользователя язык или язык. Дополнительные сведения см. в разделе <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 <xref:System.Windows.Window.SizeToContent%2A> Свойство предоставляет механизм, позволяющий разработчикам приложений предвидеть потребности локализованные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. С помощью <xref:System.Windows.SizeToContent.WidthAndHeight> значения данного свойства является родительским <xref:System.Windows.Window> всегда изменяет свой размер динамически по размеру содержимого и не ограничивается искусственный ограничения высоты или ширины.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, и <xref:System.Windows.Controls.StackPanel> — это хороший выбор для локализуемых [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas> Тем не менее, является хорошим выбором, так как его расположение содержимого абсолютно, что затрудняет локализации.  
  
 Дополнительные сведения о создании приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с локализуемыми [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] см. в разделе [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Пример коллекции макетов WPF](http://go.microsoft.com/fwlink/?LinkID=160054)  
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)  
 [Пример коллекции элементов управления WPF](http://go.microsoft.com/fwlink/?LinkID=160053)  
 [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Создать пользовательский образец панели с переносом содержимого](http://go.microsoft.com/fwlink/?LinkID=159979)  
 [Общие сведения о присоединенных свойствах](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
