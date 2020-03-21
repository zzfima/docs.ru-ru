---
title: Общие сведения о ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185916"
---
# <a name="contextmenu-overview"></a>Общие сведения о ContextMenu
Класс <xref:System.Windows.Controls.ContextMenu> представляет элемент, который предоставляет функциональность с <xref:System.Windows.Controls.Menu>помощью контекста. Как правило, пользователь <xref:System.Windows.Controls.ContextMenu> разоблачает в правой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] нажатием кнопки мыши. Эта тема представляет <xref:System.Windows.Controls.ContextMenu> элемент и приводит примеры [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] того, как использовать его в и код.  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>Элемент управления ContextMenu  
 A <xref:System.Windows.Controls.ContextMenu> крепится к определенному элементу управления. Элемент <xref:System.Windows.Controls.ContextMenu> позволяет представить пользователям список элементов, которые указывают команды или параметры, связанные с <xref:System.Windows.Controls.Button>определенным элементом управления, например, Пользователи нажимают правой кнопкой мыши элемент управления, чтобы появилось меню. Обычно нажатие <xref:System.Windows.Controls.MenuItem> кнопки открывает подменю или вызывает выполнение команды приложением.  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>Создание элементов ContextMenu  
 Следующие примеры показывают, <xref:System.Windows.Controls.ContextMenu> как создать с подменю. Элементы <xref:System.Windows.Controls.ContextMenu> управления крепятся к кнопке управления.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>Применение стилей к ContextMenu  
 С помощью <xref:System.Windows.Style>элемента управления, вы можете резко <xref:System.Windows.Controls.ContextMenu> изменить внешний вид и поведение без написания пользовательского контроля. В дополнение к установке визуальных свойств также можно применить стили к частям элемента управления. Например, можно изменить поведение частей элемента управления с помощью свойств, или можно добавить <xref:System.Windows.Controls.ContextMenu>части или изменить макет a. Ниже приведены некоторые примеры, <xref:System.Windows.Controls.ContextMenu> которые могут добавить стили в элементы управления.  
  
 В первом примере определяется стиль с именем `SimpleSysResources`, который показывает, как использовать текущие параметры системы в стиле. Пример <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> присваивается как <xref:System.Windows.Controls.Control.Background%2A> цвет и <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> как <xref:System.Windows.Controls.Control.Foreground%2A> цвет . <xref:System.Windows.Controls.ContextMenu>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 В следующем примере <xref:System.Windows.Trigger> элемент изменяется <xref:System.Windows.Controls.Menu> внешний вид в ответ <xref:System.Windows.Controls.ContextMenu>на события, поднятые на . Когда пользователь перемещает мышь по меню, внешний вид <xref:System.Windows.Controls.ContextMenu> элементов меняется.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [Стили и шаблоны элемента ContextMenu](contextmenu-styles-and-templates.md)
- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
