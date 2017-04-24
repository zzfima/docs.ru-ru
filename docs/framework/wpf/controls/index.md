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
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 3c9baa45741cbc21e1d22ad6a126d7c3d94370cb
ms.lasthandoff: 04/08/2017

---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поставляется с множеством стандартных компонентов пользовательского интерфейса, которые используются практически во всех приложениях Windows, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.ListBox>. Исторически эти объекты называются элементами управления. Хотя SDK [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] продолжает использовать термин "элемент управления" для общего обозначения любого класса, который представляет визуальный объект в приложении, важно отметить, что для наличия визуального представления класс не обязательно должен наследовать от класса <xref:System.Windows.Controls.Control>. Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, содержат шаблон <xref:System.Windows.Controls.ControlTemplate>, позволяющий потребителю элемента управления существенно изменить внешний вид элемента управления, не создавая новый подкласс.  В этом разделе рассматривается, как элементы управления (как те, которые наследуют от класса <xref:System.Windows.Controls.Control>, так и другие) обычно используются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<<<<<<< HEAD
 
=======
   
>>>>>>> a8ea58d... fix build errors
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Можно добавить элемент управления в приложение с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: две метки, два текстовых поля и две кнопки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости создание <xref:System.Windows.Controls.Grid>, `grid1`, было исключено из примера.                   `grid1` имеет такие же определения столбцов и строк, как показано в предыдущем примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
-   Измените значение свойства элемента управления.  
  
-   Создайте <xref:System.Windows.Style> для элемента управления.  
  
-   Создайте новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления обладают свойствами, которые позволяют изменять внешний вид элемента управления, например <xref:System.Windows.Controls.Control.Background%2A> кнопки <xref:System.Windows.Controls.Button>. Можно задать свойства значения в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и коде. Следующий пример устанавливает свойства <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontWeight%2A> для <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 Вместо установки свойств для каждого экземпляра в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] дает возможность указать внешний вид всех элементов управления путем создания <xref:System.Windows.Style>.                           В следующем примере создается <xref:System.Windows.Style>, который применяется к каждому элементу <xref:System.Windows.Controls.Button> в приложении.                          Определения <xref:System.Windows.Style> обычно задаются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в словаре <xref:System.Windows.ResourceDictionary>, например свойство <xref:System.Windows.FrameworkElement.Resources%2A> элемента <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления конкретного типа, присвоив ключ для стиля и указав этот ключ в свойстве `Style` элемента управления.  Дополнительные сведения о стилях см. в разделе [Использование стилей и шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 <xref:System.Windows.Style> позволяет задать свойства для нескольких элементов управления одновременно, но иногда может потребоваться настроить внешний вид <xref:System.Windows.Controls.Control> за пределами того, что можно сделать, создав <xref:System.Windows.Style>. Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, имеют <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>. Свойство <xref:System.Windows.Controls.Control.Template%2A> элемента <xref:System.Windows.Controls.Control> является общедоступным, поэтому можно предоставить <xref:System.Windows.Controls.Control> шаблон <xref:System.Windows.Controls.ControlTemplate>, который отличается от стандартного. Часто можно указать новый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control> вместо наследования от элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control>.  
  
 Рассмотрим очень часто используемый элемент управления, <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> состоит в том, чтобы позволить приложению предпринимать определенные действия, когда пользователь нажимает на него.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как приподнятый прямоугольник.  При разработке приложения можно воспользоваться поведением <xref:System.Windows.Controls.Button>, то есть обработкой события нажатия кнопки. Но можно изменить внешний вид кнопки, изменив свойства кнопки.  В этом случае можно создать новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> создает <xref:System.Windows.Controls.Button> со скругленными углами и градиентным фоном.  <xref:System.Windows.Controls.ControlTemplate> содержит объект <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Border.Background%2A> которого является <xref:System.Windows.Media.LinearGradientBrush> с двумя объектами <xref:System.Windows.Media.GradientStop>.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных для привязки свойства <xref:System.Windows.Media.GradientStop.Color%2A> объекта <xref:System.Windows.Media.GradientStop> к цвету фона кнопки.  Если задано свойство <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Controls.Button>, то цвет этого значения будет использоваться как первый <xref:System.Windows.Media.GradientStop>. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). В примере также создается <xref:System.Windows.Trigger>, изменяющий внешний вид <xref:System.Windows.Controls.Button> при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>, равном `true`.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Свойству <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Controls.Button> должно быть присвоено значение <xref:System.Windows.Media.SolidColorBrush> для правильной работы примера.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Можно подписаться на событие элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но обрабатывать события можно только в коде.  В следующем примере показано, как подписаться на событие `Click` <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Следующий пример обрабатывает событие `Click` <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, которые наследуют от класса <xref:System.Windows.Controls.Control>, могут включать форматированное содержимое. Например, <xref:System.Windows.Controls.Label> может содержать любой объект, например строку, <xref:System.Windows.Controls.Image> или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку форматированного содержимого и служат базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl> — некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl> — некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl> — некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox> и <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl> — некоторые примеры классов, которые наследуют от этого класса: <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem> и <xref:System.Windows.Controls.ToolBar>.  
  
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
