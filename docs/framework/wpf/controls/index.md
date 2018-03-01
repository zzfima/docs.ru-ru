---
title: "Элементы управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66c6cc58423a2af8d0fd6de93b8884918888fb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]поставляется с большинством общих компонентов пользовательского интерфейса, которые используются в практически во всех приложениях Windows, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, и <xref:System.Windows.Controls.ListBox>. Исторически эти объекты называются элементами управления. Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK продолжает использовать термин «элемент управления» для общего обозначения любого класса, который представляет видимый объект в приложении, очень важно Обратите внимание, что класс необходимо наследовать от <xref:System.Windows.Controls.Control> класс, чтобы иметь визуальное представление. Классы, наследующие от <xref:System.Windows.Controls.Control> класс содержит <xref:System.Windows.Controls.ControlTemplate>, что позволяет потребителю элемента управления радикально изменить внешний вид элемента управления без необходимости создания нового подкласса.  В этом разделе рассматриваются как элементы управления (тех, которые наследуют от <xref:System.Windows.Controls.Control> класса и не поддерживающие) часто применяются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Добавление элемента управления в приложение с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: двух меток, два текстовых поля и две кнопки, в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости создание <xref:System.Windows.Controls.Grid>, `grid1`, был исключен из примера. `grid1`имеет одинаковые определения столбцов и строк, как показано в предыдущем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
-   Измените значение свойства элемента управления.  
  
-   Создать <xref:System.Windows.Style> для элемента управления.  
  
-   Создать новую <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления обладают свойствами, которые позволяют изменять внешний вид элемента управления, такие как <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button>. Можно задать значение свойства в обеих [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и код. В следующем примере задается <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, и <xref:System.Windows.Controls.Control.FontWeight%2A> свойства <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет возможность задавать внешний вид элементов управления, вместо того чтобы задавать свойства для каждого экземпляра в приложении, создав <xref:System.Windows.Style>. В следующем примере создается <xref:System.Windows.Style> , применяется к каждому <xref:System.Windows.Controls.Button> в приложении. <xref:System.Windows.Style>определения обычно определяются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в <xref:System.Windows.ResourceDictionary>, такие как <xref:System.Windows.FrameworkElement.Resources%2A> свойство <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления определенного типа путем присвоения ключа для стиля и задания этого ключа в `Style` свойство элемента управления.  Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 Объект <xref:System.Windows.Style> позволяет одновременно задать свойства для нескольких элементов управления, но иногда может потребоваться настроить внешний вид <xref:System.Windows.Controls.Control> за то, что можно сделать, создав <xref:System.Windows.Style>. Классы, наследующие от <xref:System.Windows.Controls.Control> класса имеют <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>. <xref:System.Windows.Controls.Control.Template%2A> Свойство <xref:System.Windows.Controls.Control> является открытым, так что можно предоставить <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> , отличается от значения по умолчанию. Часто можно указать новый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control> вместо наследования от элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control>.  
  
 Рассмотрим очень часто управления <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> — позволить приложению выполнить некоторое действие, когда пользователь нажимает кнопку.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как приподнятый прямоугольник.  При разработке приложения, можно воспользоваться преимуществами поведение <xref:System.Windows.Controls.Button>— то есть путем обработки события нажатия кнопки, но могут измениться внешний вид можно сделать, изменив свойства этой кнопки кнопки.  В этом случае можно создать новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> Создает <xref:System.Windows.Controls.Button> со скругленными углами и градиента фона.  <xref:System.Windows.Controls.ControlTemplate> Содержит <xref:System.Windows.Controls.Border> которого <xref:System.Windows.Controls.Border.Background%2A> — <xref:System.Windows.Media.LinearGradientBrush> с двумя <xref:System.Windows.Media.GradientStop> объектов.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных для привязки <xref:System.Windows.Media.GradientStop.Color%2A> свойство <xref:System.Windows.Media.GradientStop> цвет фона кнопки.  При задании <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.Button>, цвет этого значения будет использоваться в качестве первого <xref:System.Windows.Media.GradientStop>. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). В примере также создается <xref:System.Windows.Trigger> , изменяется внешний вид <xref:System.Windows.Controls.Button> при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> — `true`.  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control.Background%2A> Свойство <xref:System.Windows.Controls.Button> должно быть присвоено <xref:System.Windows.Media.SolidColorBrush> для правильной работы примера.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Можно подписаться на событие элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или код, но может обрабатывать только событие в коде.  Следующий пример показывает, как подписаться на `Click` событие <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 В следующем примере показана обработка `Click` событие <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, наследующих <xref:System.Windows.Controls.Control> класс иметь возможность содержать сложных элементов. Например <xref:System.Windows.Controls.Label> может содержать любой объект, например, строка <xref:System.Windows.Controls.Image>, или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку для расширенного содержимого и служить базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>— Примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, и <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>— Примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>— Примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, и <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>— Примеры классов, наследующих от этого класса: <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, и <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Дополнительные сведения об этих базовых классах см. в разделе [модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Категории элементов управления](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [Библиотека элементов управления](../../../../docs/framework/wpf/controls/control-library.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Ввод](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [Включение команды](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [Пошаговые руководства: создание пользовательской анимированной кнопки](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)
