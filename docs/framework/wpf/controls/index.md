---
title: "Элементы управления | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7652a2e64cdc107546ac3ea51178a3542606bd43
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержит большинство распространенных компонентов пользовательского интерфейса, которые используются практически во всех Windows-приложениях, например <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.ListBox>. Исторически эти объекты называются элементами управления. Хотя SDK [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] продолжает использовать термин "элемент управления" для обобщенного обозначения любого класса, который представляет видимый объект в приложении, важно отметить, что класс с визуальным представлением не обязательно должен наследовать от класса <xref:System.Windows.Controls.Control>. Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, содержат шаблон <xref:System.Windows.Controls.ControlTemplate>, который позволяет существенно изменить внешний вид элемента управления, не создавая новый подкласс.  В этой статье описаны типичные методы применения в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления (наследующих или не наследующих от класса <xref:System.Windows.Controls.Control>).  
  
 
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Можно добавить элемент управления в приложение с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: две метки, два текстовых поля и две кнопки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для упрощения примера из него исключено создание <xref:System.Windows.Controls.Grid>, `grid1`.                   `grid1` имеет такие же определения столбцов и строк, как показано в предыдущем примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)] [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
-   Измените значение свойства элемента управления.  
  
-   Создайте <xref:System.Windows.Style> для элемента управления.  
  
-   Создайте новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 У многих элементов управления есть свойства, которые позволяют изменять внешний вид элемента управления, например <xref:System.Windows.Controls.Control.Background%2A> для <xref:System.Windows.Controls.Button>. Можно задать свойства значения в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и коде. Следующий пример устанавливает атрибуты <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontWeight%2A> для элемента <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)] [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет управлять внешним видом всех элементов, создавая <xref:System.Windows.Style>, вместо того чтобы указывать свойства отдельно для каждого экземпляра в приложении.                           Следующий пример создает <xref:System.Windows.Style>, который применяется к каждому <xref:System.Windows.Controls.Button> в приложении.                          Определения <xref:System.Windows.Style> обычно определяются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для <xref:System.Windows.ResourceDictionary>, например в свойстве <xref:System.Windows.FrameworkElement.Resources%2A> для <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления конкретного типа, присвоив ключ для стиля и указав этот ключ в свойстве `Style` элемента управления.  Дополнительные сведения о стилях см. в разделе [Использование стилей и шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 <xref:System.Windows.Style> позволяет задать свойства для нескольких элементов управления одновременно, но иногда для настройки внешнего вида <xref:System.Windows.Controls.Control> вам потребуется больше возможностей, чем предоставляет <xref:System.Windows.Style>. Классы, наследующие от класса <xref:System.Windows.Controls.Control>, имеют <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>. Свойство <xref:System.Windows.Controls.Control.Template%2A> для <xref:System.Windows.Controls.Control> является открытым, поэтому пользователь может предоставить для <xref:System.Windows.Controls.Control> значение <xref:System.Windows.Controls.ControlTemplate>, отличное от значения по умолчанию. Обычно для настройки внешнего вида <xref:System.Windows.Controls.Control> вы можете указать новый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control>, а не наследовать свойства элемента управления.  
  
 Давайте рассмотрим очень популярный элемент управления <xref:System.Windows.Controls.Button>.  Основное назначение <xref:System.Windows.Controls.Button> — предоставить приложению возможность выполнить определенное действие, когда пользователь нажимает кнопку.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как объемный прямоугольник.  При разработке приложения вас обычно интересует поведение <xref:System.Windows.Controls.Button>, то есть обработка события нажатия кнопки, но вы можете изменить еще и внешний вид кнопки, не ограничиваясь стандартными свойствами кнопки.  В нашем примере создается новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> создает <xref:System.Windows.Controls.Button> со скругленными углами и градиентным фоном.  <xref:System.Windows.Controls.ControlTemplate> содержит <xref:System.Windows.Controls.Border>, у которого <xref:System.Windows.Controls.Border.Background%2A> является <xref:System.Windows.Media.LinearGradientBrush> с двумя объектами <xref:System.Windows.Media.GradientStop>.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных, чтобы связать свойство <xref:System.Windows.Media.GradientStop.Color%2A> объекта <xref:System.Windows.Media.GradientStop> с цветом фона кнопки.  Когда вы изменяете свойство <xref:System.Windows.Controls.Control.Background%2A> объекта <xref:System.Windows.Controls.Button>, соответствующий новому значению цвет будет использоваться как первый <xref:System.Windows.Media.GradientStop>. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). Также этот пример создает <xref:System.Windows.Trigger>, который изменяет внешний вид <xref:System.Windows.Controls.Button>, если <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> имеет значение `true`.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Чтобы наш пример работал правильно, свойство <xref:System.Windows.Controls.Control.Background%2A> для <xref:System.Windows.Controls.Button> должно иметь значение <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Можно подписаться на событие элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но обрабатывать события можно только в коде.  Следующий пример демонстрирует, как подписаться на событие `Click` объекта <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)] [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Следующий пример демонстрирует, как обрабатывать событие `Click` объекта <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)] [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, которые наследуют от класса <xref:System.Windows.Controls.Control>, могут содержать форматированное содержимое. Например, <xref:System.Windows.Controls.Label> может содержать любой объект, <xref:System.Windows.Controls.Image> или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку форматированного содержимого и служат базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl> — в качестве примеров классов, наследующих от этого класса, можно назвать <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, и <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl> — в качестве примеров классов, наследующих от этого класса, можно назвать <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl> — в качестве примеров классов, наследующих от этого класса, можно назвать <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, и <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl> — в качестве примеров классов, наследующих от этого класса, можно назвать <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, и <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Для получения дополнительной информации об этих базовых классах см. раздел [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также  
 [Использование стилей и шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Категории элементов управления](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Библиотека элементов управления](../../../../docs/framework/wpf/controls/control-library.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Входные данные](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [Включение команды](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [Пошаговые руководства: создание пользовательской анимированной кнопки](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)
