---
title: Общие сведения о всплывающих подсказках
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: b70387e604b0917d154fc056b904e9ee05f6fbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tooltip-overview"></a>Общие сведения о всплывающих подсказках
Всплывающая подсказка представляет небольшое всплывающее окно, которое появляется при наведении указателя мыши на элемент, например, на <xref:System.Windows.Controls.Button>. В этом разделе рассказывается о всплывающих подсказках и о том, как создавать и настраивать их содержимое.  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>Что такое всплывающая подсказка?  
 Когда пользователь наводит указатель мыши на элемент, для которого имеется всплывающая подсказка, окно с содержимым этой подсказки (например, текстом, описывающим функции этого элемента управления) отображается в течение заданного периода времени. Когда пользователь перемещает указатель мыши за пределы элемента управления, это окно исчезает, так как теперь фокус не направлен на содержимое подсказки.  
  
 Содержимым подсказки может быть одна или несколько строк текста, изображения, фигуры или другие видимые элементы. Чтобы задать всплывающую подсказку для элемента управления, нужно задать одно из следующих свойств содержимого этой всплывающей подсказки.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 Какое свойство использовать зависит ли элемент управления, который определяет подсказку наследует от <xref:System.Windows.FrameworkContentElement> или <xref:System.Windows.FrameworkElement> класса.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>Создание всплывающей подсказки  
 Приведенный ниже показано, как создать простой подсказку, присвоив <xref:System.Windows.FrameworkElement.ToolTip%2A> свойства <xref:System.Windows.Controls.Button> элемента управления в текстовую строку.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Можно также определить подсказку как <xref:System.Windows.Controls.ToolTip> объект. В следующем примере используется [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для указания <xref:System.Windows.Controls.ToolTip> объект как подсказку <xref:System.Windows.Controls.TextBox> элемента. Обратите внимание, что в примере указывается <xref:System.Windows.Controls.ToolTip> , установив <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> свойство.  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 В следующем примере кода используется для создания <xref:System.Windows.Controls.ToolTip> объекта. В примере создается <xref:System.Windows.Controls.ToolTip> (`tt`) и связывает его с <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Можно также создать содержимое подсказки, которая не определена как <xref:System.Windows.Controls.ToolTip> , включив содержимое подсказки в макет элемента, такие как <xref:System.Windows.Controls.DockPanel>. Следующий пример показывает, как задать <xref:System.Windows.FrameworkElement.ToolTip%2A> свойство <xref:System.Windows.Controls.TextBox> на содержимое, которое заключено в <xref:System.Windows.Controls.DockPanel> элемента управления.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Использование свойств классов ToolTip и ToolTipService  
 Содержимое всплывающей подсказки можно настроить, задавая его визуальные свойства и применяя стили. Если определить содержимое подсказки как <xref:System.Windows.Controls.ToolTip> объекта, можно установить свойства visual <xref:System.Windows.Controls.ToolTip> объекта. В противном случае необходимо задать в эквивалентные вложенного свойства <xref:System.Windows.Controls.ToolTipService> класса.  
  
 Пример того, как задать свойства, чтобы указать положение содержимого всплывающей подсказки с помощью <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> свойствах см. [положение подсказки](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>Задание стиля всплывающей подсказки  
 Задать стиль <xref:System.Windows.Controls.ToolTip> , определив пользовательский <xref:System.Windows.Style>. В следующем примере определяется <xref:System.Windows.Style> вызывается `Simple` , показано, как изменить расположение <xref:System.Windows.Controls.ToolTip> и изменить его внешний вид, установив <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, и <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Использование свойств интервала времени элемента ToolTipService  
 <xref:System.Windows.Controls.ToolTipService> Класс предоставляет следующие свойства для задания подсказки отображения времени: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, и <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Используйте <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> и <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> свойства для указания задержки, как правило, короткой, перед <xref:System.Windows.Controls.ToolTip> отображается и Кроме того, чтобы указать, как долго <xref:System.Windows.Controls.ToolTip> остается видимым. Подробнее см. в разделе [Практическое руководство. Задержка отображения всплывающей подсказки](http://msdn.microsoft.com/library/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).  
  
 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> Свойство определяет, если подсказки для различных элементов управления отображаются без начальной задержки при наведении указателя мыши быстро между ними. Дополнительные сведения о <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> свойство, в разделе [руководство](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 В примере ниже показано, как задать эти свойства для всплывающих подсказок.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
