---
title: Общие сведения об элементе управления ContextMenu
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746196"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="003df-102">Общие сведения о компоненте ContextMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="003df-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="003df-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.</span><span class="sxs-lookup"><span data-stu-id="003df-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="003df-104">С помощью компонента Windows Forms <xref:System.Windows.Forms.ContextMenu> можно предоставить пользователям легко доступное контекстное меню часто используемых команд, связанных с выбранным объектом.</span><span class="sxs-lookup"><span data-stu-id="003df-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="003df-105">Элементы в контекстном меню часто являются подмножеством элементов из главных меню, которые появляются в других частях приложения.</span><span class="sxs-lookup"><span data-stu-id="003df-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="003df-106">Обычно пользователь может получить доступ к контекстному меню, щелкнув его правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="003df-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="003df-107">В Windows Forms контекстные меню связаны с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="003df-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="003df-108">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="003df-108">Key Properties</span></span>  
 <span data-ttu-id="003df-109">Контекстное меню можно связать с элементом управления, присвоив свойству <xref:System.Windows.Forms.Control.ContextMenu%2A> элемента управления компоненту <xref:System.Windows.Forms.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="003df-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="003df-110">Одно контекстное меню может быть связано с несколькими элементами управления, но у каждого элемента управления может быть только одно контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="003df-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="003df-111">Ключевым свойством <xref:System.Windows.Forms.ContextMenu> компонента является свойство <xref:System.Windows.Forms.Menu.MenuItems%2A>.</span><span class="sxs-lookup"><span data-stu-id="003df-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="003df-112">Элементы меню можно добавлять путем программного создания объектов <xref:System.Windows.Forms.MenuItem> и их добавления в <xref:System.Windows.Forms.Menu.MenuItemCollection> контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="003df-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="003df-113">Поскольку элементы в контекстном меню обычно выводятся из других меню, чаще всего добавляются элементы в контекстное меню путем их копирования.</span><span class="sxs-lookup"><span data-stu-id="003df-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003df-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="003df-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
