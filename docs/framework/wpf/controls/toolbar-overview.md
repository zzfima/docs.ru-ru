---
title: "Общие сведения о панели инструментов ToolBar | Microsoft Docs"
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
  - "элементы управления, ToolBar"
  - "ToolBar - элемент управления"
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Общие сведения о панели инструментов ToolBar
Элементы управления <xref:System.Windows.Controls.ToolBar> являются контейнером для группы команд или элементов управления, обычно связанных между собой по функциональности.  Панель инструментов <xref:System.Windows.Controls.ToolBar> обычно содержит кнопки, которые вызывают команды.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="ToolBarControl"></a>   
## Элемент управления ToolBar  
 Элемент управления <xref:System.Windows.Controls.ToolBar> называется так потому, что выглядит как ряд кнопок или других элементов управления, расположенных как строка или столбец \(англ. tool — инструмент, bar — планка, полоса\).  Элементы управления <xref:System.Windows.Controls.ToolBar> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют механизм переполнения, который помещает в специальную область переполнения все элементы, не попадающие в ограничения по размеру объекта <xref:System.Windows.Controls.ToolBar>.  Кроме того, элементы управления <xref:System.Windows.Controls.ToolBar> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обычно используются со связанным элементом управления <xref:System.Windows.Controls.ToolBarTray>, который предоставляет специальное поведение макета, а также поддержку инициированных пользователем изменений в размерах и размещении панелей инструментов.  
  
<a name="Creating_ToolBars"></a>   
## Указание позиции объектов ToolBar в ToolBarTray  
 Для размещения объекта <xref:System.Windows.Controls.ToolBar> в <xref:System.Windows.Controls.ToolBarTray> используйте свойства <xref:System.Windows.Controls.ToolBar.Band%2A> и <xref:System.Windows.Controls.ToolBar.BandIndex%2A>.  Свойство <xref:System.Windows.Controls.ToolBar.Band%2A> указывает положение объекта <xref:System.Windows.Controls.ToolBar> в его родительском объекте <xref:System.Windows.Controls.ToolBarTray>.  Свойство <xref:System.Windows.Controls.ToolBar.BandIndex%2A> указывает порядок расположения элементов управления <xref:System.Windows.Controls.ToolBar>.  В следующем примере показано использование этого свойства для размещения элементов управления <xref:System.Windows.Controls.ToolBar> внутри <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## Панели инструментов с элементами в области переполнения  
 Часто элемент управления <xref:System.Windows.Controls.ToolBar> содержит больше элементов, чем можно разместить в размере панели инструментов.  В этом случае <xref:System.Windows.Controls.ToolBar> отображает кнопку переполнения.  Для просмотра элементов переполнения пользователь нажимает кнопку переполнения, и элементы отображаются во всплывающем окне ниже <xref:System.Windows.Controls.ToolBar>.  На рисунке, приведенном ниже, показана панель инструментов <xref:System.Windows.Controls.ToolBar> с элементами переполнения.  
  
 ![Панель инструментов с перекрытием](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Панель инструментов с элементами в области переполнения  
  
 Можно указать, что элемент должен размещаться в панели переполнения, присвоив вложенному свойству <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=fullName> значение <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>, <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName> или <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>.  В следующем примере указывается, что последние четыре кнопки в панели инструментов всегда должны быть в панели переполнения.  
  
 [!code-xml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Панель инструментов <xref:System.Windows.Controls.ToolBar> использует <xref:System.Windows.Controls.Primitives.ToolBarPanel> и <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> в ее шаблоне <xref:System.Windows.Controls.ControlTemplate>.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> отвечает за размещение элементов в панели инструментов.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> отвечает за размещение элементов, которые не помещаются на <xref:System.Windows.Controls.ToolBar>.  Пример <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ToolBar> см. в  
  
 [Стили и шаблоны элемента ToolBar](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## См. также  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>   
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>   
 [Определение стиля элементов управления в панели инструментов](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)   
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)