---
title: Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 4a84571bf8b81cd26c864edcd4d313a4009dda16
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592422"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="fb838-102">Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="fb838-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="fb838-103">Внешний вид элемента управления <xref:System.Windows.Forms.ToolStrip> можно настроить путем реализации класса, производного от <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="fb838-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="fb838-104">Это дает возможность создать внешний вид, который отличается от внешнего вида, предоставляемого классами <xref:System.Windows.Forms.ToolStripProfessionalRenderer> и <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="fb838-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb838-105">Пример</span><span class="sxs-lookup"><span data-stu-id="fb838-105">Example</span></span>  
 <span data-ttu-id="fb838-106">В следующем примере кода показано создание пользовательского класса <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="fb838-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="fb838-107">В этом примере элемент управления `GridStrip` реализует головоломку "Пятнашки", которая позволяет пользователю перемещать элементы мозаики в табличном макете для формирования изображения.</span><span class="sxs-lookup"><span data-stu-id="fb838-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="fb838-108">Пользовательский элемент управления <xref:System.Windows.Forms.ToolStrip> упорядочивает элементы управления <xref:System.Windows.Forms.ToolStripButton> в виде сетки.</span><span class="sxs-lookup"><span data-stu-id="fb838-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="fb838-109">Макет содержит одну пустую ячейку, в которую можно сдвинуть соседний элемент мозаики, используя операцию перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fb838-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="fb838-110">Элементы мозаики, которые пользователь может перемещать, выделяются.</span><span class="sxs-lookup"><span data-stu-id="fb838-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="fb838-111">Класс `GridStripRenderer` настраивает три характеристики внешнего вида элемента управления `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="fb838-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="fb838-112">граница `GridStrip`;</span><span class="sxs-lookup"><span data-stu-id="fb838-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="fb838-113">граница <xref:System.Windows.Forms.ToolStripButton>;</span><span class="sxs-lookup"><span data-stu-id="fb838-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="fb838-114"><xref:System.Windows.Forms.ToolStripButton> Изображение</span><span class="sxs-lookup"><span data-stu-id="fb838-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb838-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fb838-115">Compiling the Code</span></span>  
 <span data-ttu-id="fb838-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="fb838-116">This example requires:</span></span>  
  
- <span data-ttu-id="fb838-117">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fb838-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb838-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fb838-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="fb838-119">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fb838-119">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
