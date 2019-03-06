---
title: Элементы управления
ms.date: 03/30/2017
dev_langs:
  - csharp
  - vb
helpviewer_keywords:
  - 'controls [WPF], about WPF controls'
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержит большинство распространенных компонентов пользовательского интерфейса, которые используются практически во всех приложениях Windows, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, и <xref:System.Windows.Controls.ListBox>. Исторически эти объекты называются элементами управления. Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK продолжает использовать термин «элемент управления» для общего обозначения любого класса, который представляет видимый объект в приложении, важно отметить, что класс не обязательно должен наследовать от <xref:System.Windows.Controls.Control> класса, чтобы иметь визуальное представление. Классы, наследующие от <xref:System.Windows.Controls.Control> класс содержать <xref:System.Windows.Controls.ControlTemplate>, позволяющий потребителю элемента управления существенно изменить внешний вид элемента управления, не создавая новый подкласс.  В этом разделе обсуждаются как элементы управления (наследующих или наследующих от <xref:System.Windows.Controls.Control> класса и не возвращающие) обычно используются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Элемент управления можно добавить в приложение с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: две метки, два текстовых поля и две кнопки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости создание <xref:System.Windows.Controls.Grid>, `grid1`, был исключен из примера. `grid1` имеет те же определения столбцов и строк, как показано в предыдущем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] пример.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
-   Измените значение свойства элемента управления.  
  
-   Создание <xref:System.Windows.Style> для элемента управления.  
  
-   Создайте новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления имеют свойства, которые позволяют изменять внешний вид элемента управления, такие как <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button>. Можно задать свойства значения в обоих [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода. В следующем примере задается <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, и <xref:System.Windows.Controls.Control.FontWeight%2A> свойства <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] дает возможность задавать внешний вид элементов управления, вместо установки свойств для каждого экземпляра в приложении путем создания <xref:System.Windows.Style>. В следующем примере создается <xref:System.Windows.Style> , применяется к каждому <xref:System.Windows.Controls.Button> в приложении. <xref:System.Windows.Style> определения обычно определяются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в <xref:System.Windows.ResourceDictionary>, такие как <xref:System.Windows.FrameworkElement.Resources%2A> свойство <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления определенного типа, присвоив ключ для стиля и указав этот ключ в `Style` свойство элемента управления.  Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 Объект <xref:System.Windows.Style> позволяет одновременно задать свойства для нескольких элементов управления, но иногда может потребоваться настроить внешний вид <xref:System.Windows.Controls.Control> за то, что можно сделать, создав <xref:System.Windows.Style>. Классы, наследующие от <xref:System.Windows.Controls.Control> класс иметь <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>. <xref:System.Windows.Controls.Control.Template%2A> Свойство <xref:System.Windows.Controls.Control> является открытым, поэтому пользователь может предоставить <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> , отличается от значения по умолчанию. Часто можно указать новый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control> вместо наследования от элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control>.  
  
 Рассмотрим очень популярный элемент управления, <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> позволяет приложению выполнить определенное действие, когда пользователь щелкает его.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как приподнятый прямоугольник.  При разработке приложения, можно воспользоваться преимуществами поведения <xref:System.Windows.Controls.Button>— то есть путем обработки события нажатия кнопки, но вы можете изменить внешний вид кнопки можно сделать, изменив свойства кнопки.  В этом случае можно создать новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> Создает <xref:System.Windows.Controls.Button> со скругленными углами и градиентным фоном.  <xref:System.Windows.Controls.ControlTemplate> Содержит <xref:System.Windows.Controls.Border> которого <xref:System.Windows.Controls.Border.Background%2A> — <xref:System.Windows.Media.LinearGradientBrush> с двумя <xref:System.Windows.Media.GradientStop> объектов.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных для привязки <xref:System.Windows.Media.GradientStop.Color%2A> свойство <xref:System.Windows.Media.GradientStop> цвету фона кнопки.  При задании <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.Button>, цвет этого значения будет использоваться как первый <xref:System.Windows.Media.GradientStop>. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md). В примере также создается <xref:System.Windows.Trigger> , изменяет внешний вид <xref:System.Windows.Controls.Button> при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> является `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control.Background%2A> Свойство <xref:System.Windows.Controls.Button> должно быть присвоено <xref:System.Windows.Media.SolidColorBrush> для правильной работы примера.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Можно подписаться на событие элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но может обрабатывать только событие в коде.  В следующем примере показано, как подписаться на `Click` событие <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 В следующем примере показана обработка `Click` событие <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, наследующих <xref:System.Windows.Controls.Control> класса, могут содержать форматированное содержимое. Например <xref:System.Windows.Controls.Label> может содержать любой объект, например строку, <xref:System.Windows.Controls.Image>, или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку форматированного содержимого и служат базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>— Некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, и <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>— Некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>— Некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, и <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>— Некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, и <xref:System.Windows.Controls.ToolBar>.  

  
 Дополнительные сведения об этих базовых классах см. в разделе [модель содержимого WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>См. также
- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Категории элементов управления](controls-by-category.md)
- [Библиотека элементов управления](control-library.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Ввод](../advanced/input-wpf.md)
- [Включение команды](../advanced/how-to-enable-a-command.md)
- [Пошаговые руководства: Создание пользовательской анимированной кнопки](walkthroughs-create-a-custom-animated-button.md)
- [Настройка элементов управления](control-customization.md)
