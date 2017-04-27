---
title: "Общие сведения о всплывающих подсказках | Microsoft Docs"
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
  - "элементы управления, ToolTip"
  - "ToolTip - элемент управления, сведения об элементе управления ToolTip"
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Общие сведения о всплывающих подсказках
Всплывающая подсказка представляет собой небольшое всплывающее окно, которое появляется, когда пользователь задерживает указатель мыши на элементе, например, на <xref:System.Windows.Controls.Button>.  В этом разделе представлены всплывающие подсказки и способы создания и настройки содержимого всплывающей подсказки.  
  
   
  
<a name="what_is_a_tooltip"></a>   
## Что такое всплывающие подсказки?  
 Когда пользователь перемещает указатель мыши на элемент, который имеет всплывающую подсказку, в течение указанного промежутка времени всплывает окно с содержимым подсказки \(например, в содержимом текста описываются функции элемента управления\).  Если пользователь убирает указатель мыши с элемента управления, окно исчезает, так как содержимое подсказки не может получить фокус.  
  
 Содержимое подсказки может содержать одну или несколько строк текста, рисунки, фигуры или другое визуальное содержимое.  Можно определить всплывающую подсказку для элемента управления настройкой одного из следующих свойств содержимого всплывающей подсказки.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>  
  
 Какое свойство используется, зависит от того, наследует ли элемент управления, определяющий подсказку, от класса <xref:System.Windows.FrameworkContentElement> или <xref:System.Windows.FrameworkElement>.  
  
<a name="create_tooltip"></a>   
## Создание всплывающей подсказки  
 В следующем примере представлены способы создания простых подсказок установкой свойства <xref:System.Windows.FrameworkElement.ToolTip%2A> элемента управления <xref:System.Windows.Controls.Button> в значение строки.  
  
 [!code-xml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Можно также определить подсказку как объект <xref:System.Windows.Controls.ToolTip>.  В следующем примере используется [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для задания объекта <xref:System.Windows.Controls.ToolTip> в качестве подсказки элемента <xref:System.Windows.Controls.TextBox>.  Обратите внимание, что в примере <xref:System.Windows.Controls.ToolTip> задается установкой свойства <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>.  
  
 [!code-xml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 В следующем примере используется код для создания объекта <xref:System.Windows.Controls.ToolTip>.  В примере создается объект <xref:System.Windows.Controls.ToolTip> \(`tt`\) и связывается с объектом <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Можно также создать содержимое подсказки, которая не определена как объект <xref:System.Windows.Controls.ToolTip>, включив содержимое подсказки в макет элемента, например <xref:System.Windows.Controls.DockPanel>.  В следующем примере показано, как установить свойство <xref:System.Windows.FrameworkElement.ToolTip%2A> для содержимого <xref:System.Windows.Controls.TextBox>, заключенного в элементе управления <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-xml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## Использование свойств классов ToolTip и ToolTipService  
 Можно настроить содержимое подсказки, задав визуальные свойства и используя стили.  Если определить содержимое подсказки как объект <xref:System.Windows.Controls.ToolTip>, то можно установить визуальные свойства объекта <xref:System.Windows.Controls.ToolTip>.  В противном случае необходимо задать эквивалент [вложенных свойств](GTMT) в классе <xref:System.Windows.Controls.ToolTipService>.  
  
 Пример задания свойства в порядке указания содержимого подсказки с помощью <xref:System.Windows.Controls.ToolTip> и <xref:System.Windows.Controls.ToolTipService> см. в разделе [Задание положения всплывающей подсказки](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## Стилизация всплывающей подсказки  
 Можно стилизовать <xref:System.Windows.Controls.ToolTip> путем определения пользовательского <xref:System.Windows.Style>.  В следующем примере определяется <xref:System.Windows.Style>, названный `Simple`, и показано, как изменить расположение <xref:System.Windows.Controls.ToolTip> и изменить его внешний вид, установив <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## Использование свойств временного интервала ToolTipService  
 <xref:System.Windows.Controls.ToolTipService> класс предоставляет следующие свойства для задания времени отображения подсказки: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, и <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Используйте <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> и<xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> свойства для указания задержки, как правило, короткой, перед появлением <xref:System.Windows.Controls.ToolTip>, а так же для указания того, как долго <xref:System.Windows.Controls.ToolTip> останется видимой.  Дополнительные сведения см. в разделе [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/ru-ru/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).  
  
 Свойство <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> определяет, отображаются ли подсказки для различных элементов управления без начальной задержки при быстром перемещении указателя мыши между ними.  Дополнительные сведения о свойстве <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> см. в разделе [Использование свойства BetweenShowDelay](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 В следующем примере показано, как настроить эти свойства для всплывающих подсказок.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## См. также  
 <xref:System.Windows.Controls.ToolTipService>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipEventArgs>   
 <xref:System.Windows.Controls.ToolTipEventHandler>   
 [Практические руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)