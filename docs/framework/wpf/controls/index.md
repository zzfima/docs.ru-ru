---
title: Управление
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2ec8c0a99f4e2431aed0d8c24168b7329de669f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187534"
---
# <a name="controls"></a>Управление
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]поставляется со многими общими компонентами uI, которые используются <xref:System.Windows.Controls.TextBox>почти <xref:System.Windows.Controls.Menu>в <xref:System.Windows.Controls.ListBox>каждом приложении Windows, таких как, <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label>, и . Исторически эти объекты называются элементами управления. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] то время как SDK продолжает использовать термин "контроль", чтобы свободно означать любой класс, представляющий видимый объект <xref:System.Windows.Controls.Control> в приложении, важно отметить, что класс не должен наследовать от класса, чтобы иметь видимое присутствие. Классы, которые <xref:System.Windows.Controls.Control> наследуют <xref:System.Windows.Controls.ControlTemplate>из класса содержат , что позволяет потребителю контроля радикально изменить внешний вид управления без создания нового подкласса.  Эта тема обсуждает, как элементы управления <xref:System.Windows.Controls.Control> (как те, которые наследуют [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]от класса и те, которые этого не делают) обычно используются в .  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Создание экземпляра элемента управления  
 Вы можете добавить элемент управления [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в приложение, используя либо или код.  В следующем примере показано, как создать простое приложение, которое запрашивает у пользователя имя и фамилию.  Этот пример создает шесть элементов управления: две метки, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]два текстовых ящика и две кнопки в . Все элементы управления могут быть созданы аналогичным образом.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 В следующем примере создается такое же приложение в коде. Для краткости, создание <xref:System.Windows.Controls.Grid>, `grid1`был исключен из образца. `grid1`имеет те же определения столбца и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] строки, как показано в предыдущем примере.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Изменение внешнего вида элемента управления  
 Обычно внешний вид элемента управления изменяется в соответствии с внешним видом приложения. Можно изменить внешний вид элемента управления, выполнив одно из следующих действий (в зависимости от того, чего нужно достичь):  
  
- Измените значение свойства элемента управления.  
  
- Создайте <xref:System.Windows.Style> для управления.  
  
- Создайте <xref:System.Windows.Controls.ControlTemplate> новый элемент управления.  
  
### <a name="changing-a-controls-property-value"></a>Изменение значения свойства элемента управления  
 Многие элементы управления имеют свойства, которые позволяют <xref:System.Windows.Controls.Control.Background%2A> изменять <xref:System.Windows.Controls.Button>способ отослания элемента управления, например, элемент . Свойства значений можно установить как [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в коде, так и в коде. Следующий пример <xref:System.Windows.Controls.Control.Background%2A>устанавливает, <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.Control.FontWeight%2A> и свойства <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]на в .  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Следующий пример устанавливает те же самые свойства в коде.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Создание стиля для элемента управления  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]дает возможность указать внешний вид элементов управления оптом, вместо установки <xref:System.Windows.Style>свойств на каждом экземпляре в приложении, создавая . Следующий пример <xref:System.Windows.Style> создает, который <xref:System.Windows.Controls.Button> применяется к каждому в приложении. <xref:System.Windows.Style>определения, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] как <xref:System.Windows.ResourceDictionary>правило, определяются в <xref:System.Windows.FrameworkElement.Resources%2A> , <xref:System.Windows.FrameworkElement>например, свойство .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Вы также можете применить стиль только к определенным элементам управления определенного типа, назначив `Style` ключ к стилю и указав этот ключ в свойстве вашего элемента управления.  Для получения дополнительной информации о стилях, [см Стиль и Templating](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Создание шаблона ControlTemplate  
 A <xref:System.Windows.Style> позволяет устанавливать свойства на нескольких элементах управления одновременно, но иногда вы <xref:System.Windows.Controls.Control> можете настроить внешний <xref:System.Windows.Style>вид за то, что вы можете сделать, создав . Классы, которые <xref:System.Windows.Controls.Control> наследуют <xref:System.Windows.Controls.ControlTemplate>от класса имеют , который <xref:System.Windows.Controls.Control>определяет структуру и внешний вид . Свойство <xref:System.Windows.Controls.Control.Template%2A> a <xref:System.Windows.Controls.Control> является общедоступным, поэтому <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> вы можете дать, что отличается от его по умолчанию. Часто можно указать <xref:System.Windows.Controls.ControlTemplate> новое <xref:System.Windows.Controls.Control> для вместо наследования от элемента <xref:System.Windows.Controls.Control>управления, чтобы настроить внешний вид .  
  
 Рассмотрим очень распространенный контроль, <xref:System.Windows.Controls.Button>.  Основное поведение <xref:System.Windows.Controls.Button> a заключается в том, чтобы позволить приложению предпринять некоторые действия, когда пользователь нажимает на него.  По <xref:System.Windows.Controls.Button> умолчанию, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в появляется как поднятый прямоугольник.  При разработке приложения можно воспользоваться поведением, <xref:System.Windows.Controls.Button>т.е. при обработке события нажатия кнопки, но вы можете изменить внешний вид кнопки помимо того, что вы можете сделать, изменив свойства кнопки.  В этом случае можно создать <xref:System.Windows.Controls.ControlTemplate>новый .  
  
 Следующий пример <xref:System.Windows.Controls.ControlTemplate> создает <xref:System.Windows.Controls.Button>для .  <xref:System.Windows.Controls.Button> Создается <xref:System.Windows.Controls.ControlTemplate> с закруглеными углами и градиентным фоном.  <xref:System.Windows.Controls.Border> Содержит, <xref:System.Windows.Controls.ControlTemplate> который <xref:System.Windows.Controls.Border.Background%2A> с <xref:System.Windows.Media.LinearGradientBrush> двумя <xref:System.Windows.Media.GradientStop> объектами.  Первый <xref:System.Windows.Media.GradientStop> использует связывание <xref:System.Windows.Media.GradientStop.Color%2A> данных <xref:System.Windows.Media.GradientStop> для привязки свойства к цвету фона кнопки.  При установке <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button>свойства, цвет этого значения будет использоваться <xref:System.Windows.Media.GradientStop>в качестве первого. Для получения дополнительной информации [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md)о привязке данных см. Пример также <xref:System.Windows.Trigger> создает, что изменяет <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> внешний вид, когда это `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Свойство <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> должно быть установлено <xref:System.Windows.Media.SolidColorBrush> для того, чтобы пример работал должным образом.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Подписка на события  
 Вы можете подписаться на событие элемента управления, используя либо [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или код, но вы можете обрабатывать событие только в коде.  Ниже приводится следующий `Click` <xref:System.Windows.Controls.Button>пример, как подписаться на событие .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Следующий пример обрабатывает `Click` событие <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Форматированное содержимое в элементах управления  
 Большинство классов, которые <xref:System.Windows.Controls.Control> наследуют из класса, имеют возможность содержать богатое содержимое. Например, <xref:System.Windows.Controls.Label> может содержать любой объект, например строку, строку <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Panel>или.  Следующие классы обеспечивают поддержку богатого контента и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]выступают в качестве базовых классов для большинства элементов управления в .  
  
- <xref:System.Windows.Controls.ContentControl>-- Некоторые примеры классов, которые <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button>наследуют <xref:System.Windows.Controls.ToolTip>от этого класса, и .  
  
- <xref:System.Windows.Controls.ItemsControl>-- Некоторые примеры классов, которые <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.Menu>наследуют <xref:System.Windows.Controls.Primitives.StatusBar>от этого класса, и .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- Некоторые примеры классов, которые <xref:System.Windows.Controls.TabItem> <xref:System.Windows.Controls.GroupBox>наследуют <xref:System.Windows.Controls.Expander>от этого класса, и .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Некоторые примеры классов, которые <xref:System.Windows.Controls.MenuItem>наследуют от этого класса, <xref:System.Windows.Controls.TreeViewItem>и <xref:System.Windows.Controls.ToolBar>.  

 Для получения дополнительной информации [WPF Content Model](wpf-content-model.md)об этих базовых классах см.  
  
## <a name="see-also"></a>См. также раздел

- [Стилизация и использование шаблонов](styling-and-templating.md)
- [Категории элементов управления](controls-by-category.md)
- [Библиотека элементов управления](control-library.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Вход](../advanced/input-wpf.md)
- [Включение команды](../advanced/how-to-enable-a-command.md)
- [Пошаговые руководства: создание пользовательской анимированной кнопки](walkthroughs-create-a-custom-animated-button.md)
- [Настройка элементов управления](control-customization.md)
