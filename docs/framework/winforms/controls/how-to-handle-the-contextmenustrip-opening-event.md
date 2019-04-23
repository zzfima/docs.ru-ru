---
title: Практическое руководство. Обработка события Opening компонента ContextMenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170722"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="dcd33-102">Практическое руководство. Обработка события Opening компонента ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="dcd33-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="dcd33-103">Можно настроить поведение вашей <xref:System.Windows.Forms.ContextMenuStrip> управления путем обработки <xref:System.Windows.Forms.ToolStripDropDown.Opening> событий.</span><span class="sxs-lookup"><span data-stu-id="dcd33-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcd33-104">Пример</span><span class="sxs-lookup"><span data-stu-id="dcd33-104">Example</span></span>  
 <span data-ttu-id="dcd33-105">В следующем примере кода показано, как обрабатывать <xref:System.Windows.Forms.ToolStripDropDown.Opening> событий.</span><span class="sxs-lookup"><span data-stu-id="dcd33-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="dcd33-106">Обработчик событий добавляет элементы динамически в <xref:System.Windows.Forms.ContextMenuStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dcd33-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="dcd33-107">Полный пример кода, см. в разделе [как: Динамическое добавление элементов ToolStrip](how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="dcd33-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="dcd33-108">Задайте <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> свойства `true` чтобы препятствовать открытию меню.</span><span class="sxs-lookup"><span data-stu-id="dcd33-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd33-109">См. также</span><span class="sxs-lookup"><span data-stu-id="dcd33-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="dcd33-110">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="dcd33-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
