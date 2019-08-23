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
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962154"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="a2778-102">Общие сведения об элементе управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a2778-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="a2778-103">Элемент управления заменяет и расширяет функциональные возможности <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.ContextMenu> элемента управления, однако он сохраняется для обеспечения обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="a2778-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a2778-104">Контекстные меню, также называемые контекстными меню, отображаются в позиции указателя мыши при нажатии пользователем правой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="a2778-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="a2778-105">Контекстные *меню* предоставляют параметры для клиентской области или элемента управления в расположении указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="a2778-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="a2778-106">Этот <xref:System.Windows.Forms.ContextMenuStrip> элемент управления предназначен для беспрепятственной работы с новыми <xref:System.Windows.Forms.ToolStrip> и связанными элементами управления, <xref:System.Windows.Forms.ContextMenuStrip> но его можно связать с другими элементами управления так же просто.</span><span class="sxs-lookup"><span data-stu-id="a2778-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="a2778-107">В следующей таблице показаны важные <xref:System.Windows.Forms.ContextMenuStrip> сопутствующие классы.</span><span class="sxs-lookup"><span data-stu-id="a2778-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="a2778-108">Класс</span><span class="sxs-lookup"><span data-stu-id="a2778-108">Class</span></span>|<span data-ttu-id="a2778-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a2778-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="a2778-110">Представляет выбираемый параметр, отображаемый в <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="a2778-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="a2778-111">Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или элемент меню более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="a2778-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="a2778-112">Предоставляет базовые функциональные возможности для элементов управления <xref:System.Windows.Forms.ToolStripItem> , производных от элементов с раскрывающимися списками при щелчке.</span><span class="sxs-lookup"><span data-stu-id="a2778-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2778-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a2778-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
