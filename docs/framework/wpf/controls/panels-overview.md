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
ms.openlocfilehash: 7810bfbf4f5bedf51e0797a4b9017f589e0b0a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187579"
---
# <a name="panels-overview"></a>Общие сведения о панелях
<xref:System.Windows.Controls.Panel>элементы являются компонентами, которые контролируют визуализацию элементов– их размер и размеры, их положение и расположение их содержимого ребенка. Предоставляет [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ряд предопределенных <xref:System.Windows.Controls.Panel> элементов, а также <xref:System.Windows.Controls.Panel> возможность построения пользовательских элементов.  
  
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
 <xref:System.Windows.Controls.Panel>является базовым классом для всех элементов, которые обеспечивают поддержку макета в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Полученные <xref:System.Windows.Controls.Panel> элементы используются для [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] позиционирования и расположения элементов и кода.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает полный набор реализаций производных панели, позволяющих использовать множество сложных макетов. Эти производные классы предоставляют свойства и методы, с помощью которых реализуется большинство стандартных сценариев [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Разработчики, которые не могут найти поведение расположения ребенка, отвечающее <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> их потребностям, могут создавать новые макеты, переопределяя методы. Дополнительные сведения о поведении пользовательских макетов см. в разделе [Пользовательские элементы Panel](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Общие члены элементов Panel  
 Все <xref:System.Windows.Controls.Panel> элементы поддерживают базовые свойства размера <xref:System.Windows.FrameworkElement>и <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A>позиционирования, определяемые, включая, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>и. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Для получения дополнительной информации <xref:System.Windows.FrameworkElement>о свойствах позиционирования, определяемых по сведениям, см. [Обзор выравнивания, маржи и Padding.](../advanced/alignment-margins-and-padding-overview.md)  
  
 <xref:System.Windows.Controls.Panel>предоставляет дополнительные свойства, которые имеют решающее значение в понимании и использовании макета. Свойство <xref:System.Windows.Controls.Panel.Background%2A> используется для заполнения области между границами производного <xref:System.Windows.Media.Brush>элемента панели с . <xref:System.Windows.Controls.Panel.Children%2A>представляет детскую коллекцию <xref:System.Windows.Controls.Panel> элементов, из них состоит. <xref:System.Windows.Controls.Panel.InternalChildren%2A>представляет содержание коллекции <xref:System.Windows.Controls.Panel.Children%2A> плюс те члены, генерируемые связыванием данных. Оба состоят <xref:System.Windows.Controls.UIElementCollection> из элементов ребенка, размещенных в родительском. <xref:System.Windows.Controls.Panel>  
  
 Панель также предоставляет <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> прилагаемое свойство, которое может быть <xref:System.Windows.Controls.Panel>использовано для достижения многоуровневого порядка в произвесостояниии. Члены <xref:System.Windows.Controls.Panel.Children%2A> коллекции панели с <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> более высокой стоимостью появляются перед теми, кто имеет более низкое <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> значение. Это особенно полезно для <xref:System.Windows.Controls.Canvas> таких <xref:System.Windows.Controls.Grid> панелей, как и которые позволяют детям совместно готировать пространство координат.  
  
 <xref:System.Windows.Controls.Panel>также определяет <xref:System.Windows.Controls.Panel.OnRender%2A> метод, который может быть использован для переопределения <xref:System.Windows.Controls.Panel>поведения представления по умолчанию .  
  
#### <a name="attached-properties"></a>Вложенные свойства  
 Производные элементы панели широко используют вложенные свойства. Прилагаемое свойство является специализированной формой свойства зависимости, которая не имеет обычного общего языка времени выполнения (CLR) свойство "обертка". Вложенные свойства имеют специальный синтаксис в языке [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], с которым можно познакомиться в некоторых из следующих примеров.  
  
 Одной из целей вложенного свойства является предоставление возможности дочерним элементам хранить уникальные значения свойства, фактически определенные в родительском элементе. Случаем применения данной возможности является уведомление родительского элемента со стороны дочерних элементов о способе их представления в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что очень полезно при создании макета приложения. Дополнительные сведения см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Производные элементы Panel  
 Многие объекты <xref:System.Windows.Controls.Panel>вытекают из, но не все из них предназначены для использования в качестве корневой макет амев. Есть шесть определенных<xref:System.Windows.Controls.Canvas>классов <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>панели <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.VirtualizingStackPanel>(, <xref:System.Windows.Controls.WrapPanel>, , , и), которые предназначены специально для создания приложения. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
 Каждый элемент панели имеет собственные специальные возможности, представленные в следующей таблице.  
  
|Имя элемента|Панель пользовательского интерфейса?|Описание|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Да|Определяет область, в которой можно явно позиционировать элементы <xref:System.Windows.Controls.Canvas> ребенка по координатам относительно области.|  
|<xref:System.Windows.Controls.DockPanel>|Да|Определяет область, в которой можно горизонтально либо вертикально упорядочивать дочерние элементы относительно друг друга.|  
|<xref:System.Windows.Controls.Grid>|Да|Определяет область с таблицей переменного размера, состоящей из столбцов и строк. Элементы ребенка <xref:System.Windows.Controls.Grid> можно расположить именно <xref:System.Windows.FrameworkElement.Margin%2A> с помощью свойства.|  
|<xref:System.Windows.Controls.StackPanel>|Да|Выравнивает дочерние элементы в одну линию, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|нет|Обрабатывает макет кнопок вкладок <xref:System.Windows.Controls.TabControl>в .|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|нет|Организует содержимое <xref:System.Windows.Controls.ToolBar> в элементе управления.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|нет|<xref:System.Windows.Controls.Primitives.UniformGrid>используется для организации детей в сетке со всеми равными размерами клеток.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|нет|Предоставляет базовый класс для панелей, которые могут "виртуализировать" дочерние коллекции.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Да|Упорядочивает и виртуализирует одну строку содержимого, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.WrapPanel>|Да|<xref:System.Windows.Controls.WrapPanel>позиционирует элементы ребенка в последовательном положении слева направо, разбивая содержимое следующей строке на краю содержащего окна. Последующий заказ происходит последовательно сверху вниз или справа налево, в зависимости <xref:System.Windows.Controls.WrapPanel.Orientation%2A> от стоимости имущества.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Панели пользовательского интерфейса  
 Есть шесть групповых [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] классов, доступных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в <xref:System.Windows.Controls.Canvas>том, что <xref:System.Windows.Controls.VirtualizingStackPanel>оптимизированы для поддержки сценариев: , <xref:System.Windows.Controls.WrapPanel> <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, и . Эти элементы панели являются простыми в использовании, гибкими и достаточно широкими для большинства приложений.  
  
 Каждый <xref:System.Windows.Controls.Panel> полученный элемент по-разному относится к ограничениям размеров. Понимание того, как ручки <xref:System.Windows.Controls.Panel> ограничены в горизонтальном или вертикальном направлении, может сделать макет более предсказуемым.  
  
|**Название панели**|**Размеры по оси x**|**Размеры по оси y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Ограничено содержимым|Ограничено содержимым|  
|<xref:System.Windows.Controls.DockPanel>|Ограничено|Ограничено|  
|<xref:System.Windows.Controls.StackPanel>(Вертикальная ориентация)|Ограничено|Ограничено содержимым|  
|<xref:System.Windows.Controls.StackPanel>(Горизонтальная ориентация)|Ограничено содержимым|Ограничено|  
|<xref:System.Windows.Controls.Grid>|Ограничено|Ограничения, за исключением <xref:System.Windows.GridUnitType.Auto> случаев, когда применяется к строкам и столбцы|  
|<xref:System.Windows.Controls.WrapPanel>|Ограничено содержимым|Ограничено содержимым|  
  
 С более подробными описаниями и примерами использования каждого из этих элементов можно ознакомиться ниже.  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>Холст  
 Элемент <xref:System.Windows.Controls.Canvas> позволяет позиционировать содержимое в соответствии с абсолютными *x-* и y-координатами. *y-* Элементы могут быть нарисованы в уникальном месте или, если элементы занимают одни координаты, порядок, в котором они отображаются в разметке, определяется порядком, в котором нарисованы эти элементы.  
  
 <xref:System.Windows.Controls.Canvas>обеспечивает наиболее гибкую <xref:System.Windows.Controls.Panel>поддержку макета любого . Свойства высоты и ширины используются для определения области холста, а элементам внутри присваиваются абсолютные координаты относительно области родительского. <xref:System.Windows.Controls.Canvas> Четыре прилагаемых <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>свойства, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>и , <xref:System.Windows.Controls.Canvas>позволяют тонко контролировать размещение объекта в рамках, что позволяет разработчику позиционировать и расположить элементы именно на экране.  
  
#### <a name="cliptobounds-within-a-canvas"></a>Свойство ClipToBounds в элементе Canvas  
 <xref:System.Windows.Controls.Canvas>может расположить элементы ребенка в любом положении на экране, даже при координатах, которые находятся вне его собственного определены <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A>. Кроме <xref:System.Windows.Controls.Canvas> того, не зависит от размера своих детей. В результате, элемент ребенка перечеркнет другие элементы за пределами <xref:System.Windows.Controls.Canvas>связующего прямоугольника родителя. Поведение по умолчанию <xref:System.Windows.Controls.Canvas> является тем, чтобы позволить детям <xref:System.Windows.Controls.Canvas>быть обращены за пределами родительского . Если такое поведение является <xref:System.Windows.UIElement.ClipToBounds%2A> нежелательным, `true`свойство может быть установлено. Это <xref:System.Windows.Controls.Canvas> приводит к клипу до своего размера. <xref:System.Windows.Controls.Canvas>является единственным элементом макета, который позволяет детям быть обращено за его пределами.  
  
 Такое поведение графически показано в [примере сравнения свойств ширины](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
#### <a name="defining-and-using-a-canvas"></a>Определение и использование Canvas  
 A <xref:System.Windows.Controls.Canvas> может быть мгновенно просто [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] с помощью или кода. Следующий пример показывает, <xref:System.Windows.Controls.Canvas> как использовать для абсолютного размещения контента. Этот код рисует три квадрата со стороной в 100 пикселей. Первый квадрат — красный и координаты (*x, y*) его левого верхнего угла имеют значение (0, 0). Второй квадрат — зеленый, и его левый верхний угол имеет координаты (100, 100). Он находится ниже и правее первого квадрата. Третий квадрат — синий, его левый верхний угол имеет координаты (50, 50); таким образом, он пересекается с правым нижним углом первого квадрата и левым верхним углом второго. Так как третий квадрат накладывается последним, он будет отображаться поверх первых двух квадратов — то есть пересекающиеся участки принимают цвет третьей фигуры.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент холста.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 Элемент <xref:System.Windows.Controls.DockPanel> использует <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> прикрепленное свойство, установленное в элементах содержимого ребенка, для размещения содержимого по краям контейнера. Когда <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> установлен <xref:System.Windows.Controls.Dock.Top> на <xref:System.Windows.Controls.Dock.Bottom>или , он позиционирует элементы ребенка выше или ниже друг друга. Когда <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> установлен <xref:System.Windows.Controls.Dock.Left> на <xref:System.Windows.Controls.Dock.Right>или, он позиционирует элементы ребенка влево или вправо друг от друга. Свойство <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> определяет положение конечного элемента, добавленного <xref:System.Windows.Controls.DockPanel>как ребенок .  
  
 Можно использовать <xref:System.Windows.Controls.DockPanel> для размещения группы связанных элементов управления, таких как набор кнопок. Кроме того, вы можете использовать его для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]создания "панированных" , аналогичных тем, которые можно найти в Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Изменение размеров в зависимости от содержимого  
 Если <xref:System.Windows.FrameworkElement.Height%2A> его <xref:System.Windows.FrameworkElement.Width%2A> и свойства <xref:System.Windows.Controls.DockPanel> не указаны, размеры его содержания. Размер может увеличиваться или уменьшаться, чтобы вместить его дочерние элементы. Однако, когда эти свойства указаны и больше нет места <xref:System.Windows.Controls.DockPanel> для следующего указанного элемента ребенка, не отображает этот элемент ребенка или последующие элементы ребенка и не измеряет последующие элементы ребенка.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 По умолчанию последний <xref:System.Windows.Controls.DockPanel> элемент элемента «заполняет» оставшееся нераспределенное пространство. Если такое поведение не <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> желательно, `false`установите свойство.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Определение и использование DockPanel  
 Ниже приведен приведенпримерк, как расстать <xref:System.Windows.Controls.DockPanel>пространство с помощью . Пять <xref:System.Windows.Controls.Border> элементов добавляются как <xref:System.Windows.Controls.DockPanel>дети одного из родителей. Каждый использует различное свойство <xref:System.Windows.Controls.DockPanel> позиционирования пространства раздела. Последний элемент "заполняет" оставшееся незанятое пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный сценарий DockPanel.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Сетка  
 Элемент <xref:System.Windows.Controls.Grid> объединяет функциональность абсолютного позиционирования и табликового управления данными. A <xref:System.Windows.Controls.Grid> позволяет легко позиционировать и стиль элементов. <xref:System.Windows.Controls.Grid>позволяет определить гибкие группы строк и столбцов и даже предоставляет механизм <xref:System.Windows.Controls.Grid> обмена информацией о размерах между несколькими элементами.  
  
#### <a name="how-is-grid-different-from-table"></a>Чем Grid отличается от Table?  
 <xref:System.Windows.Documents.Table>и <xref:System.Windows.Controls.Grid> имеют некоторые общие функциональные возможности, но каждый из них лучше всего подходит для различных сценариев. A <xref:System.Windows.Documents.Table> предназначен для использования в содержимом потока (см. [Обзор документов потока](../advanced/flow-document-overview.md) для получения дополнительной информации о содержимом потока). Сетки лучше всего использовать внутри форм (по сути, в любом месте вне потокового содержимого). <xref:System.Windows.Documents.FlowDocument>В рамках, <xref:System.Windows.Documents.Table> поддерживает поведение содержимого потока, как pagination, колонка reflow, и выбор содержимого в то время как <xref:System.Windows.Controls.Grid> нет. A <xref:System.Windows.Controls.Grid> с другой стороны, лучше <xref:System.Windows.Documents.FlowDocument> всего использовать <xref:System.Windows.Controls.Grid> за пределами по многим <xref:System.Windows.Documents.Table> причинам, включая добавленные элементы, основанные на строке и индексе столбца, не делает. Элемент <xref:System.Windows.Controls.Grid> позволяет наслоение содержимого ребенка, позволяя более чем одному элементу существовать в одной "клетке". <xref:System.Windows.Documents.Table>не поддерживает наслоение. Детские элементы а <xref:System.Windows.Controls.Grid> могут быть абсолютно расположены относительно области их "клеточных" границ. <xref:System.Windows.Documents.Table>не поддерживает эту функцию. Наконец, <xref:System.Windows.Controls.Grid> легче <xref:System.Windows.Documents.Table>вес, чем .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Поведение столбцов и строк при изменении их размера  
 Столбцы и строки, <xref:System.Windows.Controls.Grid> определенные <xref:System.Windows.GridUnitType.Star> в пределах может воспользоваться размеров для того, чтобы распределить оставшееся пространство пропорционально. При <xref:System.Windows.GridUnitType.Star> выборе высоты или ширины строки или столбца этот столбец или строка получает взвешенную долю оставшегося доступного пространства. Это в отличие <xref:System.Windows.GridUnitType.Auto>от , который будет распределять пространство равномерно в зависимости от размера содержимого в столбце или строке. Это значение выражается как `*` или `2*` при использовании языка [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. В первом случае строка или столбец будет получать определенное доступное пространство, а во втором случае — в два раза больше. Объединив этот метод пропорционально распределить <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> пространство `Stretch` с значением <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и значение его можно разделить пространство макета на процент пространства экрана. <xref:System.Windows.Controls.Grid>является единственной панелью макета, которая может распределять пространство таким образом.  
  
#### <a name="defining-and-using-a-grid"></a>Определение и использование Grid  
 Ниже приводится следующий пример, как создать аналогичный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] диалог, доступный в диалоге Run, доступном в меню Windows Start.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент сетки.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 A <xref:System.Windows.Controls.StackPanel> позволяет "стек" элементов в назначенном направлении. По умолчанию направление стека является вертикальным. Свойство <xref:System.Windows.Controls.StackPanel.Orientation%2A> может использоваться для управления потоком содержимого.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel vs. DockPanel  
 Хотя <xref:System.Windows.Controls.DockPanel> также может "стек" элементы ребенка, <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel> не дают аналогичных результатов в некоторых сценариях использования. Например, порядок элементов ребенка может <xref:System.Windows.Controls.DockPanel> повлиять <xref:System.Windows.Controls.StackPanel>на их размер в, но не в . Это потому, что <xref:System.Windows.Controls.StackPanel> меры в <xref:System.Double.PositiveInfinity>направлении <xref:System.Windows.Controls.DockPanel> укладки на , в то время как меры только доступный размер.  
  
 Следующий пример демонстрирует это ключевое различие.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 На этом рисунке видна разница в поведении отрисовки.  
  
 ![Снимок экрана: сравнение снимков экранов StackPanel и DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Определение и использование StackPanel  
 В следующем примере показано, <xref:System.Windows.Controls.StackPanel> как использовать набор вертикально расположенных кнопок. Для горизонтального позиционирования установите свойство <xref:System.Windows.Controls.StackPanel.Orientation%2A> на <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент StackPanel.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также обеспечивает вариацию <xref:System.Windows.Controls.StackPanel> элемента, который автоматически "виртуализирует" содержимое ребенка, привязанное к данным. В данном контексте слово "виртуализация" означает способ, с помощью которого подмножество элементов создается из большего количества элементов данных в зависимости от того, какие из элементов отображаются на экране. Как для памяти, так и для процессора затратно создавать большое число элементов пользовательского интерфейса, при том что только несколько из них могут отображаться на экране одновременно. <xref:System.Windows.Controls.VirtualizingStackPanel>(через функциональность, <xref:System.Windows.Controls.VirtualizingPanel>предоставляемую ) вычисляет видимые <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>элементы и работает с <xref:System.Windows.Controls.ItemContainerGenerator> <xref:System.Windows.Controls.ItemsControl> (например, или ) только создавать элементы для видимых элементов.  
  
 Элемент <xref:System.Windows.Controls.VirtualizingStackPanel> автоматически устанавливается как элементы, хост для элементов управления, <xref:System.Windows.Controls.ListBox>такие как. При хостинге сбора связанных данных, содержание автоматически виртуализируется, до тех пор, как содержание находится в пределах <xref:System.Windows.Controls.ScrollViewer>. Это значительно повышает производительность при размещении большого числа дочерних элементов.  
  
 Следующая разметка демонстрирует, <xref:System.Windows.Controls.VirtualizingStackPanel> как использовать в качестве элемента хоста. Прилагаемое <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> свойство `true` должно быть настроено (по умолчанию) для виртуализации.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>используется для размещения элементов ребенка в последовательном положении слева направо, нарушая содержимое следующей строки, когда она достигает края родительского контейнера. Содержимое может быть ориентировано горизонтально или вертикально. <xref:System.Windows.Controls.WrapPanel>полезен для простых сценариев. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Его также можно использовать для установления единого размера для всех его дочерних элементов.  
  
 В следующем примере показано, <xref:System.Windows.Controls.WrapPanel> как <xref:System.Windows.Controls.Button> создать элементы управления, которые обертываются, когда они достигают края контейнера.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Обычный элемент WrapPanel.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Вложенные элементы Panel  
 <xref:System.Windows.Controls.Panel>элементы могут быть вложены друг в друга для того, чтобы производить сложные макеты. Это может оказаться очень <xref:System.Windows.Controls.Panel> полезным в ситуациях, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]когда один идеально подходит для части, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]но не может удовлетворить потребности другой части .  
  
 Практически не существует ограничения объема вложения, которое может поддерживать приложение, но лучше ограничить приложение использованием только тех панелей, которые действительно необходимы для макета. Во многих случаях <xref:System.Windows.Controls.Grid> элемент можно использовать вместо вложенных панелей из-за его гибкости в качестве контейнера для компоновки. Это может повысить производительность приложения, убирая ненужные элементы из дерева.  
  
 Следующий пример показывает, как [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] создать, который <xref:System.Windows.Controls.Panel> использует вложенные элементы для достижения конкретного макета. В данном конкретном <xref:System.Windows.Controls.DockPanel> случае элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] используется для обеспечения <xref:System.Windows.Controls.StackPanel> структуры <xref:System.Windows.Controls.Grid>и <xref:System.Windows.Controls.Canvas> вложенных элементов, а также <xref:System.Windows.Controls.DockPanel>элементов, используемых для размещения элементов ребенка точно внутри родительского.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Скомпилированное приложение возвращает новый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит следующим образом.  
  
 ![Пользовательский интерфейс, использующий вложенные панели.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Пользовательские элементы Panel  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] то время как обеспечивает массив гибких элементов управления макетом, <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> пользовательские поведения макета также может быть достигнуто путем переопределения и методов. Пользовательские изменения размеров и положения могут быть выполнены путем определения нового поведения размещения с помощью этих методов переопределения.  
  
 Аналогичным образом, пользовательские поведения макета на <xref:System.Windows.Controls.Canvas> основе <xref:System.Windows.Controls.Grid>производных классов (таких как или) могут быть определены путем переопределения их <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> и <xref:System.Windows.FrameworkElement.MeasureOverride%2A> методов.  
  
 Следующая разметка демонстрирует, как <xref:System.Windows.Controls.Panel> создать пользовательский элемент. Этот <xref:System.Windows.Controls.Panel>новый, `PlotPanel`определяемый как, поддерживает позиционирование элементов ребенка с помощью жестко закодированных *х-* и y-координат. *y-* В этом примере <xref:System.Windows.Shapes.Rectangle> элемент (не показан) расположен в точке участка 50 *(x),* и 50 *(y).*  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Более сложные реализации пользовательских панелей можно найти в разделе [примера создания пользовательской панели с переносом содержимого](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Поддержка локализации и глобализации  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает ряд возможностей для создания локализуемого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Все элементы панели <xref:System.Windows.FrameworkElement.FlowDirection%2A> по своей словам поддерживают свойство, которое может быть использовано для динамического повторного потока содержимого на основе языковых или языковых настроек пользователя. Дополнительные сведения см. в разделе <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Свойство <xref:System.Windows.Window.SizeToContent%2A> предоставляет механизм, который позволяет разработчикам [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]приложений предвидеть потребности локализованных. Используя <xref:System.Windows.SizeToContent.WidthAndHeight> значение этого свойства, <xref:System.Windows.Window> родитель всегда размерирует динамически, чтобы соответствовать содержимому и не ограничен искусственными ограничениями высоты или ширины.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>и <xref:System.Windows.Controls.StackPanel> все хорошие выборы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]для локального . <xref:System.Windows.Controls.Canvas>не является хорошим выбором, однако, потому что он позиционирует содержание абсолютно, что затрудняет локализацию.  
  
 Для получения дополнительной [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] информации о создании приложений с локальными [Use Automatic Layout Overview](../advanced/use-automatic-layout-overview.md)пользовательскими интерфейсами (UI) см.  
  
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
