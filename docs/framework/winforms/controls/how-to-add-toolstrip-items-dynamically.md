---
title: Практическое руководство. Динамическое добавление элементов ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: 08d08a292995cc5e12fbab3e91a0962c3b895a02
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588874"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="f3393-102">Практическое руководство. Динамическое добавление элементов ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f3393-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="f3393-103">Коллекцию пунктов меню элемента управления <xref:System.Windows.Forms.ToolStrip> можно динамически заполнять при открытии меню.</span><span class="sxs-lookup"><span data-stu-id="f3393-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3393-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f3393-104">Example</span></span>  
 <span data-ttu-id="f3393-105">В примере кода ниже демонстрируется динамическое добавление элементов в элемент управления <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f3393-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="f3393-106">В примере также показано повторное использование <xref:System.Windows.Forms.ContextMenuStrip> для трех различных элементов управления в форме.</span><span class="sxs-lookup"><span data-stu-id="f3393-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="f3393-107">В примере обработчик событий <xref:System.Windows.Forms.ToolStripDropDown.Opening> заполняет коллекцию пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="f3393-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="f3393-108">Обработчик событий <xref:System.Windows.Forms.ToolStripDropDown.Opening> анализирует свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> и добавляет элемент <xref:System.Windows.Forms.ToolStripItem>, описывающий исходный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f3393-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3393-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f3393-109">Compiling the Code</span></span>  
 <span data-ttu-id="f3393-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f3393-110">This example requires:</span></span>  
  
- <span data-ttu-id="f3393-111">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f3393-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3393-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f3393-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="f3393-113">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f3393-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
