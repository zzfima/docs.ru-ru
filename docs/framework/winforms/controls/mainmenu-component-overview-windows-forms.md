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
ms.openlocfilehash: 6c2c33c8c03751e87d71e65523b82d92b18f31c4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709886"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="77611-102">Общие сведения о компоненте MainMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="77611-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="77611-103">Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления из предыдущих версий <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбран.</span><span class="sxs-lookup"><span data-stu-id="77611-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="77611-104">Windows Forms <xref:System.Windows.Forms.MainMenu> компонент отображает меню во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="77611-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="77611-105">Все подменю из главного меню и отдельные элементы отображаются <xref:System.Windows.Forms.MenuItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="77611-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="77611-106">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="77611-106">Key Properties</span></span>  
 <span data-ttu-id="77611-107">Пункт меню может быть объявлен как элемент по умолчанию, задав <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="77611-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="77611-108">Элемент по умолчанию отображается полужирным шрифтом, при выборе меню.</span><span class="sxs-lookup"><span data-stu-id="77611-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="77611-109">Элемент меню <xref:System.Windows.Forms.MenuItem.Checked%2A> свойство `true` или `false`и указывает, выбран ли элемент меню.</span><span class="sxs-lookup"><span data-stu-id="77611-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="77611-110">Элемент меню <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> свойство настраивает внешний вид выбранного элемента: Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> присваивается `true`, типа "переключатель" отображается рядом с элементом; Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> имеет значение `false`, появится флажок рядом с элементом.</span><span class="sxs-lookup"><span data-stu-id="77611-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77611-111">См. также</span><span class="sxs-lookup"><span data-stu-id="77611-111">See also</span></span>
- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="77611-112">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="77611-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
