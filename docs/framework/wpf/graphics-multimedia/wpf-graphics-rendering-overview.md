---
title: "Общие сведения об отрисовке графики в WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rendering
- rendering graphics [WPF]
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: "51"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfb9a546ca33b848fbbcbd114951eddc5b000663
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-graphics-rendering-overview"></a>Общие сведения об отрисовке графики в WPF
В этом разделе приведены общие сведения о визуальном слое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот раздел посвящен роль <xref:System.Windows.Media.Visual> класса для подготовки к просмотру поддержку в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модели.  
  
  
<a name="role_of_visual_object"></a>   
## <a name="role-of-the-visual-object"></a>Роль визуального объекта  
 <xref:System.Windows.Media.Visual> Класс — это базовая абстракция, из которого каждые <xref:System.Windows.FrameworkElement> объекта является производным. Эта абстракция также служит точкой входа для написания новых элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и во многих случаях ее можно рассматривать в качестве дескриптора окна (HWND) в модели приложения Win32.  
  
 <xref:System.Windows.Media.Visual> Объект — это основное [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекта, основная цель которого — обеспечение поддержки отрисовки. Элементы управления пользовательского интерфейса, такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TextBox>, являются производными от <xref:System.Windows.Media.Visual> класса и использовать его для сохранения своих визуализируемых данных. <xref:System.Windows.Media.Visual> Объект предоставляет поддержку для:  
  
-   Отображение выходных данных: визуализация сохраненного, сериализованного содержимого визуального элемента.  
  
-   Преобразование: поддерживает преобразование визуального элемента.  
  
-   Отсечение: позволяет указать область отсечения для визуального элемента.  
  
-   Проверка нажатия: определяет, содержится ли координата или геометрическая фигура в границах визуального объекта.  
  
-   Вычисление ограничивающего прямоугольника: определение ограничивающего прямоугольника визуального объекта.  
  
 Тем не менее <xref:System.Windows.Media.Visual> объект, не включает поддержку не визуализируемых возможностей, таких как:  
  
-   Обработка событий  
  
-   Макет  
  
-   Стили  
  
-   привязка данных,  
  
-   Глобализация  
  
 <xref:System.Windows.Media.Visual>предоставляется как открытый абстрактный класс, от которого должны наследоваться дочерними классами. На следующем рисунке показана иерархия визуальных объектов, которые предоставляются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 ![Схема классов, производных от объекта Visual](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
Иерархия класса Visual  
  
### <a name="drawingvisual-class"></a>Класс DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> Является упрощенным класс рисования, который используется для отрисовки фигур, изображений или текста. Этот класс считается упрощенным, так как не предоставляет средств для работы с разметкой и обработку событий, что повышает его производительность. Поэтому этот класс идеально подходит для фоновых рисунков или клипов. <xref:System.Windows.Media.DrawingVisual> Может использоваться для создания пользовательского визуального объекта. Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
### <a name="viewport3dvisual-class"></a>Класс Viewport3DVisual  
 <xref:System.Windows.Media.Media3D.Viewport3DVisual> Обеспечивает связь между 2D <xref:System.Windows.Media.Visual> и <xref:System.Windows.Media.Media3D.Visual3D> объектов. <xref:System.Windows.Media.Media3D.Visual3D> Класс является базовым классом для всех трехмерных визуальных элементов. <xref:System.Windows.Media.Media3D.Viewport3DVisual> Требует определения <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> значение и <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> значение. Камера позволяет просмотреть сцену. Окно просмотра определяет, где проекция преобразуется в двумерную поверхность. Дополнительные сведения о трехмерной графике в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Общие сведения о трехмерной графике](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  
  
### <a name="containervisual-class"></a>Класс ContainerVisual  
 <xref:System.Windows.Media.ContainerVisual> Класс используется как контейнер для коллекции <xref:System.Windows.Media.Visual> объектов. <xref:System.Windows.Media.DrawingVisual> Класс является производным от <xref:System.Windows.Media.ContainerVisual> класса, что позволяет ему содержать коллекцию визуальных объектов.  
  
### <a name="drawing-content-in-visual-objects"></a>Рисование содержимого в объектах Visual  
 Объект <xref:System.Windows.Media.Visual> объект хранит данные отрисовки как **списка инструкций векторной графики**. Каждый элемент в списке инструкций представляет низкоуровневый набор графических данных и связанных ресурсов в сериализованном формате. Существует четыре различных типа данных отрисовки, которые могут включать графическое содержимое.  
  
|Тип содержимого для отрисовки|Описание:|  
|--------------------------|-----------------|  
|Векторная графика|Представляет векторные графические данные и все связанные <xref:System.Windows.Media.Brush> и <xref:System.Windows.Media.Pen> сведения.|  
|Изображение|Представляет изображение в пределах области, определяемой <xref:System.Windows.Rect>.|  
|Глиф|Представляет рисунок, отображающий <xref:System.Windows.Media.GlyphRun>, который представляет собой последовательность глифов из указанного ресурса шрифтов. Таким образом представляется текст.|  
|Видео|Представляет рисунок, отображающий видео.|  
  
 <xref:System.Windows.Media.DrawingContext> Позволяет заполнять <xref:System.Windows.Media.Visual> визуальное содержимое. При использовании <xref:System.Windows.Media.DrawingContext> команд рисования объекта, фактически происходит сохранение набора данных визуализации, которые позднее будут использоваться графической системой; рисование на экране в режиме реального времени не выполняется.  
  
 При создании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента управления, такого как <xref:System.Windows.Controls.Button>, элемент управления неявно создает данные визуализации для рисования самого себя. Например, установка <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button> элемент управления сохраняет визуальное представление глифа.  
  
 Объект <xref:System.Windows.Media.Visual> описывает свое содержимое в виде одной или нескольких <xref:System.Windows.Media.Drawing> объектов, содержащихся в <xref:System.Windows.Media.DrawingGroup>. Объект <xref:System.Windows.Media.DrawingGroup> также описывает маски непрозрачности, преобразования, эффекты растрового изображения и другие операции, которые применяются к его содержимому. <xref:System.Windows.Media.DrawingGroup>При отображении содержимого операции, применяются в следующем порядке: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, а затем <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Ниже показан порядок, в котором <xref:System.Windows.Media.DrawingGroup> операции, применяемые во время отрисовки последовательности.  
  
 ![Порядок DrawingGroup для операций](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Порядок операций для DrawingGroup  
  
 Дополнительные сведения см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
#### <a name="drawing-content-at-the-visual-layer"></a>Отображение содержимого на визуальном уровне  
 Вы нельзя непосредственно создать экземпляр <xref:System.Windows.Media.DrawingContext>; тем не менее, можно получить контекст рисования из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>. В следующем примере извлекается <xref:System.Windows.Media.DrawingContext> из <xref:System.Windows.Media.DrawingVisual> и использует его, чтобы нарисовать прямоугольник.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### <a name="enumerating-drawing-content-at-the-visual-layer"></a>Перечисление содержимого рисования на визуальном уровне  
 В дополнение к другим применениям <xref:System.Windows.Media.Drawing> объектов также предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
> [!NOTE]
>  При перечислении содержимого визуального элемента, необходимо извлечь <xref:System.Windows.Media.Drawing> объектов, а не базовое представление данных визуализации в виде списка инструкций векторной графики.  
  
 В следующем примере используется <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> метод для извлечения <xref:System.Windows.Media.DrawingGroup> значение <xref:System.Windows.Media.Visual> и его перечисления.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## <a name="how-visual-objects-are-used-to-build-controls"></a>Использование визуальных объектов для создания элементов управления  
 Многие из объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] состоят из других визуальных объектов, то есть они могут содержать различные иерархии объектов-потомков. Многие элементы пользовательского интерфейса в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], например элементы управления, состоят из нескольких визуальных объектов, которые представляют различные типы прорисовываемых элементов. Например <xref:System.Windows.Controls.Button> элемент управления может содержать несколько других объектов, включая <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter>, и <xref:System.Windows.Controls.TextBlock>.  
  
 В следующем коде показано <xref:System.Windows.Controls.Button> элемента управления, определенного в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Бы перечислить визуальные объекты, составляющие значение по умолчанию <xref:System.Windows.Controls.Button> элемента управления, необходимо найти иерархию визуальных объектов, показано ниже:  
  
 ![Схема иерархии визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.gif "VisualLayerOverview03")  
Схема иерархии визуального дерева  
  
 <xref:System.Windows.Controls.Button> Управления содержит <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> элемент, который в свою очередь, содержит <xref:System.Windows.Controls.ContentPresenter> элемента. <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> Элемент отвечает за рисование границ и фона для <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.ContentPresenter> Элемент отвечает за отображение содержимого <xref:System.Windows.Controls.Button>. В этом случае, поскольку отображается текст, <xref:System.Windows.Controls.ContentPresenter> элемент содержит <xref:System.Windows.Controls.TextBlock> элемента. Тот факт, <xref:System.Windows.Controls.Button> управления использует <xref:System.Windows.Controls.ContentPresenter> означает, что содержимое может быть представлен другие элементы, такие как <xref:System.Windows.Controls.Image> или геометрический объект, такой как <xref:System.Windows.Media.EllipseGeometry>.  
  
### <a name="control-templates"></a>Шаблоны элементов управления  
 Развертывание элемента управления в иерархии элементов управления лежат <xref:System.Windows.Controls.ControlTemplate>. Шаблон элемента управления определяет визуальную иерархию по умолчанию для элемента управления. При явной ссылке на элемент управления вы неявно ссылаетесь на его визуальную иерархию. Для изменения внешнего вида элемента управления вы можете переопределить значения по умолчанию для шаблона элемента управления. Например, можно изменить значение цвета фона <xref:System.Windows.Controls.Button> управления, чтобы он использовал значение цвета линейного градиента вместо значения сплошного цвета. Дополнительные сведения см. в разделе [Стили и шаблоны кнопок](../../../../docs/framework/wpf/controls/button-styles-and-templates.md).  
  
 Элемент пользовательского интерфейса, такие как <xref:System.Windows.Controls.Button> контроля, содержит несколько списков инструкций векторной графики, описывающих полное определение отрисовки элемента управления. В следующем коде показано <xref:System.Windows.Controls.Button> элемента управления, определенного в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Если нужно перечислить визуальные объекты и списки инструкций векторной графики, составляющих <xref:System.Windows.Controls.Button> элемента управления, необходимо найти иерархию объектов, как показано ниже:  
  
 ![Схема визуального дерева и отрисовки данных](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
Схема визуального дерева и отрисовки данных  
  
 <xref:System.Windows.Controls.Button> Управления содержит <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> элемент, который в свою очередь, содержит <xref:System.Windows.Controls.ContentPresenter> элемента. <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> Элемент отвечает за рисование всех отдельных графических элементов, составляющих границ и фона кнопки. <xref:System.Windows.Controls.ContentPresenter> Элемент отвечает за отображение содержимого <xref:System.Windows.Controls.Button>. Таким образом, поскольку выполняется отображение изображения, <xref:System.Windows.Controls.ContentPresenter> элемент содержит <xref:System.Windows.Controls.Image> элемента.  
  
 При работе с иерархией визуальных объектов и списками инструкций векторной графики следует учитывать несколько моментов.  
  
-   Порядок иерархии представляет порядок отрисовки графической информации. От корневого визуального элемента дочерние элементы распространяются слева направо и сверху вниз. Если у элемента есть дочерние визуальные элементы, они распространяются до элементов того же уровня.  
  
-   Узел неконечных элементов в иерархии, такие как <xref:System.Windows.Controls.ContentPresenter>, используются для хранения дочерних элементов — они не содержат списки инструкций.  
  
-   Если визуальный элемент содержит как список инструкций векторной графики, так и визуальные дочерние объекты, то список инструкций в родительском визуальном элементе выполняется перед тем, как будут прорисованы любые визуальные дочерние объекты.  
  
-   Элементы в списке инструкций векторной графики обрабатываются слева направо.  
  
<a name="visual_tree"></a>   
## <a name="visual-tree"></a>Видимое дерево  
 Визуальное дерево содержит все визуальные элементы, которые используются в пользовательском интерфейсе приложения. Поскольку визуальный элемент содержит постоянную графическую информацию, визуальное дерево можно представить как граф сцены, содержащий все необходимые сведения об отрисовке, необходимые для формирования выходных данных для устройства отображения. Это дерево представляет собой совокупность всех визуальных элементов, созданных непосредственно в приложении (в коде или в разметке). Визуальное дерево также содержит все визуальные элементы, созданные путем расширения шаблона элементов, таких как элементы управления и объекты данных.  
  
 В следующем коде показано <xref:System.Windows.Controls.StackPanel> элемента, определенного в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Бы перечислить визуальные объекты, составляющие <xref:System.Windows.Controls.StackPanel> элемент в примере разметки, необходимо найти иерархию visual объектов, как показано ниже:  
  
 ![Схема иерархии визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.gif "VisualLayerOverview05")  
Схема иерархии визуального дерева  
  
### <a name="rendering-order"></a>Порядок отрисовки  
 Визуальное дерево определяет порядок отрисовки визуальных элементов и графических объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Обработка начинается с корневого визуального элемента, самого верхнего узла в визуальном дереве. Затем обрабатываются дочерние элементы корневого визуального элемента слева направо. Если у визуального элемента есть дочерние элементы, они обрабатываются перед элементами, находящимися на одном уровне с визуальным элементом. Это означает, что содержимое дочерних визуальных элементов отображается перед содержимым самого визуального элемента.  
  
 ![Схема порядка отрисовки визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.gif "VisualLayerOverview06")  
Схема порядка отрисовки визуального дерева  
  
### <a name="root-visual"></a>Корневой визуальный элемент  
 **Корневой визуальный элемент** — это самый верхний элемент в иерархии визуального дерева. В большинстве приложений базовый класс корневой визуальный является <xref:System.Windows.Window> или <xref:System.Windows.Navigation.NavigationWindow>. Однако при размещении визуальных объектов в приложении Win32 в качестве корневого визуального элемента использовался бы самый верхний визуальный элемент в окне Win32. Дополнительные сведения см. в разделе [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### <a name="relationship-to-the-logical-tree"></a>Связь с логическом деревом  
 Логическое дерево в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представляет элементы приложения во время выполнения. Хотя этим деревом нельзя управлять напрямую, с помощью этой схемы удобно представить наследование свойств и маршрутизацию событий. В отличие от визуального дерева, логическое дерево может представлять невизуальных данных объектов, таких как <xref:System.Windows.Documents.ListItem>. Во многих случаях логическое дерево приближается к определению разметки приложения. В следующем коде показано <xref:System.Windows.Controls.DockPanel> элемента, определенного в разметке.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Если бы перечислить логические объекты, которые составляют <xref:System.Windows.Controls.DockPanel> элемент в примере разметки, необходимо найти иерархию логических объектов, как показано ниже:  
  
 ![Диаграмма дерева](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.gif "Tree1_wcp")  
Схема логического дерева  
  
 Визуальное дерево и логическое дерево синхронизируются с текущим набором элементов приложения, отражая добавление, удаление или изменение элементов. Однако эти деревья отражают различные представления приложения. В отличие от визуального дерева, логическое дерево не расширяет элемент управления <xref:System.Windows.Controls.ContentPresenter> элемента. Это означает, что между логическим деревом и визуальным деревом для одного и того же набора объектов нет прямого однозначного соответствия. Фактически, вызов **LogicalTreeHelper** объекта <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> метод и **VisualTreeHelper** объекта <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> с помощью того же элемента как параметр дает разные результаты, метод .  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
### <a name="viewing-the-visual-tree-with-xamlpad"></a>Просмотр визуального дерева с помощью XamlPad  
 Средство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], XamlPad, позволяет просматривать и изучать визуальное дерево, соответствующее текущему содержимому [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Для отображения визуального дерева нажмите кнопку **Показать визуальное дерево**. Ниже показано расширение содержимого [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] в узлы визуального дерева на панели **обозревателя визуального дерева** XamlPad.  
  
 ![Панель обозревателя визуального дерева в XamlPad](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
Панель обозревателя визуального дерева в XamlPad  
  
 Обратите внимание как <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.Button> каждого отображают отдельные иерархии визуальных объектов в **обозревателя визуального дерева** панель XamlPad. Это вызвано [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы управления обладают <xref:System.Windows.Controls.ControlTemplate> , содержащий визуальное дерево этого элемента управления. При явной ссылке на элемент управления вы неявно ссылаетесь на его визуальную иерархию.  
  
### <a name="profiling-visual-performance"></a>Профилирование производительности для объекта Visual  
 В состав [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] входит пакет инструментов для профилирования производительности, с помощью которых можно проанализировать поведение приложения во время выполнения и определить, каким образом можно повысить производительность. Средство Visual Profiler предоставляет подробные данные о производительности в удобном графическом формате, сопоставляя их напрямую с визуальным деревом приложения. На этом снимке экрана показан раздел **Использование ЦП** средства Visual Profiler. В этом разделе вы можете получить точное представление об использовании объектом служб [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], таких как отрисовка и разметка.  
  
 ![Visual Profiler отображения вывода](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf_VisualProfiler_04")  
Отображение данных Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## <a name="visual-rendering-behavior"></a>Поведение отрисовки для объекта Visual  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает несколько возможностей, влияющих на отрисовку визуальных объектов: графика, векторная графика и аппаратно независимая графика.  
  
### <a name="retained-mode-graphics"></a>Абстрактный графический режим  
 Для понимания роли объекта Visual необходимо хорошо представлять различие между системами с **непосредственным** и **абстрактным** графическими режимами. В стандартном приложении Win32 на основе GDI или GDI+ используется непосредственный графический режим. Это означает, что приложение отвечает за перерисовку той части клиентской области, которая стала недействительной из-за таких действий, как изменение размера окна или изменение внешнего вида объекта.  
  
 ![Схема последовательности отрисовки Win32](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
Схема последовательности отрисовки Win32  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], напротив, используется абстрактный графический режим. Это означает, что в объектах приложения, у которых есть внешний облик, определяется набор сериализованных графических данных. После определения графических данных система отвечает на все запросы перерисовки для отрисовки объектов приложения. Даже во время выполнения можно изменять или создавать объекты приложения, при этом система будет обрабатывать запросы на перерисовку. Преимущество абстрактного режима состоит в том, что данные отрисовки всегда сохраняются приложением в сериализованном виде, при этом за отрисовку отвечает система. На следующей схеме показано, как приложение полагается на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для обработки запросов на отрисовку.  
  
 ![Схема последовательности отрисовки WPF](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
Схема последовательности отрисовки WPF  
  
#### <a name="intelligent-redrawing"></a>Интеллектуальная перерисовка  
 Одним из основных преимуществ использования абстрактного графического режима является то, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может эффективно оптимизировать элементы приложения, которые требуют перерисовки. Даже при наличии сложной сцены с различными уровнями прозрачности разработчикам обычно не нужно писать специальный код для оптимизации перерисовки. Сравните это с программированием для Win32, в котором можно потратить значительные усилия на оптимизацию приложения, уменьшая объем перерисовки в области обновления. Пример сложного случая оптимизации перерисовки для приложений Win32 см. в разделе [Перерисовка в области обновления](https://msdn.microsoft.com/library/dd162909.aspx).  
  
### <a name="vector-graphics"></a>Векторная графика  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует **векторную графику** качестве формата данных отрисовки. Векторная графика, к которой относятся масштабируемые векторные рисунки (SVG), метафайлы Windows (WMF) и шрифты TrueType, хранит данные отрисовки и передает их в виде списка инструкций, которые описывают, как воссоздать изображение с помощью графических примитивов. Например, шрифты TrueType — это контурные шрифты, которые описывают набор линий, кривых и команд, а не массив точек. Одним из основных преимуществ векторной графики является возможность масштабирования до любого размера и разрешения.  
  
 В отличие от векторной графики в растровой графике данные отрисовки представлены в попиксельном виде для определенного разрешения. Одним из ключевых различий между растровой и векторной графикой является соответствие исходному изображению. Например, при изменении размера исходного изображения в растровой графике изображение растягивается, тогда как в векторной — масштабируется с сохранением качества.  
  
 На следующем рисунке показано исходное изображение, которое было увеличено в 3 раза (масштаб 300 %). Обратите внимание на искажения, которые появляются при растяжении исходного изображения в растровом формате по сравнению с векторным.  
  
 ![Различия между растровой и векторной графикой](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
Различия между растровой и векторной графикой  
  
 В следующем примере показано два <xref:System.Windows.Shapes.Path> определенные элементы. Второй элемент использует <xref:System.Windows.Media.ScaleTransform> для изменения размера инструкции по рисованию первого элемента на 300%. Обратите внимание, что инструкции рисования в <xref:System.Windows.Shapes.Path> элементы остаются без изменений.  
  
 [!code-xaml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### <a name="about-resolution-and-device-independent-graphics"></a>О разрешении и аппаратно независимой графике  
 Существуют два фактора, которые определяют размер текста и графики на экране: разрешение и количество точек на дюйм. Разрешение определяет число пикселей, отображаемых на экране. Чем выше разрешение, тем меньше размер пикселей и тем меньше отображаемые объекты и текст. Изображение на мониторе с разрешением 1024 x 768 значительно уменьшится, если изменить разрешение на 1600 x 1200.  
  
 Другой системный параметр, количество точек на дюйм, описывает размер дюйма экрана в пикселях. Для большинства систем [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] количество точек на дюйм составляет 96, т. е. на одном дюйме экрана находится 96 пикселей. При повышении количества точек на дюйм экранный дюйм увеличивается, при понижении — уменьшается. Это означает, что дюйм экрана не совпадает с размером настоящего дюйма, по крайней мере в большинстве систем. При увеличении количества точек на дюйм изображения и текст становятся больше, так как увеличивается размер экранного дюйма. Увеличение количества точек на дюйм может сделать текст более удобным для чтения, особенно при высоких разрешениях.  
  
 Не все приложения поддерживают количество точек на дюйм: в некоторых приложениях в качестве основной единицы измерения используются аппаратно зависимые пиксели, и изменение количества точек на дюйм не влияет на такие приложения. Во многих других приложениях количество точек на дюйм используется при описании размеров шрифта, но для остальных элементов используются пиксели. Слишком маленькое или слишком большое количество точек на дюйм может вызвать проблемы с разметкой для этих приложений, так как размер текста приложения будет изменяться с изменением системного количества точек на дюйм, тогда как интерфейс приложения изменяться не будет. Для приложений, разработанных с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], эта проблема устранена.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает автоматическое масштабирование с помощью аппаратно независимых пикселей вместо аппаратно зависимых пикселей; изображения и текст масштабируются правильно без дополнительных действий со стороны разработчика приложения. На следующем рисунке показан пример отображения текста и графики [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с различными параметрами количества точек на дюйм.  
  
 ![Изображения и текст с различными параметрами DPI](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm_dpi_setting_examples")  
Изображения и текст с различными параметрами количества точек на дюйм  
  
<a name="visualtreehelper_class"></a>   
## <a name="visualtreehelper-class"></a>Класс VisualTreeHelper  
 <xref:System.Windows.Media.VisualTreeHelper> Класс является статическим вспомогательным классом, предоставляющим низкоуровневые функции для программирования на уровне визуализации объекта, что полезно в определенных случаях, таких как разработка пользовательских элементов управления высокой производительности. В большинстве случаев более высокого уровня [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework объекты, такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.TextBlock>, обладают большей гибкостью и простотой использования.  
  
### <a name="hit-testing"></a>Проверка нажатия  
 <xref:System.Windows.Media.VisualTreeHelper> Класс предоставляет методы проверки нажатия визуальных объектов, если стандартная проверки нажатия не соответствует потребностям пользователя. Можно использовать <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> методы в <xref:System.Windows.Media.VisualTreeHelper> класс, чтобы определить, является ли значение координаты геометрического или точка в пределах заданного объекта, например элемент управления или графический элемент. Например, с помощью проверки нажатия можно определить, попадает ли щелчок мыши в пределах ограничивающего прямоугольника объекта в окружность. Также можно переопределить реализацию проверки нажатия по умолчанию и выполнять собственные вычисления для проверки нажатия.  
  
 Дополнительные сведения о проверке нажатия см. в разделе [Проверка нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
### <a name="enumerating-the-visual-tree"></a>Перечисление визуального дерева  
 <xref:System.Windows.Media.VisualTreeHelper> Класс предоставляет функциональные возможности для перечисления членов визуального дерева. Чтобы извлечь родительский объект, вызовите <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A> метод. Чтобы получить дочерние или прямым потомком визуального объекта, вызовите <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> метод. Этот метод возвращает дочерний элемент <xref:System.Windows.Media.Visual> родительского объекта по указанному индексу.  
  
 В следующем примере показано, как перечислить всех потомков визуального объекта. Этот метод можно использовать для сериализации всех данных отрисовки в иерархии визуального объекта.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 В большинстве случаев логическое дерево более удобно для представления элементов приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Хотя логическое дерево нельзя изменить напрямую, с помощью этой схемы удобно представить наследование свойств и маршрутизацию событий. В отличие от визуального дерева, логическое дерево может представлять невизуальных данных объектов, таких как <xref:System.Windows.Documents.ListItem>. Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 <xref:System.Windows.Media.VisualTreeHelper> Класс предоставляет методы для возвращения ограничивающего прямоугольника визуальных объектов. Можно вернуть ограничивающий прямоугольник визуального объекта путем вызова <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>. Можно вернуть ограничивающий прямоугольник всех потомков визуального объекта, включая сам визуальный объект, путем вызова <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>. В следующем коде показано, как вычислить ограничивающие прямоугольники для визуального объекта и всех его потомков.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 <xref:System.Windows.Media.DrawingVisual>  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Проверка нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)  
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
