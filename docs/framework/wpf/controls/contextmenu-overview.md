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
# <a name="contextmenu-overview"></a><span data-ttu-id="0546b-102">Общие сведения о ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-102">ContextMenu Overview</span></span>
<span data-ttu-id="0546b-103">Класс <xref:System.Windows.Controls.ContextMenu> представляет элемент, который предоставляет функциональность с <xref:System.Windows.Controls.Menu>помощью контекста.</span><span class="sxs-lookup"><span data-stu-id="0546b-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="0546b-104">Как правило, пользователь <xref:System.Windows.Controls.ContextMenu> разоблачает в правой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] нажатием кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="0546b-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="0546b-105">Эта тема представляет <xref:System.Windows.Controls.ContextMenu> элемент и приводит примеры [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] того, как использовать его в и код.</span><span class="sxs-lookup"><span data-stu-id="0546b-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="0546b-106">Элемент управления ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-106">ContextMenu Control</span></span>  
 <span data-ttu-id="0546b-107">A <xref:System.Windows.Controls.ContextMenu> крепится к определенному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="0546b-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="0546b-108">Элемент <xref:System.Windows.Controls.ContextMenu> позволяет представить пользователям список элементов, которые указывают команды или параметры, связанные с <xref:System.Windows.Controls.Button>определенным элементом управления, например,</span><span class="sxs-lookup"><span data-stu-id="0546b-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="0546b-109">Пользователи нажимают правой кнопкой мыши элемент управления, чтобы появилось меню.</span><span class="sxs-lookup"><span data-stu-id="0546b-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="0546b-110">Обычно нажатие <xref:System.Windows.Controls.MenuItem> кнопки открывает подменю или вызывает выполнение команды приложением.</span><span class="sxs-lookup"><span data-stu-id="0546b-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="0546b-111">Создание элементов ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="0546b-112">Следующие примеры показывают, <xref:System.Windows.Controls.ContextMenu> как создать с подменю.</span><span class="sxs-lookup"><span data-stu-id="0546b-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="0546b-113">Элементы <xref:System.Windows.Controls.ContextMenu> управления крепятся к кнопке управления.</span><span class="sxs-lookup"><span data-stu-id="0546b-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="0546b-114">Применение стилей к ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="0546b-115">С помощью <xref:System.Windows.Style>элемента управления, вы можете резко <xref:System.Windows.Controls.ContextMenu> изменить внешний вид и поведение без написания пользовательского контроля.</span><span class="sxs-lookup"><span data-stu-id="0546b-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="0546b-116">В дополнение к установке визуальных свойств также можно применить стили к частям элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0546b-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="0546b-117">Например, можно изменить поведение частей элемента управления с помощью свойств, или можно добавить <xref:System.Windows.Controls.ContextMenu>части или изменить макет a.</span><span class="sxs-lookup"><span data-stu-id="0546b-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0546b-118">Ниже приведены некоторые примеры, <xref:System.Windows.Controls.ContextMenu> которые могут добавить стили в элементы управления.</span><span class="sxs-lookup"><span data-stu-id="0546b-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="0546b-119">В первом примере определяется стиль с именем `SimpleSysResources`, который показывает, как использовать текущие параметры системы в стиле.</span><span class="sxs-lookup"><span data-stu-id="0546b-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="0546b-120">Пример <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> присваивается как <xref:System.Windows.Controls.Control.Background%2A> цвет и <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> как <xref:System.Windows.Controls.Control.Foreground%2A> цвет . <xref:System.Windows.Controls.ContextMenu></span><span class="sxs-lookup"><span data-stu-id="0546b-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="0546b-121">В следующем примере <xref:System.Windows.Trigger> элемент изменяется <xref:System.Windows.Controls.Menu> внешний вид в ответ <xref:System.Windows.Controls.ContextMenu>на события, поднятые на .</span><span class="sxs-lookup"><span data-stu-id="0546b-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0546b-122">Когда пользователь перемещает мышь по меню, внешний вид <xref:System.Windows.Controls.ContextMenu> элементов меняется.</span><span class="sxs-lookup"><span data-stu-id="0546b-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0546b-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0546b-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="0546b-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="0546b-125">Стили и шаблоны элемента ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0546b-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="0546b-126">Пример коллекции элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="0546b-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
