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
ms.openlocfilehash: d0962793854a6066112eb987fbdb3f703617787f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124433"
---
# <a name="panels-overview"></a>Общие сведения о панелях
<xref:System.Windows.Controls.Panel> элементы — это компоненты, управляющие отрисовкой элементов (их размер и размеры, их расположение и расположение их дочернего содержимого). [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет ряд предопределенных элементов <xref:System.Windows.Controls.Panel>, а также возможность создания пользовательских элементов <xref:System.Windows.Controls.Panel>.  
  
 Эта тема описана в следующих разделах.  
  
- [Класс Panel](#Panels_view_from_10000_feet)  
  
- [Общие члены элементов Panel](#Panels_declared_members)  
  
- [Производные элементы Panel](#Panels_derived_elements)  
  
- [Панели пользовательского интерфейса](#Panels_main_UI_elements)  
  
- [Вложенные элементы Panel](#Panels_nested_panel_elements)  
  
- [Пользовательские элементы Panel](#Panels_custom_panel_elements)  
  
- [Поддержка локализации и глобализации](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Класс Panel  
 <xref:System.Windows.Controls.Panel> является базовым классом для всех элементов, которые обеспечивают поддержку макета в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Производные <xref:System.Windows.Controls.Panel> элементы используются для размещения и упорядочения элементов в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и коде.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает полный набор реализаций производных панели, позволяющих использовать множество сложных макетов. Эти производные классы предоставляют свойства и методы, с помощью которых реализуется большинство стандартных сценариев [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Разработчикам, которые не могут найти поведение дочернего расположения, которое соответствует их потребностям, можно создавать новые макеты путем переопределения методов <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>. Дополнительные сведения о поведении пользовательских макетов см. в разделе [Пользовательские элементы Panel](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Общие члены элементов Panel  
 Все элементы <xref:System.Windows.Controls.Panel> поддерживают базовые свойства изменения размера и позиционирования, определенные <xref:System.Windows.FrameworkElement>, включая <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>и <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Дополнительные сведения о свойствах позиционирования, определенных <xref:System.Windows.FrameworkElement>, см. в разделе [Общие сведения о выравнивании, полях и заполнении](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> предоставляет дополнительные свойства, имеющие важную важность при понимании и использовании макета. Свойство <xref:System.Windows.Controls.Panel.Background%2A> используется для заполнения области между границами производного элемента Panel <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A> представляет дочернюю коллекцию элементов, из которых состоит <xref:System.Windows.Controls.Panel>. <xref:System.Windows.Controls.Panel.InternalChildren%2A> представляет содержимое коллекции <xref:System.Windows.Controls.Panel.Children%2A>, а также элементы, созданные привязкой данных. Оба состоят из <xref:System.Windows.Controls.UIElementCollection> дочерних элементов, размещенных в родительской <xref:System.Windows.Controls.Panel>.  
  
 Панель также предоставляет <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> присоединенное свойство, которое можно использовать для достижения многоуровневого порядка в производном <xref:System.Windows.Controls.Panel>. Элементы коллекции <xref:System.Windows.Controls.Panel.Children%2A> Panel с более высоким значением <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> отображаются перед ними с более низким значением <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>. Это особенно удобно для таких панелей, как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.Grid>, которые позволяют дочерним элементам совместно использовать одинаковое пространство координат.  
  
 <xref:System.Windows.Controls.Panel> также определяет метод <xref:System.Windows.Controls.Panel.OnRender%2A>, который можно использовать для переопределения поведения представления <xref:System.Windows.Controls.Panel>по умолчанию.  
  
#### <a name="attached-properties"></a>Вложенные свойства  
 Производные элементы панели широко используют вложенные свойства. Присоединенное свойство — это специализированная форма свойства зависимостей, не имеющая стандартной оболочки для свойства среды CLR. Вложенные свойства имеют специальный синтаксис в языке [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], с которым можно познакомиться в некоторых из следующих примеров.  
  
 Одной из целей вложенного свойства является предоставление возможности дочерним элементам хранить уникальные значения свойства, фактически определенные в родительском элементе. Случаем применения данной возможности является уведомление родительского элемента со стороны дочерних элементов о способе их представления в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что очень полезно при создании макета приложения. Дополнительные сведения см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Производные элементы Panel  
 Многие объекты являются производными от <xref:System.Windows.Controls.Panel>, но не все из них предназначены для использования в качестве поставщиков корневого макета. Существует шесть определенных классов Panel (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>и <xref:System.Windows.Controls.WrapPanel>), разработанных специально для создания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]приложений.  
  
 Каждый элемент панели имеет собственные специальные возможности, представленные в следующей таблице.  
  
|Имя элемента|Панель пользовательского интерфейса?|Description|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Да|Определяет область, в которой можно явно располагать дочерние элементы по координатам относительно области <xref:System.Windows.Controls.Canvas>.|  
|<xref:System.Windows.Controls.DockPanel>|Да|Определяет область, в которой можно горизонтально либо вертикально упорядочивать дочерние элементы относительно друг друга.|  
|<xref:System.Windows.Controls.Grid>|Да|Определяет область с таблицей переменного размера, состоящей из столбцов и строк. Дочерние элементы <xref:System.Windows.Controls.Grid> можно точно располагать с помощью свойства <xref:System.Windows.FrameworkElement.Margin%2A>.|  
|<xref:System.Windows.Controls.StackPanel>|Да|Выравнивает дочерние элементы в одну линию, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|нет|Обрабатывает макет кнопок вкладки в <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|нет|Упорядочивает содержимое в элементе управления <xref:System.Windows.Controls.ToolBar>.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|нет|<xref:System.Windows.Controls.Primitives.UniformGrid> используется для упорядочения дочерних элементов в сетке со всеми равными размерами ячеек.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|нет|Предоставляет базовый класс для панелей, которые могут "виртуализировать" дочерние коллекции.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Да|Упорядочивает и виртуализирует одну строку содержимого, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.WrapPanel>|Да|<xref:System.Windows.Controls.WrapPanel> размещает дочерние элементы в последовательном положении слева направо, разбивая содержимое на следующую строку на границе содержащего поля. Последующее упорядочение происходит последовательно сверху вниз или справа налево в зависимости от значения свойства <xref:System.Windows.Controls.WrapPanel.Orientation%2A>.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Панели пользовательского интерфейса  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], оптимизированных для поддержки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сценариев, доступны шесть классов Panel: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>и <xref:System.Windows.Controls.WrapPanel>. Эти элементы панели являются простыми в использовании, гибкими и достаточно широкими для большинства приложений.  
  
 Каждый производный элемент <xref:System.Windows.Controls.Panel> обрабатывает ограничения размеров по-разному. Понимание того, как <xref:System.Windows.Controls.Panel> обрабатывает ограничения в горизонтальном или вертикальном направлении, может сделать макет более прогнозируемым.  
  
|**Имя панели**|**Размеры по оси x**|**Размеры по оси y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Ограничено содержимым|Ограничено содержимым|  
|<xref:System.Windows.Controls.DockPanel>|Ограничена|Ограничена|  
|<xref:System.Windows.Controls.StackPanel> (вертикальная ориентация)|Ограничена|Ограничено содержимым|  
|<xref:System.Windows.Controls.StackPanel> (горизонтальная ориентация)|Ограничено содержимым|Ограничена|  
|<xref:System.Windows.Controls.Grid>|Ограничена|Ограничено, за исключением случаев, когда <xref:System.Windows.GridUnitType.Auto> применимо к строкам и столбцам|  
|<xref:System.Windows.Controls.WrapPanel>|Ограничено содержимым|Ограничено содержимым|  
  
 С более подробными описаниями и примерами использования каждого из этих элементов можно ознакомиться ниже.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Холст  
 Элемент <xref:System.Windows.Controls.Canvas> обеспечивает размещение содержимого в соответствии с абсолютными координатами *x* и *y* . Элементы могут быть нарисованы в уникальном месте или, если элементы занимают одни координаты, порядок, в котором они отображаются в разметке, определяется порядком, в котором нарисованы эти элементы.  
  
 <xref:System.Windows.Controls.Canvas> предоставляет наиболее гибкую поддержку макета любых <xref:System.Windows.Controls.Panel>. Свойства Height и Width используются для определения области холста, а элементам внутри назначаются абсолютные координаты относительно области родительского <xref:System.Windows.Controls.Canvas>. Четыре вложенных свойства, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, позволяют точно контролировать размещение объектов в <xref:System.Windows.Controls.Canvas>, позволяя разработчику точно располагать и упорядочивать элементы на экране.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Свойство ClipToBounds в элементе Canvas  
 <xref:System.Windows.Controls.Canvas> может размещать дочерние элементы в любой позиции на экране даже в координатах, находящихся за пределами определенного <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A>. Кроме того, на <xref:System.Windows.Controls.Canvas> не влияет размер дочерних элементов. В результате дочерний элемент может перерисовывать другие элементы за пределами ограничивающего прямоугольника родительского <xref:System.Windows.Controls.Canvas>. Поведение <xref:System.Windows.Controls.Canvas> по умолчанию состоит в том, чтобы разрешить прорисовку дочерних элементов вне границ родительского <xref:System.Windows.Controls.Canvas>. Если такое поведение нежелательно, свойству <xref:System.Windows.UIElement.ClipToBounds%2A> может быть присвоено значение `true`. Это приводит к тому, что <xref:System.Windows.Controls.Canvas> обрезается по собственному размеру. <xref:System.Windows.Controls.Canvas> является единственным элементом макета, который позволяет рисовать дочерние элементы за пределами границ.  
  
 Такое поведение графически показано в [примере сравнения свойств ширины](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
#### <a name="defining-and-using-a-canvas"></a>Определение и использование Canvas  
 Экземпляр <xref:System.Windows.Controls.Canvas> можно создать просто с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода. В следующем примере показано, как использовать <xref:System.Windows.Controls.Canvas> для абсолютного позиционирования содержимого. Этот код рисует три квадрата со стороной в 100 пикселей. Первый квадрат — красный и координаты (*x, y*) его левого верхнего угла имеют значение (0, 0). Второй квадрат — зеленый, и его левый верхний угол имеет координаты (100, 100). Он находится ниже и правее первого квадрата. Третий квадрат — синий, его левый верхний угол имеет координаты (50, 50); таким образом, он пересекается с правым нижним углом первого квадрата и левым верхним углом второго. Так как третий квадрат накладывается последним, он будет отображаться поверх первых двух квадратов — то есть пересекающиеся участки принимают цвет третьей фигуры.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Типичный элемент Canvas.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 Элемент <xref:System.Windows.Controls.DockPanel> использует присоединенное <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> свойство, как задано в дочерних элементах содержимого для размещения содержимого вдоль краев контейнера. Если <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> имеет значение <xref:System.Windows.Controls.Dock.Top> или <xref:System.Windows.Controls.Dock.Bottom>, то он размещает дочерние элементы выше или ниже. Если <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> имеет значение <xref:System.Windows.Controls.Dock.Left> или <xref:System.Windows.Controls.Dock.Right>, то он размещает дочерние элементы слева или справа друг от друга. Свойство <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> определяет расположение последнего элемента, добавляемого в качестве дочернего элемента для <xref:System.Windows.Controls.DockPanel>.  
  
 <xref:System.Windows.Controls.DockPanel> можно использовать для размещения группы связанных элементов управления, например набора кнопок. Кроме того, его можно использовать для создания "панели" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]аналогично тому, который находится в Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Изменение размеров в соответствии с содержимым  
 Если свойства <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> не указаны, <xref:System.Windows.Controls.DockPanel> размеры содержимого. Размер может увеличиваться или уменьшаться, чтобы вместить его дочерние элементы. Однако если эти свойства заданы и больше не хватает для следующего указанного дочернего элемента, <xref:System.Windows.Controls.DockPanel> не отображает этот дочерний элемент или последующие дочерние элементы и не измеряет последующие дочерние элементы.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 По умолчанию последний дочерний элемент элемента <xref:System.Windows.Controls.DockPanel> будет заполнять оставшееся нераспределенное пространство. Если это не требуется, задайте для свойства <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> значение `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Определение и использование DockPanel  
 В следующем примере показано, как секционировать пространство с помощью <xref:System.Windows.Controls.DockPanel>. Пять <xref:System.Windows.Controls.Border> элементов добавляются как дочерние элементы родительского <xref:System.Windows.Controls.DockPanel>. Каждый из них использует другое свойство позиционирования <xref:System.Windows.Controls.DockPanel> для разделения пространства. Последний элемент "заполняет" оставшееся незанятое пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Типичный сценарий DockPanel.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Сетка  
 Элемент <xref:System.Windows.Controls.Grid> объединяет функциональные возможности абсолютного позиционирования и табличного элемента управления данными. <xref:System.Windows.Controls.Grid> позволяет легко позиционировать элементы и изменять их стиль. <xref:System.Windows.Controls.Grid> позволяет определять гибкие группирования строк и столбцов, а также предоставляет механизм для совместного использования сведений о размере между несколькими элементами <xref:System.Windows.Controls.Grid>.  
  
#### <a name="how-is-grid-different-from-table"></a>Чем Grid отличается от Table?  
 <xref:System.Windows.Documents.Table> и <xref:System.Windows.Controls.Grid> обладают некоторыми общими функциями, но они лучше всего подходят для различных сценариев. <xref:System.Windows.Documents.Table> предназначен для использования в содержимом нефиксированного формата (Дополнительные сведения о содержимом нефиксированного формата см. в разделе [Общие сведения о документе](../advanced/flow-document-overview.md) ). Сетки лучше всего использовать внутри форм (по сути в любом месте вне потокового содержимого). В <xref:System.Windows.Documents.FlowDocument><xref:System.Windows.Documents.Table> поддерживает поведение нефиксированного содержимого, например разбивку на страницы, перекомпоновку столбцов и выбор содержимого, когда в <xref:System.Windows.Controls.Grid> нет. <xref:System.Windows.Controls.Grid> с другой стороны лучше использовать за пределами <xref:System.Windows.Documents.FlowDocument> по многим причинам, включая <xref:System.Windows.Controls.Grid> добавляет элементы на основе индекса строки и столбца, <xref:System.Windows.Documents.Table> — нет. Элемент <xref:System.Windows.Controls.Grid> позволяет разложить разслойировать дочернее содержимое, разрешив существование в одной "ячейке" более одного элемента. <xref:System.Windows.Documents.Table> не поддерживает многоуровневые слои. Дочерние элементы <xref:System.Windows.Controls.Grid> могут быть абсолютно расположены относительно области их границ "ячейка". <xref:System.Windows.Documents.Table> не поддерживает эту функцию. Наконец, <xref:System.Windows.Controls.Grid> имеет более простой вес, чем <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Поведение столбцов и строк при изменении их размера  
 Столбцы и строки, определенные в <xref:System.Windows.Controls.Grid>, могут воспользоваться преимуществами <xref:System.Windows.GridUnitType.Star> размера для пропорционального распределения оставшегося пространства. Если в качестве высоты или ширины строки или столбца выбрано <xref:System.Windows.GridUnitType.Star>, то этот столбец или строка получает взвешенную долю оставшегося доступного пространства. Это отличается от <xref:System.Windows.GridUnitType.Auto>, которая распределяет пространство равномерно в зависимости от размера содержимого в пределах столбца или строки. Это значение выражается как `*` или `2*` при использовании языка [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. В первом случае строка или столбец будет получать определенное доступное пространство, а во втором случае — в два раза больше. Комбинируя этот метод для пропорционального распределения пространства с <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> значением `Stretch` можно секционировать пространство макета по проценту от пространства экрана. <xref:System.Windows.Controls.Grid> является единственной панелью макета, которая может распределять пространство таким образом.  
  
#### <a name="defining-and-using-a-grid"></a>Определение и использование Grid  
 В следующем примере показано, как создать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] аналогично тому, который находится в диалоговом окне Run, доступном в меню Пуск Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Типичный элемент Grid.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 <xref:System.Windows.Controls.StackPanel> позволяет "Stack" элементы в назначенном направлении. По умолчанию направление стека является вертикальным. Свойство <xref:System.Windows.Controls.StackPanel.Orientation%2A> может использоваться для управления потоком содержимого.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel и DockPanel  
 Хотя <xref:System.Windows.Controls.DockPanel> может также дочерние элементы "Stack", <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel> не создают аналогичные результаты в некоторых сценариях использования. Например, порядок дочерних элементов может повлиять на их размер в <xref:System.Windows.Controls.DockPanel>, но не в <xref:System.Windows.Controls.StackPanel>. Это обусловлено тем, что <xref:System.Windows.Controls.StackPanel> измеряется в направлении <xref:System.Double.PositiveInfinity>, тогда как <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.  
  
 Следующий пример демонстрирует это ключевое различие.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 На этом рисунке видна разница в поведении отрисовки.  
  
 ![Снимок экрана: StackPanel и DockPanel снимок экрана](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Определение и использование StackPanel  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.StackPanel> для создания набора вертикально позиционированных кнопок. Для горизонтального позиционирования задайте для свойства <xref:System.Windows.Controls.StackPanel.Orientation%2A> значение <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Типичный элемент StackPanel.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет вариант элемента <xref:System.Windows.Controls.StackPanel>, который автоматически "виртуализировать" дочернее содержимое с привязкой к данным. В данном контексте слово "виртуализация" означает способ, с помощью которого подмножество элементов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том, что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel> (с помощью функций, предоставляемых <xref:System.Windows.Controls.VirtualizingPanel>) вычисляет видимые элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> из <xref:System.Windows.Controls.ItemsControl> (например, <xref:System.Windows.Controls.ListBox> или <xref:System.Windows.Controls.ListView>), чтобы создавать элементы только для видимых элементов.  
  
 Элемент <xref:System.Windows.Controls.VirtualizingStackPanel> автоматически задается как узел элементов для таких элементов управления, как <xref:System.Windows.Controls.ListBox>. При размещении коллекции, привязанной к данным, содержимое автоматически виртуализовано, пока содержимое находится в пределах границ <xref:System.Windows.Controls.ScrollViewer>. Это значительно повышает производительность при размещении большого числа дочерних элементов.  
  
 В следующей разметке показано, как использовать <xref:System.Windows.Controls.VirtualizingStackPanel> в качестве узла элементов. Присоединенное свойство <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> должно иметь значение `true` (по умолчанию), чтобы виртуализация выполнялась.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> используется для позиционирования дочерних элементов в последовательном положении слева направо, что приводит к разрыву содержимого на следующую строку, когда она достигает края родительского контейнера. Содержимое может быть ориентировано горизонтально или вертикально. <xref:System.Windows.Controls.WrapPanel> удобно использовать для [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] сценариев с простым перетеканием. Его также можно использовать для установления единого размера для всех его дочерних элементов.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.WrapPanel> для отображения элементов управления <xref:System.Windows.Controls.Button>, которые переносятся в оболочку, когда они достигают края контейнера.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Типичный элемент WrapPanel.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Вложенные элементы Panel  
 <xref:System.Windows.Controls.Panel> элементы могут быть вложены друг в друга для создания сложных макетов. Это может оказаться очень полезным в ситуациях, когда один <xref:System.Windows.Controls.Panel> идеально подходит для части [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], но может не соответствовать потребностям другой части [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Практически не существует ограничения объема вложения, которое может поддерживать приложение, но лучше ограничить приложение использованием только тех панелей, которые действительно необходимы для макета. Во многих случаях элемент <xref:System.Windows.Controls.Grid> можно использовать вместо вложенных панелей из-за гибкости в качестве контейнера макета. Это может повысить производительность приложения, убирая ненужные элементы из дерева.  
  
 В следующем примере показано, как создать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который использует преимущества вложенных элементов <xref:System.Windows.Controls.Panel> для достижения определенного макета. В этом конкретном случае элемент <xref:System.Windows.Controls.DockPanel> используется для предоставления структуры [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], а вложенные элементы <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Grid>и <xref:System.Windows.Controls.Canvas> используются для точного позиционирования дочерних элементов в родительском <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Пользовательский интерфейс, использующий вложенные панели.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Пользовательские элементы Panel  
 Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет массив гибких элементов управления макетом, пользовательские поведения макета можно также получить, переопределив методы <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>. Пользовательские изменения размеров и положения могут быть выполнены путем определения нового поведения размещения с помощью этих методов переопределения.  
  
 Аналогичным образом пользовательские поведения макета, основанные на производных классах (например <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.Grid>), можно определить путем переопределения методов <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
 В следующей разметке показано, как создать пользовательский элемент <xref:System.Windows.Controls.Panel>. Эта новая <xref:System.Windows.Controls.Panel>, определенная как `PlotPanel`, поддерживает размещение дочерних элементов с помощью жестко заданных координат *x* и *y* . В этом примере элемент <xref:System.Windows.Shapes.Rectangle> (не показан) располагается в точке построения 50 (*x*) и 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Более сложные реализации пользовательских панелей можно найти в разделе [примера создания пользовательской панели с переносом содержимого](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Поддержка локализации и глобализации  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает ряд возможностей для создания локализуемого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Все элементы панели изначально поддерживают свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A>, которое можно использовать для динамического повторного перетекания содержимого в зависимости от языкового стандарта пользователя или параметров языка. Дополнительные сведения см. в разделе <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Свойство <xref:System.Windows.Window.SizeToContent%2A> предоставляет механизм, позволяющий разработчикам приложений предвидеть потребности локализованных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Используя значение <xref:System.Windows.SizeToContent.WidthAndHeight> этого свойства, родительский <xref:System.Windows.Window> всегда динамически обновляется в соответствии с содержимым и не ограничивается искусственным ограничением высоты или ширины.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>и <xref:System.Windows.Controls.StackPanel> являются хорошим выбором для локализуемых [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Однако <xref:System.Windows.Controls.Canvas> не является хорошим выбором, так как он размещает содержимое абсолютно, что затрудняет локализацию.  
  
 Дополнительные сведения о создании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений с помощью локализуемых пользовательских интерфейсов см. в разделе [Обзор использования автоматической разметки](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Пошаговое руководство. Создание первого классического приложения WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Пример коллекции макетов WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Макет](../advanced/layout.md)
- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
- [Общие сведения о свойствах Alignment, Margin, Padding](../advanced/alignment-margins-and-padding-overview.md)
- [Пример создания пользовательской панели с переносом содержимого](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Общие сведения о присоединенных свойствах](../advanced/attached-properties-overview.md)
- [Обзор использования автоматической разметки](../advanced/use-automatic-layout-overview.md)
- [Разметка и разработка](../advanced/optimizing-performance-layout-and-design.md)
