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
ms.openlocfilehash: 85729082d34cc976fabdbc50629b528c5f28cf54
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624084"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="2f11f-102">Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="2f11f-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="2f11f-103">Можно добавить только один элемент меню или несколько элементов за раз, чтобы <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2f11f-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="2f11f-104">Чтобы добавить отдельный элемент меню в элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="2f11f-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="2f11f-105">Используйте <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> метод для добавления одного пункта меню <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2f11f-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="2f11f-106">Чтобы добавить несколько пунктов меню в элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="2f11f-106">To add several menu items to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="2f11f-107">Используйте <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> метод, чтобы добавить несколько пунктов меню, чтобы <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2f11f-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f11f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2f11f-108">See also</span></span>

- [<span data-ttu-id="2f11f-109">Элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="2f11f-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
