---
title: "Общие сведения о ContextMenu | Microsoft Docs"
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
  - "ContextMenu - элементы управления [WPF], об элементах управления ContextMenu"
  - "элементы управления, ContextMenu"
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Общие сведения о ContextMenu
Класс <xref:System.Windows.Controls.ContextMenu> представляет элемент, предоставляющий функциональные возможности с помощью контекстного <xref:System.Windows.Controls.Menu>.  Как правило, <xref:System.Windows.Controls.ContextMenu> предоставляется пользователю в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] по щелчку правой кнопкой мыши.  В этом разделе рассматривается элемент <xref:System.Windows.Controls.ContextMenu> и примеры его использования в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="contextmenu_control"></a>   
## Элемент управления ContextMenu  
 <xref:System.Windows.Controls.ContextMenu> присоединяется к определенному элементу управления.  Элемент <xref:System.Windows.Controls.ContextMenu> позволяет представлять пользователям список элементов, определяющих команды или параметры, которые связаны с определенным элементом управления, таким как <xref:System.Windows.Controls.Button>.  Для отображения меню пользователю необходимо нажать правую кнопку мыши на элементе управления.  Как правило, при нажатии <xref:System.Windows.Controls.MenuItem> открывается подменю или вызывается приложение для выполнения команды.  
  
<a name="creating_contextmenus"></a>   
## Создание ContextMenus  
 В следующем примере показано, как создать <xref:System.Windows.Controls.ContextMenu> с подменю.  Элементы управления <xref:System.Windows.Controls.ContextMenu> привязываются к кнопкам.  
  
 [!code-xml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## Применение стилей к ContextMenu  
 С помощью элемента управления <xref:System.Windows.Style> можно значительно изменить внешний вид и поведение <xref:System.Windows.Controls.ContextMenu> без написания пользовательского элемента управления.  В дополнение к визуальным свойствам можно также применить стили к частям элемента управления.  Например, можно изменить поведение части элемента управления с помощью свойств, добавить в него часть или изменить макет <xref:System.Windows.Controls.ContextMenu>.  В следующем примере показано несколько способов добавления стилей к элементам управления <xref:System.Windows.Controls.ContextMenu>.  
  
 В первом примере определяется стиль с именем `SimpleSysResources`, который показывает, как использовать текущие параметры системы в стиле.  В примере <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> назначается в качестве цвета <xref:System.Windows.Controls.Control.Background%2A> и <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> в качестве цвета <xref:System.Windows.Controls.Control.Foreground%2A> для <xref:System.Windows.Controls.ContextMenu>.  
  
```  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 В следующем примере элемент <xref:System.Windows.Trigger> используется, чтобы изменить внешний вид <xref:System.Windows.Controls.Menu> в ответ на событие, которое вызывается на <xref:System.Windows.Controls.ContextMenu>.  Когда пользователь помещает указатель мыши на меню, изменяется внешний вид элементов <xref:System.Windows.Controls.ContextMenu>.  
  
```  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## См. также  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.Menu>   
 <xref:System.Windows.Controls.MenuItem>   
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)   
 [Стили и шаблоны элемента ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)   
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)