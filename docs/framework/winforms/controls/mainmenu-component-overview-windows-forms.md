---
title: Общие сведения о компоненте MainMenu (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: a7ea9fcf25942f21d2d549ea998161398fbc608f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="b7d26-102">Общие сведения о компоненте MainMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b7d26-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="b7d26-103">Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функциональные возможности в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбрать.</span><span class="sxs-lookup"><span data-stu-id="b7d26-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="b7d26-104">Windows Forms <xref:System.Windows.Forms.MainMenu> компонент отображает меню во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7d26-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="b7d26-105">Все подменю из главного меню и в отдельных элементах отображаются <xref:System.Windows.Forms.MenuItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="b7d26-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b7d26-106">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="b7d26-106">Key Properties</span></span>  
 <span data-ttu-id="b7d26-107">Элемент меню назначается в качестве элемента по умолчанию, задав <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="b7d26-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="b7d26-108">Элемент по умолчанию отображается полужирным шрифтом, при выборе данного меню.</span><span class="sxs-lookup"><span data-stu-id="b7d26-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="b7d26-109">Элемент меню <xref:System.Windows.Forms.MenuItem.Checked%2A> равно либо `true` или `false`и указывает, выбран ли элемент меню.</span><span class="sxs-lookup"><span data-stu-id="b7d26-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="b7d26-110">Элемент меню <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> свойство настраивает внешний вид выбранного элемента: Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> задано значение `true`, появляется переключатель рядом с элементом; Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> имеет значение `false`, отображается флажок рядом с элементом.</span><span class="sxs-lookup"><span data-stu-id="b7d26-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d26-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b7d26-111">See Also</span></span>  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="b7d26-112">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="b7d26-112">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
