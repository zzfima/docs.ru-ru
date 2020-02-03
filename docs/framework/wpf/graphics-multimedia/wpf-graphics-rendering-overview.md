---
title: Общие сведения о отрисовке графики
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rendering
- rendering graphics [WPF]
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
ms.openlocfilehash: 103d086857bce8ae0960452bb92a69b68dc49dfa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744806"
---
# <a name="wpf-graphics-rendering-overview"></a>Общие сведения об отрисовке графики в WPF
В этом разделе приведены общие сведения о визуальном слое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В нем основное внимание уделяется роли класса <xref:System.Windows.Media.Visual> для поддержки отрисовки в модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="role_of_visual_object"></a>   
## <a name="role-of-the-visual-object"></a>Роль визуального объекта  
 Класс <xref:System.Windows.Media.Visual> является базовой абстракцией, из которой наследуется каждый объект <xref:System.Windows.FrameworkElement>. Эта абстракция также служит точкой входа для написания новых элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и во многих случаях ее можно рассматривать в качестве дескриптора окна (HWND) в модели приложения Win32.  
  
 Объект <xref:System.Windows.Media.Visual> является основным [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектом, первичной ролью которого является предоставление поддержки отрисовки. Элементы управления пользовательского интерфейса, такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TextBox>, являются производными от класса <xref:System.Windows.Media.Visual> и используют его для сохранения данных отрисовки. Объект <xref:System.Windows.Media.Visual> обеспечивает поддержку следующих объектов:  
  
- Отображение выходных данных: визуализация сохраненного, сериализованного содержимого визуального элемента.  
  
- Преобразование: поддерживает преобразование визуального элемента.  
  
- Отсечение: позволяет указать область отсечения для визуального элемента.  
  
- Проверка нажатия: определяет, содержится ли координата или геометрическая фигура в границах визуального объекта.  
  
- Вычисление ограничивающего прямоугольника: определение ограничивающего прямоугольника визуального объекта.  
  
 Однако объект <xref:System.Windows.Media.Visual> не включает поддержку функций, не связанных с отрисовкой, таких как:  
  
- Обработка событий  
  
- Макет  
  
- Стили  
  
- привязка данных,  
  
- Глобализация  
  
 <xref:System.Windows.Media.Visual> предоставляется как открытый абстрактный класс, от которого должны наследоваться дочерние классы. На следующем рисунке показана иерархия визуальных объектов, которые предоставляются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 ![Схема классов, производных от Visual-объекта](./media/wpf-graphics-rendering-overview/classes-derived-visual-object.png)    
  
### <a name="drawingvisual-class"></a>Класс DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> — это упрощенный класс рисования, используемый для отрисовки фигур, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов. <xref:System.Windows.Media.DrawingVisual> можно использовать для создания пользовательского визуального объекта. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](using-drawingvisual-objects.md).  
  
### <a name="viewport3dvisual-class"></a>Класс Viewport3DVisual  
 <xref:System.Windows.Media.Media3D.Viewport3DVisual> предоставляет мост между 2D-<xref:System.Windows.Media.Visual> и <xref:System.Windows.Media.Media3D.Visual3D>ными объектами. Класс <xref:System.Windows.Media.Media3D.Visual3D> является базовым классом для всех трехмерных визуальных элементов. Для <xref:System.Windows.Media.Media3D.Viewport3DVisual> требуется определить <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> значение и <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> значение. Камера позволяет просмотреть сцену. Окно просмотра определяет, где проекция преобразуется в двумерную поверхность. Дополнительные сведения о трехмерной графике в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Общие сведения о трехмерной графике](3-d-graphics-overview.md).  
  
### <a name="containervisual-class"></a>Класс ContainerVisual  
 Класс <xref:System.Windows.Media.ContainerVisual> используется в качестве контейнера для коллекции объектов <xref:System.Windows.Media.Visual>. Класс <xref:System.Windows.Media.DrawingVisual> является производным от класса <xref:System.Windows.Media.ContainerVisual>, что позволяет ему содержать коллекцию визуальных объектов.  
  
### <a name="drawing-content-in-visual-objects"></a>Рисование содержимого в объектах Visual  
 Объект <xref:System.Windows.Media.Visual> сохраняет свои данные рендеринга в виде **списка инструкций векторной графики**. Каждый элемент в списке инструкций представляет низкоуровневый набор графических данных и связанных ресурсов в сериализованном формате. Существует четыре различных типа данных отрисовки, которые могут включать графическое содержимое.  
  
|Тип содержимого для отрисовки|Description|  
|--------------------------|-----------------|  
|Векторная графика|Представляет данные векторной графики и все связанные <xref:System.Windows.Media.Brush> и <xref:System.Windows.Media.Pen> сведения.|  
|Образ —|Представляет изображение в регионе, определенном <xref:System.Windows.Rect>.|  
|Глиф|Представляет рисунок, который визуализирует <xref:System.Windows.Media.GlyphRun>, который представляет собой последовательность глифов из указанного ресурса шрифта. Таким образом представляется текст.|  
|Видеоролик|Представляет рисунок, отображающий видео.|  
  
 <xref:System.Windows.Media.DrawingContext> позволяет заполнять <xref:System.Windows.Media.Visual> визуальным содержимым. При использовании команд рисования <xref:System.Windows.Media.DrawingContext> объекта фактически сохраняется набор данных рендеринга, который впоследствии будет использоваться графической системой. Вы не рисуете на экране в режиме реального времени.  
  
 При создании элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такого как <xref:System.Windows.Controls.Button>, элемент управления неявно создает данные отрисовки для рисования самих себя. Например, установка свойства <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Button> приводит к тому, что элемент управления будет сохранять представление глифа в виде отрисовки.  
  
 <xref:System.Windows.Media.Visual> описывает его содержимое как один или несколько объектов <xref:System.Windows.Media.Drawing>, содержащихся в <xref:System.Windows.Media.DrawingGroup>. <xref:System.Windows.Media.DrawingGroup> также описывает маски непрозрачности, преобразования, эффекты точечных рисунков и другие операции, применяемые к его содержимому. <xref:System.Windows.Media.DrawingGroup> операции применяются в следующем порядке при отображении содержимого: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, а затем <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 На следующем рисунке показан порядок, в котором операции <xref:System.Windows.Media.DrawingGroup> применяются во время последовательности отрисовки.  
  
 ![Порядок операций для DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Порядок операций для DrawingGroup  
  
 Дополнительные сведения см. в разделе [Обзор объектов Drawing](drawing-objects-overview.md).  
  
#### <a name="drawing-content-at-the-visual-layer"></a>Отображение содержимого на визуальном уровне  
 Вы никогда не создаете экземпляр <xref:System.Windows.Media.DrawingContext>напрямую; Однако можно получить контекст рисования из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>. Следующий пример извлекает <xref:System.Windows.Media.DrawingContext> из <xref:System.Windows.Media.DrawingVisual> и использует его для рисования прямоугольника.  
  
 [!code-csharp[drawingvisualsample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### <a name="enumerating-drawing-content-at-the-visual-layer"></a>Перечисление содержимого рисования на визуальном уровне  
 В дополнение к другим применениям <xref:System.Windows.Media.Drawing> объекты также предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
> [!NOTE]
> При перечислении содержимого визуального элемента извлекаются <xref:System.Windows.Media.Drawing> объекты, а не базовое представление данных рендеринга в виде списка инструкций векторной графики.  
  
 В следующем примере используется метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> для получения значения <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.Visual> и его перечисления.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## <a name="how-visual-objects-are-used-to-build-controls"></a>Использование визуальных объектов для создания элементов управления  
 Многие из объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] состоят из других визуальных объектов, то есть они могут содержать различные иерархии объектов-потомков. Многие элементы пользовательского интерфейса в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], например элементы управления, состоят из нескольких визуальных объектов, которые представляют различные типы прорисовываемых элементов. Например, элемент управления <xref:System.Windows.Controls.Button> может содержать ряд других объектов, включая <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter>и <xref:System.Windows.Controls.TextBlock>.  
  
 В следующем коде показан элемент управления <xref:System.Windows.Controls.Button>, определенный в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Если необходимо перечислить визуальные объекты, составляющие элемент управления <xref:System.Windows.Controls.Button> по умолчанию, можно найти иерархию визуальных объектов, показанную ниже:  
  
 ![Схема иерархии визуального дерева](./media/wpf-graphics-rendering-overview/visual-object-diagram.gif) 
  
 Элемент управления <xref:System.Windows.Controls.Button> содержит элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, который, в свою очередь, содержит элемент <xref:System.Windows.Controls.ContentPresenter>. Элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> отвечает за Рисование границы и фона для <xref:System.Windows.Controls.Button>. Элемент <xref:System.Windows.Controls.ContentPresenter> отвечает за отображение содержимого <xref:System.Windows.Controls.Button>. В этом случае, поскольку отображается текст, элемент <xref:System.Windows.Controls.ContentPresenter> содержит элемент <xref:System.Windows.Controls.TextBlock>. Тот факт, что элемент управления <xref:System.Windows.Controls.Button> использует <xref:System.Windows.Controls.ContentPresenter>, означает, что содержимое может быть представлено другими элементами, например <xref:System.Windows.Controls.Image> или геометрией, например <xref:System.Windows.Media.EllipseGeometry>.  
  
### <a name="control-templates"></a>Шаблоны элементов управления  
 Ключом к раскрытию элемента управления в иерархии элементов управления является <xref:System.Windows.Controls.ControlTemplate>. Шаблон элемента управления определяет визуальную иерархию по умолчанию для элемента управления. При явной ссылке на элемент управления вы неявно ссылаетесь на его визуальную иерархию. Для изменения внешнего вида элемента управления вы можете переопределить значения по умолчанию для шаблона элемента управления. Например, можно изменить значение цвета фона элемента управления <xref:System.Windows.Controls.Button> таким образом, чтобы оно использовало значение цвета линейного градиента вместо сплошного значения цвета. Дополнительные сведения см. в разделе [Стили и шаблоны кнопок](../controls/button-styles-and-templates.md).  
  
 Элемент пользовательского интерфейса, например элемент управления <xref:System.Windows.Controls.Button>, содержит несколько списков инструкций векторной графики, описывающих все определение отрисовки элемента управления. В следующем коде показан элемент управления <xref:System.Windows.Controls.Button>, определенный в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Если необходимо перечислить визуальные объекты и списки инструкций векторной графики, составляющие элемент управления <xref:System.Windows.Controls.Button>, можно найти иерархию объектов, показанную ниже:  
  
 ![Схема визуального дерева и отрисовки данных](./media/wpf-graphics-rendering-overview/visual-tree-rendering-data.png)  
  
 Элемент управления <xref:System.Windows.Controls.Button> содержит элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, который, в свою очередь, содержит элемент <xref:System.Windows.Controls.ContentPresenter>. Элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> отвечает за рисование всех дискретных графических элементов, составляющих границу и фон кнопки. Элемент <xref:System.Windows.Controls.ContentPresenter> отвечает за отображение содержимого <xref:System.Windows.Controls.Button>. В этом случае, поскольку отображается изображение, элемент <xref:System.Windows.Controls.ContentPresenter> содержит элемент <xref:System.Windows.Controls.Image>.  
  
 При работе с иерархией визуальных объектов и списками инструкций векторной графики следует учитывать несколько моментов.  
  
- Порядок иерархии представляет порядок отрисовки графической информации. От корневого визуального элемента дочерние элементы распространяются слева направо и сверху вниз. Если у элемента есть дочерние визуальные элементы, они распространяются до элементов того же уровня.  
  
- Неконечные элементы узла в иерархии, такие как <xref:System.Windows.Controls.ContentPresenter>, используются для хранения дочерних элементов — они не содержат списки инструкций.  
  
- Если визуальный элемент содержит как список инструкций векторной графики, так и визуальные дочерние объекты, то список инструкций в родительском визуальном элементе выполняется перед тем, как будут прорисованы любые визуальные дочерние объекты.  
  
- Элементы в списке инструкций векторной графики обрабатываются слева направо.  
  
<a name="visual_tree"></a>   
## <a name="visual-tree"></a>Видимое дерево  
 Визуальное дерево содержит все визуальные элементы, которые используются в пользовательском интерфейсе приложения. Поскольку визуальный элемент содержит постоянную графическую информацию, визуальное дерево можно представить как граф сцены, содержащий все необходимые сведения об отрисовке, необходимые для формирования выходных данных для устройства отображения. Это дерево представляет собой совокупность всех визуальных элементов, созданных непосредственно в приложении (в коде или в разметке). Визуальное дерево также содержит все визуальные элементы, созданные путем расширения шаблона элементов, таких как элементы управления и объекты данных.  
  
 В следующем коде показан элемент <xref:System.Windows.Controls.StackPanel>, определенный в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Если необходимо перечислить визуальные объекты, составляющие элемент <xref:System.Windows.Controls.StackPanel> в примере разметки, можно найти иерархию визуальных объектов, показанную ниже:  
  
 ![Схема иерархии визуального дерева](./media/wpf-graphics-rendering-overview/visual-tree-hierarchy.gif)  
  
### <a name="rendering-order"></a>Порядок отрисовки  
 Визуальное дерево определяет порядок отрисовки визуальных элементов и графических объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Обработка начинается с корневого визуального элемента, самого верхнего узла в визуальном дереве. Затем обрабатываются дочерние элементы корневого визуального элемента слева направо. Если у визуального элемента есть дочерние элементы, они обрабатываются перед элементами, находящимися на одном уровне с визуальным элементом. Это означает, что содержимое дочерних визуальных элементов отображается перед содержимым самого визуального элемента.  
  
 ![Схема порядка отрисовки визуального дерева](./media/wpf-graphics-rendering-overview/visual-tree-rendering-order.gif) 
  
### <a name="root-visual"></a>Корневой визуальный элемент  
 **Корневой визуальный элемент** — это самый верхний элемент в иерархии визуального дерева. В большинстве приложений базовым классом корневого визуального элемента является либо <xref:System.Windows.Window>, либо <xref:System.Windows.Navigation.NavigationWindow>. Однако при размещении визуальных объектов в приложении Win32 в качестве корневого визуального элемента использовался бы самый верхний визуальный элемент в окне Win32. Дополнительные сведения см. в разделе [Руководство по размещению визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### <a name="relationship-to-the-logical-tree"></a>Связь с логическом деревом  
 Логическое дерево в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представляет элементы приложения во время выполнения. Хотя этим деревом нельзя управлять напрямую, с помощью этой схемы удобно представить наследование свойств и маршрутизацию событий. В отличие от визуального дерева, логическое дерево может представлять объекты данных, не являющиеся визуальными, например <xref:System.Windows.Documents.ListItem>. Во многих случаях логическое дерево приближается к определению разметки приложения. В следующем коде показан элемент <xref:System.Windows.Controls.DockPanel>, определенный в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Если необходимо перечислить логические объекты, составляющие элемент <xref:System.Windows.Controls.DockPanel>, в примере разметки, можно найти иерархию логических объектов, как показано ниже:  
  
 ![Схема дерева](./media/tree1-wcp.gif "Tree1_wcp")  
Схема логического дерева  
  
 Визуальное дерево и логическое дерево синхронизируются с текущим набором элементов приложения, отражая добавление, удаление или изменение элементов. Однако эти деревья отражают различные представления приложения. В отличие от визуального дерева, логическое дерево не расширяет элемент <xref:System.Windows.Controls.ContentPresenter> элемента управления. Это означает, что между логическим деревом и визуальным деревом для одного и того же набора объектов нет прямого однозначного соответствия. Фактически, вызов метода <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> объекта **LogicalTreeHelper** и метода <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> объекта **VisualTreeHelper** с использованием того же элемента, что и параметр, дает разные результаты.  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../advanced/trees-in-wpf.md).  
  
### <a name="viewing-the-visual-tree-with-xamlpad"></a>Просмотр визуального дерева с помощью XamlPad  
 Средство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XamlPad предоставляет возможность просмотра и исследования визуального дерева, соответствующего определенному в настоящий момент содержимому XAML. Для отображения визуального дерева нажмите кнопку **Показать визуальное дерево**. Ниже показано, как раскрытие содержимого XAML в узлах визуального дерева на панели **обозревателя визуального дерева** XamlPad:  
  
 ![Панель обозревателя визуального дерева в XamlPad](./media/wpf-graphics-rendering-overview/visual-tree-explorer.png)  

 Обратите внимание, что элементы управления <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>и <xref:System.Windows.Controls.Button> отображают отдельную иерархию визуальных объектов на панели **обозревателя визуального дерева** XamlPad. Это связано с тем, что элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют <xref:System.Windows.Controls.ControlTemplate>, который содержит визуальное дерево этого элемента управления. При явной ссылке на элемент управления вы неявно ссылаетесь на его визуальную иерархию.  
  
### <a name="profiling-visual-performance"></a>Профилирование производительности для объекта Visual  
 В состав [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] входит пакет инструментов для профилирования производительности, с помощью которых можно проанализировать поведение приложения во время выполнения и определить, каким образом можно повысить производительность. Средство Visual Profiler предоставляет подробные данные о производительности в удобном графическом формате, сопоставляя их напрямую с визуальным деревом приложения. На этом снимке экрана показан раздел **Использование ЦП** средства Visual Profiler. В этом разделе вы можете получить точное представление об использовании объектом служб [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], таких как отрисовка и разметка.  
  
 ![Отображение данных Visual Profiler](./media/wpfperf-visualprofiler-04.png "WPFPerf_VisualProfiler_04")  
Отображение данных Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## <a name="visual-rendering-behavior"></a>Поведение отрисовки для объекта Visual  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает несколько возможностей, влияющих на отрисовку визуальных объектов: графика, векторная графика и аппаратно независимая графика.  
  
### <a name="retained-mode-graphics"></a>Абстрактный графический режим  
 Для понимания роли объекта Visual необходимо хорошо представлять различие между системами с **непосредственным** и **абстрактным** графическими режимами. В стандартном приложении Win32 на основе GDI или GDI+ используется непосредственный графический режим. Это означает, что приложение отвечает за перерисовку той части клиентской области, которая стала недействительной из-за таких действий, как изменение размера окна или изменение внешнего вида объекта.  
  
 ![Схема последовательности отрисовки Win32](./media/wpf-graphics-rendering-overview/win32-rendering-squence.png)  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], напротив, используется абстрактный графический режим. Это означает, что в объектах приложения, у которых есть внешний облик, определяется набор сериализованных графических данных. После определения графических данных система отвечает на все запросы перерисовки для отрисовки объектов приложения. Даже во время выполнения можно изменять или создавать объекты приложения, при этом система будет обрабатывать запросы на перерисовку. Преимущество абстрактного режима состоит в том, что данные отрисовки всегда сохраняются приложением в сериализованном виде, при этом за отрисовку отвечает система. На следующей схеме показано, как приложение полагается на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для обработки запросов на отрисовку.  
  
 ![Схема последовательности отрисовки WPF](./media/wpf-graphics-rendering-overview/wpf-rendering-sequence.png)  

#### <a name="intelligent-redrawing"></a>Интеллектуальная перерисовка  
 Одним из основных преимуществ использования абстрактного графического режима является то, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может эффективно оптимизировать элементы приложения, которые требуют перерисовки. Даже при наличии сложной сцены с различными уровнями прозрачности разработчикам обычно не нужно писать специальный код для оптимизации перерисовки. Сравните это с программированием для Win32, в котором можно потратить значительные усилия на оптимизацию приложения, уменьшая объем перерисовки в области обновления. Пример сложного случая оптимизации перерисовки для приложений Win32 см. в разделе [Перерисовка в области обновления](/windows/desktop/gdi/redrawing-in-the-update-region).  
  
### <a name="vector-graphics"></a>Векторная графика  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует **векторную графику** качестве формата данных отрисовки. Векторная графика, к которой относятся масштабируемые векторные рисунки (SVG), метафайлы Windows (WMF) и шрифты TrueType, хранит данные отрисовки и передает их в виде списка инструкций, которые описывают, как воссоздать изображение с помощью графических примитивов. Например, шрифты TrueType — это контурные шрифты, которые описывают набор линий, кривых и команд, а не массив точек. Одним из основных преимуществ векторной графики является возможность масштабирования до любого размера и разрешения.  
  
 В отличие от векторной графики в растровой графике данные отрисовки представлены в попиксельном виде для определенного разрешения. Одним из ключевых различий между растровой и векторной графикой является соответствие исходному изображению. Например, при изменении размера исходного изображения в растровой графике изображение растягивается, тогда как в векторной — масштабируется с сохранением качества.  
  
 На следующем рисунке показано исходное изображение, которое было увеличено в 3 раза (масштаб 300 %). Обратите внимание на искажения, которые появляются при растяжении исходного изображения в растровом формате по сравнению с векторным.  
  
 ![Различия между растровой и векторной графикой](./media/wpf-graphics-rendering-overview/raster-vector-differences.png)  
  
 В следующей разметке показаны два определенных элемента <xref:System.Windows.Shapes.Path>. Второй элемент использует <xref:System.Windows.Media.ScaleTransform> для изменения размера инструкций рисования первого элемента на 300%. Обратите внимание, что инструкции по рисованию в элементах <xref:System.Windows.Shapes.Path> остаются неизменными.  
  
 [!code-xaml[VectorGraphicsSnippets#VectorGraphicsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### <a name="about-resolution-and-device-independent-graphics"></a>О разрешении и аппаратно независимой графике  
 Существуют два фактора, которые определяют размер текста и графики на экране: разрешение и количество точек на дюйм. Разрешение определяет число пикселей, отображаемых на экране. Чем выше разрешение, тем меньше размер пикселей и тем меньше отображаемые объекты и текст. Изображение на мониторе с разрешением 1024 x 768 значительно уменьшится, если изменить разрешение на 1600 x 1200.  
  
 Другой системный параметр, количество точек на дюйм, описывает размер дюйма экрана в пикселях. В большинстве систем Windows используется значение DPI 96, означающее, что экранный дюйм составляет 96 пикселей. При повышении количества точек на дюйм экранный дюйм увеличивается, при понижении — уменьшается. Это означает, что дюйм экрана не совпадает с размером настоящего дюйма, по крайней мере в большинстве систем. При увеличении количества точек на дюйм изображения и текст становятся больше, так как увеличивается размер экранного дюйма. Увеличение количества точек на дюйм может сделать текст более удобным для чтения, особенно при высоких разрешениях.  
  
 Не все приложения поддерживают количество точек на дюйм: в некоторых приложениях в качестве основной единицы измерения используются аппаратно зависимые пиксели, и изменение количества точек на дюйм не влияет на такие приложения. Во многих других приложениях количество точек на дюйм используется при описании размеров шрифта, но для остальных элементов используются пиксели. Слишком маленькое или слишком большое количество точек на дюйм может вызвать проблемы с разметкой для этих приложений, так как размер текста приложения будет изменяться с изменением системного количества точек на дюйм, тогда как интерфейс приложения изменяться не будет. Для приложений, разработанных с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], эта проблема устранена.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает автоматическое масштабирование с помощью аппаратно независимых пикселей вместо аппаратно зависимых пикселей; изображения и текст масштабируются правильно без дополнительных действий со стороны разработчика приложения. На следующем рисунке показан пример отображения текста и графики [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с различными параметрами количества точек на дюйм.  
  
 ![Изображения и текст с различными параметрами количества точек на дюйм](./media/graphicsmm-dpi-setting-examples.png "graphicsmm_dpi_setting_examples")  
Изображения и текст с различными параметрами количества точек на дюйм  
  
<a name="visualtreehelper_class"></a>   
## <a name="visualtreehelper-class"></a>Класс VisualTreeHelper  
 Класс <xref:System.Windows.Media.VisualTreeHelper> является статическим вспомогательным классом, предоставляющим низкоуровневые функции для программирования на уровне визуальных объектов, который полезен в особых сценариях, таких как разработка высокопроизводительных пользовательских элементов управления. В большинстве случаев объекты платформы более высокого уровня [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.TextBlock>, обеспечивают большую гибкость и простоту использования.  
  
### <a name="hit-testing"></a>Проверка нажатия  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет методы для проверки попадания на визуальные объекты, если поддержка проверки попадания по умолчанию не соответствует вашим потребностям. Можно использовать методы <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> в классе <xref:System.Windows.Media.VisualTreeHelper>, чтобы определить, находится ли значение геометрии или координаты точки внутри границы данного объекта, например элемента управления или графического элемента. Например, с помощью проверки нажатия можно определить, попадает ли щелчок мыши в пределах ограничивающего прямоугольника объекта в окружность. Также можно переопределить реализацию проверки нажатия по умолчанию и выполнять собственные вычисления для проверки нажатия.  
  
 Дополнительные сведения о проверке нажатия см. в разделе [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md).  
  
### <a name="enumerating-the-visual-tree"></a>Перечисление визуального дерева  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет функциональные возможности для перечисления элементов визуального дерева. Чтобы получить родительский объект, вызовите метод <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A>. Чтобы получить дочерний или прямой потомок визуального объекта, вызовите метод <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A>. Этот метод возвращает дочерний <xref:System.Windows.Media.Visual> родителя по указанному индексу.  
  
 В следующем примере показано, как перечислить всех потомков визуального объекта. Этот метод можно использовать для сериализации всех данных отрисовки в иерархии визуального объекта.  
  
 [!code-csharp[VisualsOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 В большинстве случаев логическое дерево более удобно для представления элементов приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Хотя логическое дерево нельзя изменить напрямую, с помощью этой схемы удобно представить наследование свойств и маршрутизацию событий. В отличие от визуального дерева, логическое дерево может представлять объекты данных, не являющиеся визуальными, например <xref:System.Windows.Documents.ListItem>. Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../advanced/trees-in-wpf.md).  
  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет методы для возврата ограничивающего прямоугольника визуальных объектов. Можно вернуть ограничивающий прямоугольник визуального объекта, вызвав <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>. Можно вернуть ограничивающий прямоугольник всех потомков визуального объекта, включая сам визуальный объект, вызвав <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>. В следующем коде показано, как вычислить ограничивающие прямоугольники для визуального объекта и всех его потомков.  
  
 [!code-csharp[VisualsOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- <xref:System.Windows.Media.DrawingVisual>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
- [Использование объектов DrawingVisual](using-drawingvisual-objects.md)
- [Руководство по размещению визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)
- [Улучшение производительности приложений WPF](../advanced/optimizing-wpf-application-performance.md)
