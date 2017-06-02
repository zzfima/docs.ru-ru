---
title: "Общие сведения об отрисовке графики в WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "графика, отрисовка"
  - "отрисовка графики"
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: 51
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 48
---
# Общие сведения об отрисовке графики в WPF
В этом разделе дан обзор визуального уровня [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Он посвящен роли класса <xref:System.Windows.Media.Visual> для поддержки отрисовки в модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="role_of_visual_object"></a>   
## Роль визуального объекта  
 Класс <xref:System.Windows.Media.Visual> — это базовая абстракция, от которой наследуется каждый объект <xref:System.Windows.FrameworkElement>.  Он также служит точкой входа для написания новых элементов управления в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и во многих случая может рассматриваться как дескриптор окна \(HWND\) в модели приложения Win32.  
  
 Объект <xref:System.Windows.Media.Visual> является основным объектом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], основная цель которого — обеспечение поддержки отрисовки.  Элементы управления пользовательского интерфейса, такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TextBox>, являются производными от класса <xref:System.Windows.Media.Visual> и используют его для сохранения своих визуализируемых данных.  Объект <xref:System.Windows.Media.Visual> обеспечивает поддержку следующих возможностей.  
  
-   Отображение выходных данных: отрисовка сохраненного, сериализованного содержимого изображения визуального объекта.  
  
-   Преобразование: выполнение преобразований визуального объекта.  
  
-   Отсечение: обеспечение поддержки отсечения области визуального объекта.  
  
-   Проверка нажатия: определение, содержатся ли координаты или контур в границах визуального объекта.  
  
-   Вычисления ограничивающего прямоугольника: определение ограничивающего прямоугольника визуального объекта.  
  
 Однако объект <xref:System.Windows.Media.Visual> не включает поддержку не визуализируемых возможностей, перечисленных ниже.  
  
-   обработка событий,  
  
-   Макет  
  
-   Стили  
  
-   привязка данных,  
  
-   Глобализация  
  
 Объект <xref:System.Windows.Media.Visual> предоставляется как открытый абстрактный класс, от которого должны наследовать дочерние классы.  На следующем рисунке показана иерархия визуальных объектов, которые представлены в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 ![Схема классов, производных от Visual&#45;объекта](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
Иерархия визуальных классов  
  
### Класс DrawingVisual  
 Объект <xref:System.Windows.Media.DrawingVisual> представляет собой облегченный класс рисования, который используется для отображения фигур, рисунков или текста.  Этот класс считается облегченным, поскольку он не предоставляет возможности разметки или обработки событий, что повышает его производительность во время выполнения.  По этой причине эти объекты идеально подходят для фоновых рисунков и коллекций картинок.  Объект <xref:System.Windows.Media.DrawingVisual> можно использовать для создания пользовательского визуального объекта.  Дополнительные сведения см. в разделе [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
### Класс Viewport3DVisual  
 Объект <xref:System.Windows.Media.Media3D.Viewport3DVisual> обеспечивает связь между двухмерными объектами <xref:System.Windows.Media.Visual> и объектами <xref:System.Windows.Media.Media3D.Visual3D>.  Класс <xref:System.Windows.Media.Media3D.Visual3D> является базовым для всех трехмерных визуальных элементов.  Для объекта <xref:System.Windows.Media.Media3D.Viewport3DVisual> требуется определение значений <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> и <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A>.  Камера позволяет просмотреть сцену.  Окно просмотра устанавливает место отображения проекции на двумерной поверхности.  Дополнительные сведения о трехмерных объектах в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  
  
### Класс ContainerVisual  
 Класс <xref:System.Windows.Media.ContainerVisual> используется в качестве контейнера для коллекции объектов <xref:System.Windows.Media.Visual>.  Класс <xref:System.Windows.Media.DrawingVisual> наследует от класса <xref:System.Windows.Media.ContainerVisual>, что позволяет ему содержать коллекцию визуальных объектов.  
  
### Рисование содержимого в визуальных объектах  
 Объект <xref:System.Windows.Media.Visual> хранит данные визуализации в виде **списка инструкций векторной графики**.  Каждый элемент в списке инструкций представляет набор графических данных нижнего уровня и связанных ресурсов в сериализованном формате.  Существуют четыре различных типа данных визуализации, которые могут содержать графическое содержимое.  
  
|Тип графического содержимого|Описание|  
|----------------------------------|--------------|  
|Векторная графика|Представляет данные векторной графики и любую информацию, связанную с объектами <xref:System.Windows.Media.Brush> и <xref:System.Windows.Media.Pen>.|  
|Изображение|Представляет изображение в пределах области, определенной объектом <xref:System.Windows.Rect>.|  
|Глиф|Представляет рисунок, отображающий объект <xref:System.Windows.Media.GlyphRun>, который представляет собой последовательность глифов из указанного ресурса шрифтов.  Это способ представления текста.|  
|Видео|Представляет рисунок, который отображает видео.|  
  
 Объект <xref:System.Windows.Media.DrawingContext> позволяет заполнить объект <xref:System.Windows.Media.Visual> визуальным содержимым.  При использовании команд рисования объекта <xref:System.Windows.Media.DrawingContext> фактически происходит сохранение набора данных визуализации, которые позднее будут использоваться графической системой; рисование не выполняется на экране в режиме реального времени.  
  
 При создании элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такого как <xref:System.Windows.Controls.Button>, этот элемент управления неявно создает данные визуализации для рисования самого себя.  Например, при установке свойства <xref:System.Windows.Controls.ContentControl.Content%2A> объекта <xref:System.Windows.Controls.Button> элемент управления сохраняет визуальное представление глифа.  
  
 Объект <xref:System.Windows.Media.Visual> описывает свое содержимое в виде одного или нескольких объектов <xref:System.Windows.Media.Drawing>, содержащихся в группе <xref:System.Windows.Media.DrawingGroup>.  Объект <xref:System.Windows.Media.DrawingGroup> также описывает маски прозрачности, преобразования, эффекты растрового изображения и другие операции, которые применяются к его содержимому.  При отображении содержимого операции <xref:System.Windows.Media.DrawingGroup> применяются в следующем порядке: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> и <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Ниже показан порядок, в котором операции <xref:System.Windows.Media.DrawingGroup> применяются во время отрисовки последовательности.  
  
 ![Порядок DrawingGroup для операций](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
Порядок операций DrawingGroup  
  
 Дополнительные сведения см. в разделе [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
#### Отображение содержимого на уровне визуализации  
 Нельзя непосредственно создать экземпляр <xref:System.Windows.Media.DrawingContext>; однако можно получить контекст рисования из определенных методов, таких как <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> и <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>.  В следующем примере извлекается <xref:System.Windows.Media.DrawingContext> из класса <xref:System.Windows.Media.DrawingVisual> и использует его, чтобы нарисовать прямоугольник.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### Перечисление содержимого рисования на уровне визуализации  
 В дополнение к другим применениям, объекты <xref:System.Windows.Media.Drawing> также предоставляют объектную модель для перечисления содержимого объекта <xref:System.Windows.Media.Visual>.  
  
> [!NOTE]
>  При перечислении содержимого визуального объекта извлекаются объекты <xref:System.Windows.Media.Drawing>, а не базовое представление данных визуализации в виде списка инструкций векторной графики.  
  
 В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> объекта <xref:System.Windows.Media.Visual> и его перечисления.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## Использование визуальных объектов для построения элементов управления  
 Многие объекты в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] состоят из других визуальных объектов, то есть они могут содержать различные иерархии объектов\-потомков.  Многие элементы пользовательского интерфейса в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как элементы управления, состоят из нескольких визуальных объектов, представляющих различные типы отрисовываемых элементов.  Например, элемент управления <xref:System.Windows.Controls.Button> может содержать другие объекты, включая <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> <xref:System.Windows.Controls.ContentPresenter> и <xref:System.Windows.Controls.TextBlock>.  
  
 В следующем коде показан элемент управления <xref:System.Windows.Controls.Button>, определенный в разметке.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Если нужно перечислить визуальные объекты, составляющие элемент управления <xref:System.Windows.Controls.Button> по умолчанию, необходимо найти иерархию визуальных объектов, как показано ниже.  
  
 ![Схема иерархии визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.png "VisualLayerOverview03")  
Схема иерархии визуального дерева  
  
 Элемент управления <xref:System.Windows.Controls.Button> содержит элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, который, в свою очередь, содержит элемент <xref:System.Windows.Controls.ContentPresenter>.  Элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> отвечает за рисование границ и фона объекта <xref:System.Windows.Controls.Button>.  Элемент <xref:System.Windows.Controls.ContentPresenter> отвечает за отображение содержимого <xref:System.Windows.Controls.Button>.  В данном случае, поскольку отображается текст, элемент <xref:System.Windows.Controls.ContentPresenter> содержит элемент <xref:System.Windows.Controls.TextBlock>.  Тот факт, что элемент управления <xref:System.Windows.Controls.Button> использует элемент <xref:System.Windows.Controls.ContentPresenter>, означает, что содержимое может быть представлено другими элементами, такими как <xref:System.Windows.Controls.Image>, или геометрическим объектом, таким как <xref:System.Windows.Media.EllipseGeometry>.  
  
### Шаблоны элементов управления  
 Основным компонентом для включения элемента управления в иерархию элементов управления является класс <xref:System.Windows.Controls.ControlTemplate>.  Шаблон элемента управления определяет для элемента управления визуальную иерархию по умолчанию.  При явной ссылке на элемент управления происходит неявное обращение к его визуальной иерархии.  Можно переопределить значения по умолчанию для шаблона элемента управления, чтобы создать пользовательский внешний вид элемента управления.  Например, можно изменить значение цвета фона элемента управления <xref:System.Windows.Controls.Button> таким образом, чтобы он использовал значение цвета линейного градиента вместо значения сплошного цвета.  Дополнительные сведения см. в разделе [Стили и шаблоны элемента Button](../../../../docs/framework/wpf/controls/button-styles-and-templates.md).  
  
 Элемент пользовательского интерфейса, такой как элемент управления <xref:System.Windows.Controls.Button>, содержит несколько списков инструкций векторной графики, описывающих полное определение отрисовки элемента управления.  В следующем коде показан элемент управления <xref:System.Windows.Controls.Button>, определенный в разметке.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Если нужно перечислить визуальные объекты и списки инструкций векторной графики, составляющих элемент управления <xref:System.Windows.Controls.Button>, необходимо найти иерархию объектов, как показано ниже.  
  
 ![Схема визуального дерева и отрисовки данных](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
Схема визуального дерева и отрисовки данных  
  
 Элемент управления <xref:System.Windows.Controls.Button> содержит элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, который, в свою очередь, содержит элемент <xref:System.Windows.Controls.ContentPresenter>.  Элемент <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> отвечает за рисование всех отдельных графических элементов, составляющих границу и фон кнопки.  Элемент <xref:System.Windows.Controls.ContentPresenter> отвечает за отображение содержимого <xref:System.Windows.Controls.Button>.  В данном случае, поскольку выполняется отображение изображения, элемент <xref:System.Windows.Controls.ContentPresenter> содержит элемент <xref:System.Windows.Controls.Image>.  
  
 Существует несколько моментов, на которые следует обратить внимание при рассмотрении иерархии визуальных объектов и списков инструкций векторной графики.  
  
-   Порядок в иерархии представляет порядок отрисовки графической информации.  От корневого визуального элемента дочерние элементы следуют слева направо, сверху вниз.  Если элемент имеет визуальные дочерние элементы, то они следуют до элементов того же уровня.  
  
-   Неконечные элементы узла в иерархии, например <xref:System.Windows.Controls.ContentPresenter>, используются для содержания дочерних элементов — они не содержат списки инструкций.  
  
-   Если визуальный элемент содержит список инструкций векторной графики и визуальные дочерние объекты, то список инструкций в родительском визуальном элементе отображается перед изображениями в любом из визуальных дочерних объектов.  
  
-   Элементы в списке инструкций векторной графики отображаются слева направо.  
  
<a name="visual_tree"></a>   
## Визуальное дерево  
 Визуальное дерево содержит все визуальные элементы, которые используются в пользовательском интерфейсе приложения.  Поскольку визуальный элемент содержит сохраненную графическую информацию, можно представить визуальное дерево как граф сцены, содержащий все сведения отрисовки, необходимые для формирования выходных данных для отрисовки на дисплее.  Это дерево является набором всех визуальных элементов, созданных непосредственно приложением либо в коде, либо в разметке.  Визуальное дерево также содержит все визуальные элементы, созданные расширением шаблона элементов, таких как элементы управления и объекты данных.  
  
 В следующем коде показан элемент <xref:System.Windows.Controls.StackPanel>, определенный в разметке.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Если нужно перечислить визуальные объекты, которые входят в состав элемента <xref:System.Windows.Controls.StackPanel> в примере разметки, необходимо найти иерархию визуальных объектов, как показано ниже.  
  
 ![Схема иерархии визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.png "VisualLayerOverview05")  
Схема иерархии визуального дерева  
  
### Порядок отрисовки  
 Визуальное дерево определяет порядок отрисовки визуальных и графические объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Порядок обхода начинается с корневого визуального элемента, который является самым верхним узлом визуального дерева.  Потомки корневого визуального элемента следуют слева направо.  Если визуальный элемент имеет дочерние элементы, они следуют до визуальных элементов одного уровня.  Это означает, что содержимое дочерних визуальных элементов отображается перед собственным содержимым визуального элемента.  
  
 ![Схема порядка отрисовки визуального дерева](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.png "VisualLayerOverview06")  
Схема порядка отрисовки визуального дерева  
  
### Корневой визуальный элемент  
 **Корневой визуальный элемент** является элементом иерархии визуального дерева верхнего уровня.  В большинстве приложений базовым классом корневого визуального элемента является <xref:System.Windows.Window> либо <xref:System.Windows.Navigation.NavigationWindow>.  Однако если визуальные объекты размещены в приложения Win32, то корневой визуальный элемент является визуальным узлом верхнего уровня окна Win32.  Дополнительные сведения см. в разделе [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### Связь с логическим деревом  
 Логическое дерево в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представляет элементы приложения во время выполнения.  Хотя напрямую этим деревом нельзя управлять, это представление приложения полезно для понимания наследования свойств и перенаправления событий.  В отличие от визуального дерева, логическое дерево может представлять невизуальные объекты данных, такие как <xref:System.Windows.Documents.ListItem>.  В большинстве случаев логическое дерево очень близко сопоставлено определениям разметки приложения.  В следующем коде показан элемент <xref:System.Windows.Controls.DockPanel>, определенный в разметке.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Если нужно перечислить логические объекты, которые входят в состав элемента <xref:System.Windows.Controls.DockPanel> в примере разметки, необходимо найти иерархию логических объектов, как показано ниже.  
  
 ![Схема дерева](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.png "Tree1\_wcp")  
Схема логического дерева  
  
 И визуальное, и логическое дерево синхронизируются с текущим набором элементов приложения, отражая любое добавление, удаление или изменение элементов.  Однако эти деревья представляют различные представления приложения.  В отличие от визуального дерева, логическое дерево не расширяет элемент <xref:System.Windows.Controls.ContentPresenter> элемента управления.  Это означает, что не существует прямого однозначного соответствия между логическим деревом и визуальным деревом для одного набора объектов.  Фактически вызов метода <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> объекта **LogicalTreeHelper** и метода <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> объекта **VisualTreeHelper** с помощью одного и того же элемента в качестве параметра дает разные результаты.  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
### Просмотр визуального дерева с помощью средства XamlPad  
 Средство XamlPad приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет возможность для просмотра и анализа визуального дерева, соответствующего текущему определенному содержимому [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  Нажмите кнопку **Показать визуальное дерево** в строке меню для отображения визуального дерева.  Ниже показано развертывание содержимого [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] в узлы визуального дерева в панели **Обозреватель визуального дерева** средства XamlPad:  
  
 ![Панель обозревателя визуального дерева в XamlPad](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
Панель обозревателя визуального дерева в XamlPad  
  
 Обратите внимание, как элементы управления <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.Button> отображают отдельные иерархии визуальных объектов в панели **Обозреватель визуального дерева** XamlPad.  Это происходит потому, что элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют объект <xref:System.Windows.Controls.ControlTemplate>, содержащий визуальное дерево этого элемента управления.  При явной ссылке на элемент управления происходит неявное обращение к его визуальной иерархии.  
  
### Анализ производительности визуальными средствами  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет набор средств профилирования производительности, позволяющие анализировать поведение приложения во время выполнения и определять типы оптимизации производительности, которые можно применить.  Средство Visual Profiler обеспечивает широкие возможности графического представления данных о производительности путем их сопоставления непосредственно с визуальным деревом приложения.  На этом снимке показан раздел **Использование ЦП** средства Visual Profiler, дающий точную декомпозицию использования объектом служб [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], таких как отрисовка и макет.  
  
 ![Отображение данных Visual Profiler](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf\_VisualProfiler\_04")  
Вывод на экран данных Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## Поведение при визуальной отрисовке  
 Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает несколько возможностей, влияющих на отрисовку визуальных объектов: графика, отображаемая после группирования объектов, векторная графика и аппаратно\-независимая графика.  
  
### Сохраненные графические режимы  
 Одной из основ для понимания роли объекта Visual является понимание различия между графическими системами **режима интерпретации** и **сохраненного режима**.  В стандартном приложении Win32 на основе GDI или GDI\+ используется графическая система режима интерпретации.  Это означает, что за обновление части клиентской области, ставшей недопустимой в результате какого\-либо действия, такого как изменения размера окна или изменения внешнего вида объекта, отвечает приложение.  
  
 ![Схема последовательности отрисовки Win32](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
Схема последовательности отрисовки Win32  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], напротив, используется система сохраненного режима.  Это означает, что объекты приложения, имеющие визуальное представление, определяют набор сериализованных графических данных.  После определения графических данных за все запросы на перерисовку для отрисовываемых объектов приложения отвечает система.  Даже во время выполнения можно изменить или создать объекты приложения и по\-прежнему полагаться на систему, отвечающую на запросы перерисовки.  Преимущество сохраненного режима графической системы заключается в том, что графические данные всегда сохраняются приложением в сериализованном состоянии, но за отрисовку по\-прежнему отвечает система.  На следующей схеме показано, как приложение использует [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для ответа на запросы рисования.  
  
 ![Схема последовательности отрисовки WPF](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
Схема последовательности отрисовки WPF  
  
#### Интеллектуальная перерисовка  
 Одним из преимуществ использования сохраненного режима для отображения графики является то, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может эффективно оптимизировать необходимую перерисовку в приложении.  Даже при наличии сложной сцены с различными уровнями прозрачности, как правило, необязательно писать специальный код для оптимизации перерисовки.  Сравните с программированием Win32, в котором можно потратить значительные усилия при оптимизации приложения путем уменьшения объема перерисовки в области обновления.  Пример сложной оптимизации перерисовки в приложениях Win32 см. в разделе [Перерисовка в области обновления](_win32_Redrawing_in_the_Update_Region).  
  
### Векторная графика  
 Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует **векторную графику** в качестве формата данных отрисовки.  Векторная графика — включающая SVG \(Scalable Vector Graphics\), метафайлы Windows \(wmf\) и шрифты TrueType — хранит данные отрисовки и передает их в виде списка инструкций, описывающих, как воссоздать изображение, используя графические примитивы.  Например, шрифты TrueType являются контурными шрифтами, которые описывают набор линий, кривых и команд, а не массив пикселей.  Одним из ключевых преимуществ векторной графики является возможность масштабирования до любого размера и разрешения.  
  
 В отличие от векторной графики, растровая графика хранит данные отрисовки как попиксельное представление изображения, что в совокупности дает изображение, подготовленное для определенного разрешения.  Одним из основных различий между растровым и векторным графическими форматами является соответствие с исходным изображением.  Например, при изменении размера исходного изображения растровые графические системы растягивают изображение, тогда как векторные графические системы масштабируют изображения, сохраняя его качество.  
  
 На следующем рисунке показано исходное изображение, размер которого изменен на 300%.  Обратите внимание, что в результате растягивания исходного растрового изображения возникают искажения в отличие от растягивания векторного графического изображения.  
  
 ![Различия между растровой и векторной графикой](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
Различия между растровой и векторной графикой  
  
 В следующей разметке показаны два определенных элемента <xref:System.Windows.Shapes.Path>.  Второй элемент использует <xref:System.Windows.Media.ScaleTransform>, чтобы изменить размер инструкций рисования первого элемента на 300%.  Обратите внимание, что инструкции рисования в элементах <xref:System.Windows.Shapes.Path> остаются неизменными.  
  
 [!code-xml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### Разрешение и аппаратно\-независимая графика  
 Существуют два фактора системы, определяющих размер текста и графики на экране: разрешение и число точек на дюйм \(DPI\).  Разрешение описывает число пикселей, отображаемых на экране.  Чем выше разрешение, тем меньше пиксели, в результате чего уменьшается размер отображаемой графики и текста.  Размер рисунка на мониторе с разрешением 1024 x 768 станет намного меньше, если изменить разрешение на 1600 x 1200.  
  
 Другой системный параметр, число точек на дюйм, описывает размер дюйма экрана в пикселях.  Большинство систем [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] имеют значение точек на дюйм, равное 96; это означает, что дюйм экрана содержит 96 пикселей.  При увеличении количества точек на дюйм увеличивается дюйм экрана; при уменьшение количества точек на дюйм экрана уменьшается.  Это означает, что дюйм экрана не соответствует размеру реального дюйма; в большинстве систем это, скорее всего, не так.  При увеличении количества точек на дюйм изображения и текст, в которых учитывается этот параметр, становятся большего размера, так как был увеличен размер экранного дюйма.  Увеличение количества точек на дюйм позволяет облегчить чтение текста, особенно при высоких разрешениях.  
  
 Не все приложения учитывают количество точек на дюйм: в некоторых приложениях в качестве единицы измерения используются аппаратно\-зависимые пиксели; изменение количества точек на дюйм системы не влияет на эти приложения.  Многие приложения используют единицы измерения, зависящие от количества точек на дюйм, для описания размеров шрифта, но для описания остальных элементов используют пиксели.  Установка слишком маленького или слишком большого количества точек на дюйм может вызвать проблемы разметки для этих приложений, так как текст приложения масштабируется, используя количества точек на дюйм системы, а пользовательский интерфейс приложений — не использует.  Данная проблема отсутствует для приложений, разработанных с использованием [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает автоматическое масштабирование с помощью аппаратно\-независимого пикселя в качестве основной единицы измерения вместо аппаратно\-зависимых пикселей; изображения и текст масштабируются правильно без какого\-либо дополнительного участия со стороны разработчика приложения.  На следующем рисунке показан пример того, как текст и изображения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображаются с различными параметрами количества точек на дюйм.  
  
 ![Изображения и текст с различными параметрами количества точек на дюйм](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm\_dpi\_setting\_examples")  
Изображения и текст с различными параметрами количества точек на дюйм  
  
<a name="visualtreehelper_class"></a>   
## Класс VisualTreeHelper  
 Класс <xref:System.Windows.Media.VisualTreeHelper> является статическим вспомогательным классом, предоставляющим низкоуровневые функции для программирования на уровне визуализации объекта, что полезно в определенных случаях, таких как разработка пользовательских элементов управления высокой производительности.  В большинстве случаев, объекты высокого уровня структуры [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.TextBlock>, предоставляют большую гибкость и просты в использовании.  
  
### Проверка нажатия  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет методы проверки нажатия визуальных объектов, если стандартная проверки нажатия не соответствует потребностям пользователя.  Можно использовать методы <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> в классе <xref:System.Windows.Media.VisualTreeHelper>, чтобы определить, находится ли геометрический объект или значение координаты точки внутри границы данного объекта, такого как элемент управления или графический элемент.  Например, можно использовать проверку нажатия, чтобы определить, попал ли щелчок ограничивающего прямоугольника объекта в границы фигуры круга. Также можно переопределить реализацию по умолчанию проверки нажатия для выполнения пользовательских вычислений проверки нажатия.  
  
 Дополнительные сведения о проверки нажатия см. в разделе [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
### Перечисление визуального дерева  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет функциональные возможности для перечисления членов визуального дерева.  Чтобы извлечь родительский объект, вызовите метод <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A>.  Чтобы извлечь дочерний элемент или прямой потомок визуального объекта, вызовите метод <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A>.  Этот метод возвращает дочерний элемент <xref:System.Windows.Media.Visual> родительского объекта по указанному индексу.  
  
 В следующем примере показано, как перечислить всех потомков визуального объекта. Этот метод можно использовать, если нужно сериализовать всю отрисовываемую информацию иерархии визуального объекта.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 В большинстве случаев логическое дерево является более полезным представлением элементов в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Хотя напрямую логическое дерево нельзя изменить, это представление приложения полезно для понимания наследования свойств и перенаправления событий.  В отличие от визуального дерева, логическое дерево может представлять невизуальные объекты данных, такие как <xref:System.Windows.Documents.ListItem>.  Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Класс <xref:System.Windows.Media.VisualTreeHelper> предоставляет методы для возвращения ограничивающего прямоугольника визуальных объектов.  Можно вернуть ограничивающий прямоугольник визуального объекта путем вызова метода <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>.  Можно вернуть ограничивающий прямоугольник всех потомков визуального объекта, включая сам визуальный объект, вызвав метод <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>.  В следующем коде показано, как выполнить вычисление ограничивающего прямоугольника визуального объекта и всех его потомков.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## См. также  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 <xref:System.Windows.Media.DrawingVisual>   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)   
 [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)   
 [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)