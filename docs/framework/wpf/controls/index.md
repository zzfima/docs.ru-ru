---
title: Элементы управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 42596c8adf1b8b27f250fa7a3cf6cc173a63e2eb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459445"
---
# <a name="controls"></a>Элементы управления
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] поставляется с множеством общих компонентов пользовательского интерфейса, которые используются практически в любом приложении Windows, например <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>и <xref:System.Windows.Controls.ListBox>. Исторически эти объекты называются элементами управления. Хотя пакет SDK для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по-видимому использует термин "элемент управления" для слабого обозначения любого класса, представляющего видимый объект в приложении, важно отметить, что классу не требуется наследование от класса <xref:System.Windows.Controls.Control>, чтобы иметь видимое присутствие. Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, содержат <xref:System.Windows.Controls.ControlTemplate>, что позволяет потребителю элемента управления радикально изменять внешний вид элемента управления без необходимости создания нового подкласса.  В этом разделе описывается, как часто используются элементы управления (которые наследуются от класса <xref:System.Windows.Controls.Control> и тех, которые не являются) в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Элемент управления можно добавить в приложение с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  В этом примере создается шесть элементов управления: две метки, два текстовых поля и две кнопки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости создание <xref:System.Windows.Controls.Grid>, `grid1`, было исключено из примера. `grid1` имеет одинаковые определения столбцов и строк, как показано в предыдущем примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
- Измените значение свойства элемента управления.  
  
- Создайте <xref:System.Windows.Style> для элемента управления.  
  
- Создайте новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления имеют свойства, позволяющие изменять способ отображения элемента управления, например <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button>. Свойства значения можно задать как в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так и в коде. В следующем примере задаются свойства <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>и <xref:System.Windows.Controls.Control.FontWeight%2A> в <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] дает возможность задавать внешний вид элементов управления, а не задавать свойства для каждого экземпляра в приложении, создавая <xref:System.Windows.Style>. В следующем примере создается <xref:System.Windows.Style>, которая применяется к каждому <xref:System.Windows.Controls.Button> в приложении. определения <xref:System.Windows.Style> обычно определяются в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в <xref:System.Windows.ResourceDictionary>, например свойство <xref:System.Windows.FrameworkElement.Resources%2A> <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Можно также применить стиль только к определенным элементам управления определенного типа, назначив ключ стилю и указав этот ключ в свойстве `Style` элемента управления.  Дополнительные сведения о стилях см. в разделе [Стилизация и создание шаблонов](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 <xref:System.Windows.Style> позволяет одновременно задавать свойства для нескольких элементов управления, но иногда может потребоваться настроить внешний вид <xref:System.Windows.Controls.Control> помимо того, что можно сделать, создав <xref:System.Windows.Style>. Классы, которые наследуют от класса <xref:System.Windows.Controls.Control>, имеют <xref:System.Windows.Controls.ControlTemplate>, который определяет структуру и внешний вид <xref:System.Windows.Controls.Control>. Свойство <xref:System.Windows.Controls.Control.Template%2A> <xref:System.Windows.Controls.Control> является открытым, поэтому можно предоставить <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate>, который отличается от его значения по умолчанию. Часто можно указать новое <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Control> вместо наследования от элемента управления для настройки внешнего вида <xref:System.Windows.Controls.Control>.  
  
 Рассмотрим очень распространенный элемент управления <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> заключается в том, чтобы позволить приложению предпринимать какие-либо действия, когда пользователь щелкнет его.  По умолчанию <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается как порожденный прямоугольник.  При разработке приложения может потребоваться воспользоваться преимуществом поведения <xref:System.Windows.Controls.Button>--то есть путем обработки события нажатия кнопки, но вы можете изменить внешний вид кнопки, выполнив изменения свойств кнопки. это можно сделать, изменив ее свойства.  В этом случае можно создать новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере создается <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> создает <xref:System.Windows.Controls.Button> со скругленными углами и градиентным фоном.  <xref:System.Windows.Controls.ControlTemplate> содержит <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Media.LinearGradientBrush> с двумя объектами <xref:System.Windows.Media.GradientStop>.  Первый <xref:System.Windows.Media.GradientStop> использует привязку данных для привязки свойства <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.GradientStop> к цвету фона кнопки.  При установке свойства <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button>цвет этого значения будет использоваться в качестве первого <xref:System.Windows.Media.GradientStop>. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md). В примере также создается <xref:System.Windows.Trigger>, которая изменяет внешний вид <xref:System.Windows.Controls.Button>, когда <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Чтобы пример работал правильно, для свойства <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> необходимо задать <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Вы можете подписываться на события элемента управления с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода, но вы можете только обрабатывали событие в коде.  В следующем примере показано, как подписываться на событие `Click` <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 В следующем примере обрабатывается событие `Click` <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, которые наследуют от класса <xref:System.Windows.Controls.Control>, имеют емкость для хранения форматированного содержимого. Например, <xref:System.Windows.Controls.Label> может содержать любой объект, например строку, <xref:System.Windows.Controls.Image>или <xref:System.Windows.Controls.Panel>.  Следующие классы обеспечивают поддержку расширенного содержимого и служат базовыми классами для большинства элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>--несколько примеров классов, наследующих от этого класса, являются <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>и <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>--несколько примеров классов, наследующих от этого класса, являются <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>и <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--несколько примеров классов, наследующих от этого класса, являются <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>и <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--несколько примеров классов, наследующих от этого класса, являются <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>и <xref:System.Windows.Controls.ToolBar>.  

 Дополнительные сведения об этих базовых классах см. в разделе [модель содержимого WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>См. также

- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Категории элементов управления](controls-by-category.md)
- [Библиотека элементов управления](control-library.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Ввод](../advanced/input-wpf.md)
- [Включение команды](../advanced/how-to-enable-a-command.md)
- [Пошаговые руководства: создание пользовательской анимированной кнопки](walkthroughs-create-a-custom-animated-button.md)
- [Настройка элементов управления](control-customization.md)
