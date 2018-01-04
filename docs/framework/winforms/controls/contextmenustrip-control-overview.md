---
title: "Общие сведения об элементе управления ContextMenuStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11d5de760b8a03d7bc35adabb631048a70e20264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="f06f3-102">Общие сведения об элементе управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="f06f3-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="f06f3-103"><xref:System.Windows.Forms.ContextMenuStrip> Управления заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.ContextMenu> управления; Однако <xref:System.Windows.Forms.ContextMenu> Если выбрать элемент управления можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="f06f3-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="f06f3-104">Контекстные меню, также называемый контекстные меню отображаются в положении указателя по щелчку правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="f06f3-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="f06f3-105">Ярлык *меню* предоставляют параметры для клиентской области или элемент управления в положении указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="f06f3-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="f06f3-106"><xref:System.Windows.Forms.ContextMenuStrip> Элемент управления предназначен для эффективной работы с новым <xref:System.Windows.Forms.ToolStrip> и связанных элементов управления, но вы можете связать <xref:System.Windows.Forms.ContextMenuStrip> с другими элементами управления легко.</span><span class="sxs-lookup"><span data-stu-id="f06f3-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="f06f3-107">В следующей таблице показаны важные <xref:System.Windows.Forms.ContextMenuStrip> сопутствующих классов.</span><span class="sxs-lookup"><span data-stu-id="f06f3-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="f06f3-108">Класс</span><span class="sxs-lookup"><span data-stu-id="f06f3-108">Class</span></span>|<span data-ttu-id="f06f3-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f06f3-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="f06f3-110">Представляет отдельные пункты, отображаемые на <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f06f3-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="f06f3-111">Представляет элемент управления, который позволяет пользователю выбрать один элемент из списка, который отображается, когда пользователь нажимает кнопку <xref:System.Windows.Forms.ToolStripDropDownButton> или пункта меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="f06f3-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="f06f3-112">Предоставляет базовые функциональные возможности для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem> , отображения элементов раскрывающегося списка при нажатии.</span><span class="sxs-lookup"><span data-stu-id="f06f3-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f06f3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f06f3-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
