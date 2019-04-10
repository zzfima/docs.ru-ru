---
title: Общие сведения об элементе управления ContextMenuStrip
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: 23699c67de616ba3f535d2527a315aebe7448d3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215824"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="7e625-102">Общие сведения об элементе управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="7e625-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="7e625-103"><xref:System.Windows.Forms.ContextMenuStrip> Управления заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.ContextMenu> управления; Однако <xref:System.Windows.Forms.ContextMenu> элемент управления можно сохранить для обратной совместимости и использования в будущем, если выбран.</span><span class="sxs-lookup"><span data-stu-id="7e625-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="7e625-104">Контекстные меню, также называется контекстные меню, появляются в позиции указателя мыши, когда пользователь щелкает правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="7e625-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="7e625-105">Ярлык *меню* предоставляют параметры для клиентской области или элемент управления в положении указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="7e625-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="7e625-106"><xref:System.Windows.Forms.ContextMenuStrip> Элемент управления предназначен для эффективной работы с новым <xref:System.Windows.Forms.ToolStrip> и связанных элементов управления, но вы можете связать <xref:System.Windows.Forms.ContextMenuStrip> с другими элементами управления так же легко.</span><span class="sxs-lookup"><span data-stu-id="7e625-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="7e625-107">В следующей таблице показаны важные <xref:System.Windows.Forms.ContextMenuStrip> сопутствующих классов.</span><span class="sxs-lookup"><span data-stu-id="7e625-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="7e625-108">Класс</span><span class="sxs-lookup"><span data-stu-id="7e625-108">Class</span></span>|<span data-ttu-id="7e625-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7e625-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="7e625-110">Представляет отдельные пункты, отображаемые на <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7e625-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="7e625-111">Представляет элемент управления, который позволяет пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или пункта меню более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="7e625-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="7e625-112">Предоставляет базовую функциональность для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem> , отображения элементов раскрывающегося списка при нажатии.</span><span class="sxs-lookup"><span data-stu-id="7e625-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e625-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7e625-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
