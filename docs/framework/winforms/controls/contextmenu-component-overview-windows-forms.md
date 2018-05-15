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
ms.openlocfilehash: 5d548815533e8f9bb37ad00129a5ae526612ea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="20f30-102">Общие сведения о компоненте ContextMenu (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="20f30-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="20f30-103">Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функциональные возможности в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбрать.</span><span class="sxs-lookup"><span data-stu-id="20f30-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="20f30-104">С помощью Windows Forms <xref:System.Windows.Forms.ContextMenu> компонента, вы можете предоставить пользователям доступного контекстного меню часто используемых команд, связанных с выделенным объектом.</span><span class="sxs-lookup"><span data-stu-id="20f30-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="20f30-105">Элементы контекстного меню часто представляют собой подмножество элементов из главного меню, которые отображаются в другом месте в приложении.</span><span class="sxs-lookup"><span data-stu-id="20f30-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="20f30-106">Как правило, пользователь может открыть контекстное меню щелчком правой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="20f30-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="20f30-107">В формах Windows Forms контекстные меню связаны с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="20f30-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="20f30-108">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="20f30-108">Key Properties</span></span>  
 <span data-ttu-id="20f30-109">Контекстное меню можно связать с элементом управления, присвоив свойству элемента управления <xref:System.Windows.Forms.Control.ContextMenu%2A> свойства <xref:System.Windows.Forms.ContextMenu> компонента.</span><span class="sxs-lookup"><span data-stu-id="20f30-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="20f30-110">Одно контекстное меню можно связать с несколькими элементами управления, но каждый элемент управления может иметь только одно контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="20f30-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="20f30-111">Ключевое свойство <xref:System.Windows.Forms.ContextMenu> компонент является <xref:System.Windows.Forms.Menu.MenuItems%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="20f30-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="20f30-112">Можно добавить элементы меню, создание программным путем <xref:System.Windows.Forms.MenuItem> объектов и добавления их в <xref:System.Windows.Forms.Menu.MenuItemCollection> контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="20f30-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="20f30-113">Так как элементы в контекстном меню, обычно являются производными от других меню, чаще всего будет добавления элементов в контекстном меню, скопировав их.</span><span class="sxs-lookup"><span data-stu-id="20f30-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f30-114">См. также</span><span class="sxs-lookup"><span data-stu-id="20f30-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
