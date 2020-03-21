---
title: Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 7e3480c5a56170ce94d5b5bde0208542c82e7702
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182315"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="d0d89-102">Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d0d89-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="d0d89-103">Вы можете добавить только один пункт меню <xref:System.Windows.Forms.ContextMenuStrip>или несколько пунктов одновременно в .</span><span class="sxs-lookup"><span data-stu-id="d0d89-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="d0d89-104">Добавление одного элемента меню в ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d0d89-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="d0d89-105">Используйте <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> метод, чтобы добавить <xref:System.Windows.Forms.ContextMenuStrip>один элемент меню в .</span><span class="sxs-lookup"><span data-stu-id="d0d89-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="d0d89-106">Добавить несколько элементов меню в ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d0d89-106">To add several menu items to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="d0d89-107">Используйте <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> метод, чтобы добавить <xref:System.Windows.Forms.ContextMenuStrip>несколько пунктов меню в .</span><span class="sxs-lookup"><span data-stu-id="d0d89-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d0d89-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0d89-108">See also</span></span>

- [<span data-ttu-id="d0d89-109">Элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d0d89-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
