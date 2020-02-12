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
ms.openlocfilehash: b973d47711632f4c0fe56f042545598272c79d2d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124368"
---
# <a name="contextmenu-overview"></a>Общие сведения о ContextMenu
Класс <xref:System.Windows.Controls.ContextMenu> представляет элемент, предоставляющий функциональные возможности с помощью <xref:System.Windows.Controls.Menu>, зависящего от контекста. Как правило, пользователь предоставляет <xref:System.Windows.Controls.ContextMenu> в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], щелкая правой кнопкой мыши. В этом разделе описывается элемент <xref:System.Windows.Controls.ContextMenu> и приводятся примеры его использования в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и коде.  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>Элемент управления ContextMenu  
 <xref:System.Windows.Controls.ContextMenu> присоединяется к конкретному элементу управления. Элемент <xref:System.Windows.Controls.ContextMenu> позволяет представлять пользователям список элементов, которые указывают команды или параметры, связанные с определенным элементом управления, например <xref:System.Windows.Controls.Button>. Пользователи нажимают правой кнопкой мыши элемент управления, чтобы появилось меню. Как правило, щелчок <xref:System.Windows.Controls.MenuItem> открывает подменю или заставляет приложение выполнить команду.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Создание элементов ContextMenu  
 В следующих примерах показано, как создать <xref:System.Windows.Controls.ContextMenu> с подменю. Элементы управления <xref:System.Windows.Controls.ContextMenu> присоединяются к элементам управления "Кнопка".  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Применение стилей к ContextMenu  
 С помощью <xref:System.Windows.Style>элементов управления можно значительно изменить внешний вид и поведение <xref:System.Windows.Controls.ContextMenu> без написания пользовательского элемента управления. В дополнение к установке визуальных свойств также можно применить стили к частям элемента управления. Например, можно изменить поведение частей элемента управления с помощью свойств, а также добавить или изменить макет, <xref:System.Windows.Controls.ContextMenu>. В следующих примерах показано несколько способов добавления стилей к элементам управления <xref:System.Windows.Controls.ContextMenu>.  
  
 В первом примере определяется стиль с именем `SimpleSysResources`, который показывает, как использовать текущие параметры системы в стиле. Этот пример назначает <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> в качестве цвета <xref:System.Windows.Controls.Control.Background%2A> и <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> в качестве <xref:System.Windows.Controls.Control.Foreground%2A>ого цвета <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 В следующем примере элемент <xref:System.Windows.Trigger> используется для изменения внешнего вида <xref:System.Windows.Controls.Menu> в ответ на события, возникающие в <xref:System.Windows.Controls.ContextMenu>. Когда пользователь наводит указатель мыши на меню, изменяется внешний вид <xref:System.Windows.Controls.ContextMenu> элементов.  
  
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
