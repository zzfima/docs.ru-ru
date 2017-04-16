---
title: "Элементы управления | Microsoft Docs"
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
  - "элементы управления [WPF], сведения об элементах управления WPF"
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Элементы управления
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поставляется с большинством общих компонентов пользовательского интерфейса, которые используются практически в каждом приложении Windows, например <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.ListBox>.  Ранее эти объекты назывались элементами управления.  Хотя пакет SDK [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] продолжает использовать термин "элемент управления" для общего обозначения любого класса, который представляет видимый объект в приложении, обратите внимание, что классу не требуется наследование от класса <xref:System.Windows.Controls.Control>, чтобы иметь визуальное представление.  Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, содержат <xref:System.Windows.Controls.ControlTemplate>, который позволяет потребителю элемента управления радикально изменить внешний вид элемента управления, для чего не требуется создавать новый подкласс.  В этом разделе обсуждается использование элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(тех, которые наследуются от класса <xref:System.Windows.Controls.Control>, и тех, которые не наследуются\).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="creating_an_instance_of_a_control"></a>   
## Создание экземпляра элемента управления  
 Чтобы добавить элемент управления в приложение, используйте [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или код.  Следующий пример показывает, как создать простое приложение, которое запрашивает у пользователя его имя и фамилию.  Этом примере создает в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] шесть элементов управления: две подписи, два текстовых поля и две кнопки.  Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере то же самое приложение создается в коде.  Создание <xref:System.Windows.Controls.Grid>, `grid1` для краткости было исключено из примера.  В `grid1` указаны определения столбца и строки, приведенные в предыдущем примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## Изменение внешнего вида элемента управления  
 Изменение внешнего вида элемента управления для подбора внешнего вида приложения — это частая задача.  Чтобы изменить внешний вид элемента управления, выполните одно из следующих действий в зависимости от того, что требуется выполнить:  
  
-   Изменить значение свойства элемента управления.  
  
-   Создайте <xref:System.Windows.Style> для элемента управления.  
  
-   Создайте новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### Изменение значения свойства элемента управления  
 Многие элементы управления обладают свойствами, которые позволяют изменять внешний вид элемента управления, например <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button>.  Можно задать свойства значения в коде и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  В следующем примере свойства <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, и <xref:System.Windows.Controls.Control.FontWeight%2A> на <xref:System.Windows.Controls.Button> устанавливаются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 В следующем примере те же свойства задаются в коде.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет возможность задавать внешний вид для нескольких элементов управления вместо того, чтобы задавать свойства для каждого экземпляра в приложении. Это достигается путем создания <xref:System.Windows.Style>.  В следующем примере создается <xref:System.Windows.Style>, который применяется к каждому <xref:System.Windows.Controls.Button> в приложении. Определения <xref:System.Windows.Style> обычно указываются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в <xref:System.Windows.ResourceDictionary>, например свойство <xref:System.Windows.FrameworkElement.Resources%2A> объекта <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Стиль можно также применить только к определенным элементам управления определенного типа путем присвоения ключа для стиля и задания этого ключа в свойстве элемента управления `Style`.  За дополнительными сведениями о стилях обратитесь к разделу [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### Создание ControlTemplate  
 <xref:System.Windows.Style> позволяет задать свойства для нескольких элементов управления одновременно. Однако в некоторых случаях может потребоваться изменить внешний вид <xref:System.Windows.Controls.Control> сверх того, что достигается путем создания <xref:System.Windows.Style>.  Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, имеют <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>.  Свойство <xref:System.Windows.Controls.Control.Template%2A> <xref:System.Windows.Controls.Control> является открытым, поэтому пользователь может предоставить <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate>, который отличен от задаваемого по умолчанию.  Часто можно указать новый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control> вместо наследования элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control>.  
  
 Рассмотрим очень часто используемый элемент, <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> заключается в том, чтобы позволить приложению выполнить некоторое действие, когда пользователь щелкает этот элемент.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как приподнятый прямоугольник.  При разработке приложения может понадобиться поведение <xref:System.Windows.Controls.Button> \(т.е. обработка события нажатия кнопки\), однако при этом внешний вид кнопки может быть изменен так, что изменения свойств кнопки будет недостаточно.  В этом случае можно создать новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> создает <xref:System.Windows.Controls.Button> с округленными углами и градиентным фоном.  <xref:System.Windows.Controls.ControlTemplate> содержит <xref:System.Windows.Controls.Border>, чей <xref:System.Windows.Controls.Border.Background%2A> является <xref:System.Windows.Media.LinearGradientBrush> с двумя объектами <xref:System.Windows.Media.GradientStop>.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных для привязки свойства <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.GradientStop> к цвету фона кнопки.  При установке свойства <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> цвет этого значения будет использоваться как первый <xref:System.Windows.Media.GradientStop>.  Дополнительные сведения о привязке данных см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  В примере также создается <xref:System.Windows.Trigger>, который изменяет внешний вид <xref:System.Windows.Controls.Button>, когда <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> равно `true`.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Для правильной работы примера свойству <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> должно быть присвоено <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="subscribing_to_events"></a>   
## Подписка на события  
 Подписаться на событие элемента управления можно с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но обрабатывать событие возможно только в коде.  В следующем примере показано, как подписаться на событие `Click` из <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 В следующем примере обрабатывается событие `Click` из <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## Расширенное содержимое в элементах управления  
 Большинство классов, которые наследуются от класса <xref:System.Windows.Controls.Control>, имеют возможность хранения расширенного содержимого.  Например, <xref:System.Windows.Controls.Label> может содержать любой объект, такой как строка, <xref:System.Windows.Controls.Image>, или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку для расширенного содержимого и служат базовым классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl> — некоторыми примерами классов, которые наследуются от этого класса, являются <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl> — некоторыми примерами классов, которые наследуются от этого класса, являются <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl> — некоторыми примерами классов, которые наследуются от этого класса, являются <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox> и <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl> — некоторыми примерами классов, которые наследуются от этого класса, являются <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem> и <xref:System.Windows.Controls.ToolBar>.  
  
 Дополнительные сведения об этих базовых классах см. в разделе [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Категории элементов управления](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Библиотека элементов управления](../../../../docs/framework/wpf/controls/control-library.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Ввод](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [Включение команды](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [Пошаговые руководства: создание пользовательской анимированной кнопки](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)