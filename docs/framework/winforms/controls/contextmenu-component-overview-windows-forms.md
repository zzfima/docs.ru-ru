---
title: Общие сведения о компоненте ContextMenu (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962189"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="95165-102">Общие сведения о компоненте ContextMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="95165-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="95165-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="95165-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="95165-104">С помощью компонента <xref:System.Windows.Forms.ContextMenu> Windows Forms можно предоставить пользователям легко доступное контекстное меню часто используемых команд, связанных с выбранным объектом.</span><span class="sxs-lookup"><span data-stu-id="95165-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="95165-105">Элементы в контекстном меню часто являются подмножеством элементов из главных меню, которые появляются в других частях приложения.</span><span class="sxs-lookup"><span data-stu-id="95165-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="95165-106">Обычно пользователь может получить доступ к контекстному меню, щелкнув его правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="95165-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="95165-107">В Windows Forms контекстные меню связаны с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="95165-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="95165-108">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="95165-108">Key Properties</span></span>  
 <span data-ttu-id="95165-109">Контекстное меню можно связать с элементом управления, присвоив <xref:System.Windows.Forms.Control.ContextMenu%2A> свойству <xref:System.Windows.Forms.ContextMenu> элемента управления компонент.</span><span class="sxs-lookup"><span data-stu-id="95165-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="95165-110">Одно контекстное меню может быть связано с несколькими элементами управления, но у каждого элемента управления может быть только одно контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="95165-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="95165-111">Ключевым свойством <xref:System.Windows.Forms.ContextMenu> компонента <xref:System.Windows.Forms.Menu.MenuItems%2A> является свойство.</span><span class="sxs-lookup"><span data-stu-id="95165-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="95165-112">Элементы меню можно добавлять путем программного создания <xref:System.Windows.Forms.MenuItem> объектов и их добавления <xref:System.Windows.Forms.Menu.MenuItemCollection> в контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="95165-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="95165-113">Поскольку элементы в контекстном меню обычно выводятся из других меню, чаще всего добавляются элементы в контекстное меню путем их копирования.</span><span class="sxs-lookup"><span data-stu-id="95165-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95165-114">См. также</span><span class="sxs-lookup"><span data-stu-id="95165-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
