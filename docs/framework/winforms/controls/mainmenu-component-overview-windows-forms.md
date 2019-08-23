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
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952132"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="7bad5-102">Общие сведения о компоненте MainMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7bad5-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="7bad5-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="7bad5-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="7bad5-104">Компонент Windows Forms <xref:System.Windows.Forms.MainMenu> отображает меню во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7bad5-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="7bad5-105">Все подменю главного меню и отдельных элементов являются <xref:System.Windows.Forms.MenuItem> объектами.</span><span class="sxs-lookup"><span data-stu-id="7bad5-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="7bad5-106">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="7bad5-106">Key Properties</span></span>  
 <span data-ttu-id="7bad5-107">Элемент меню можно назначить в качестве элемента по умолчанию, задав <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> `true`свойству значение.</span><span class="sxs-lookup"><span data-stu-id="7bad5-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="7bad5-108">Элемент по умолчанию отображается полужирным шрифтом при щелчке меню.</span><span class="sxs-lookup"><span data-stu-id="7bad5-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="7bad5-109"><xref:System.Windows.Forms.MenuItem.Checked%2A> Свойство элемента меню имеет значение `true` или `false`, а также указывает, выбран ли пункт меню.</span><span class="sxs-lookup"><span data-stu-id="7bad5-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="7bad5-110"><xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Свойство элемента меню настраивает внешний вид выбранного элемента: Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> для `true`задано значение, рядом `false`с элементом появляется переключатель. Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> параметр имеет значение, рядом с элементом отображается галочка.</span><span class="sxs-lookup"><span data-stu-id="7bad5-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bad5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7bad5-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="7bad5-112">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7bad5-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
