---
title: Общие сведения о компоненте MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745112"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="4c477-102">Общие сведения о компоненте MainMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4c477-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4c477-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.</span><span class="sxs-lookup"><span data-stu-id="4c477-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="4c477-104">Компонент <xref:System.Windows.Forms.MainMenu> Windows Forms отображает меню во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4c477-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="4c477-105">Все подменю главного меню и отдельные элементы являются <xref:System.Windows.Forms.MenuItem> объектами.</span><span class="sxs-lookup"><span data-stu-id="4c477-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="4c477-106">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="4c477-106">Key Properties</span></span>  
 <span data-ttu-id="4c477-107">Элемент меню можно назначить в качестве элемента по умолчанию, задав свойству <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4c477-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="4c477-108">Элемент по умолчанию отображается полужирным шрифтом при щелчке меню.</span><span class="sxs-lookup"><span data-stu-id="4c477-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="4c477-109"><xref:System.Windows.Forms.MenuItem.Checked%2A>ым свойством элемента меню является `true` или `false`, а также показывает, выбран ли этот пункт меню.</span><span class="sxs-lookup"><span data-stu-id="4c477-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="4c477-110">Свойство <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> элемента меню настраивает внешний вид выбранного элемента: Если для <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> задано значение `true`, рядом с элементом появляется переключатель. Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> имеет значение `false`, рядом с элементом отображается галочка.</span><span class="sxs-lookup"><span data-stu-id="4c477-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c477-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c477-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="4c477-112">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="4c477-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
