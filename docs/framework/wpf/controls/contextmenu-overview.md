---
title: "Общие сведения о ContextMenu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3061b7fed225f00bf6bb91efe529de35a5a036a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-overview"></a>Общие сведения о ContextMenu
<xref:System.Windows.Controls.ContextMenu> Класс представляет элемент, который предоставляет функциональные возможности с помощью контекстно зависимых <xref:System.Windows.Controls.Menu>. Как правило, предоставляется пользователю <xref:System.Windows.Controls.ContextMenu> в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] щелкните правой кнопкой мыши кнопку мыши. В этом разделе описываются <xref:System.Windows.Controls.ContextMenu> элемент и приводятся примеры того, как использовать его в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и код.  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>Элемент управления ContextMenu  
 Объект <xref:System.Windows.Controls.ContextMenu> присоединяется к конкретному элементу управления. <xref:System.Windows.Controls.ContextMenu> Элемент позволяет представлять пользователям список элементов, определяющих команды или параметры, связанные с конкретным элементом управления, например, <xref:System.Windows.Controls.Button>. Пользователи нажимают правой кнопкой мыши элемент управления, чтобы появилось меню. Как правило, щелкнув <xref:System.Windows.Controls.MenuItem> открывает подменю или вызывает приложение для выполнения команды.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Создание элементов ContextMenu  
 В следующих примерах показано создание <xref:System.Windows.Controls.ContextMenu> с вложенными меню. <xref:System.Windows.Controls.ContextMenu> Элементы присоединяются к элемента управления button.  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Применение стилей к ContextMenu  
 С помощью элемента управления <xref:System.Windows.Style>, можно значительно изменить внешний вид и поведение <xref:System.Windows.Controls.ContextMenu> без написания пользовательского элемента управления. В дополнение к установке визуальных свойств также можно применить стили к частям элемента управления. Например, можно изменить поведение части элемента управления с помощью свойств, или добавить в него часть или изменить макет, <xref:System.Windows.Controls.ContextMenu>. В следующих примерах показано несколько способов добавления стилей к <xref:System.Windows.Controls.ContextMenu> элементов управления.  
  
 В первом примере определяется стиль с именем `SimpleSysResources`, который показывает, как использовать текущие параметры системы в стиле. Этот пример назначает <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> как <xref:System.Windows.Controls.Control.Background%2A> цвета и <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> как <xref:System.Windows.Controls.Control.Foreground%2A> цвет <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 В следующем примере используется <xref:System.Windows.Trigger> элемент, чтобы изменить внешний вид <xref:System.Windows.Controls.Menu> в ответ на события, возникающие на <xref:System.Windows.Controls.ContextMenu>. При перемещении пользователем указателя мыши за его пределы вида <xref:System.Windows.Controls.ContextMenu> элементы изменения.  
  
```xaml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [Стили и шаблоны элемента ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [Пример коллекции элементов управления WPF](http://go.microsoft.com/fwlink/?LinkID=160053)
