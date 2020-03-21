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
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181951"
---
# <a name="tooltip-overview"></a>Общие сведения о всплывающих подсказках
Набор инструментов — это небольшое всплывающее окно, которое появляется, когда пользователь приостанавливает указатель мыши над элементом, например <xref:System.Windows.Controls.Button>над . В этом разделе рассказывается о всплывающих подсказках и о том, как создавать и настраивать их содержимое.  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a>Что такое всплывающая подсказка?  
 Когда пользователь наводит указатель мыши на элемент, для которого имеется всплывающая подсказка, окно с содержимым этой подсказки (например, текстом, описывающим функции этого элемента управления) отображается в течение заданного периода времени. Когда пользователь перемещает указатель мыши за пределы элемента управления, это окно исчезает, так как теперь фокус не направлен на содержимое подсказки.  
  
 Содержимым подсказки может быть одна или несколько строк текста, изображения, фигуры или другие видимые элементы. Чтобы задать всплывающую подсказку для элемента управления, нужно задать одно из следующих свойств содержимого этой всплывающей подсказки.  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 Какое свойство вы используете, <xref:System.Windows.FrameworkContentElement> зависит от того, <xref:System.Windows.FrameworkElement> наследует ли элемент управления, определяющий набор инструментов, от класса или класса.  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a>Создание всплывающей подсказки  
 Ниже приводится следующий пример, как создать <xref:System.Windows.FrameworkElement.ToolTip%2A> простой <xref:System.Windows.Controls.Button> набор инструментов, установив свойство для управления строкой текста.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Вы также можете определить набор <xref:System.Windows.Controls.ToolTip> инструментов как объект. В следующем [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере <xref:System.Windows.Controls.ToolTip> используется для указания объекта <xref:System.Windows.Controls.TextBox> в качестве инструмента элемента. Обратите внимание, что пример <xref:System.Windows.Controls.ToolTip> определяет свойство. <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 В следующем примере используется <xref:System.Windows.Controls.ToolTip> код для создания объекта. Пример создает <xref:System.Windows.Controls.ToolTip> a`tt`( ) и <xref:System.Windows.Controls.Button>связывает его с .  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Можно также создать содержимое tooltip, <xref:System.Windows.Controls.ToolTip> которое не определяется как объект, прикладывая содержимое tooltip в элемент макета, например <xref:System.Windows.Controls.DockPanel>. В следующем примере показано, как установить <xref:System.Windows.FrameworkElement.ToolTip%2A> свойство содержимого, <xref:System.Windows.Controls.TextBox> заключенного в <xref:System.Windows.Controls.DockPanel> элемент управления.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Использование свойств классов ToolTip и ToolTipService  
 Содержимое всплывающей подсказки можно настроить, задавая его визуальные свойства и применяя стили. Если вы определяете содержимое <xref:System.Windows.Controls.ToolTip> инструментария как объект, <xref:System.Windows.Controls.ToolTip> можно установить визуальные свойства объекта. В противном случае необходимо установить <xref:System.Windows.Controls.ToolTipService> эквивалентные прилагаемые свойства в классе.  
  
 Например, как установить свойства, чтобы указать положение содержимого <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> инструментария с помощью и свойств, [см.](how-to-position-a-tooltip.md)  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a>Задание стиля всплывающей подсказки  
 Вы можете <xref:System.Windows.Controls.ToolTip> стиль, определив пользовательский <xref:System.Windows.Style>. Следующий пример определяет <xref:System.Windows.Style> `Simple` вызов, который показывает, как <xref:System.Windows.Controls.ToolTip> компенсировать размещение и <xref:System.Windows.Controls.Control.Background%2A>изменить <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A>его <xref:System.Windows.Controls.Control.FontWeight%2A>внешний вид, установив , и .  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Использование свойств интервала времени элемента ToolTipService  
 Класс <xref:System.Windows.Controls.ToolTipService> предоставляет следующие свойства для настройки времени <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>отображения инструментария: , и <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Используйте <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> и свойства, чтобы указать задержку, обычно краткую, перед <xref:System.Windows.Controls.ToolTip> отображанием, а также указать, как долго <xref:System.Windows.Controls.ToolTip> остается видимым. Подробнее см. в разделе [Практическое руководство. Задержка отображения всплывающей подсказки](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).  
  
 Свойство <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> определяет, отображаются ли наконечники инструментов для различных элементов управления без первоначальной задержки при быстром перемещении указателя мыши между ними. Для получения дополнительной <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> информации о собственности, [см.](how-to-use-the-betweenshowdelay-property.md)  
  
 В примере ниже показано, как задать эти свойства для всплывающих подсказок.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [Как-к темам](tooltip-how-to-topics.md)
