---
title: Практическое руководство. Практическое
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: c6150b23cf8390a31c6b77ae3c56cfb898eded4b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723014"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="5fadc-102">Практическое руководство. Практическое</span><span class="sxs-lookup"><span data-stu-id="5fadc-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="5fadc-103">Внешний вид элемента управления <xref:System.Windows.Forms.ToolStrip> можно настроить путем реализации класса, производного от <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="5fadc-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="5fadc-104">Это дает возможность создать внешний вид, который отличается от внешнего вида, предоставляемого классами <xref:System.Windows.Forms.ToolStripProfessionalRenderer> и <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="5fadc-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fadc-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5fadc-105">Example</span></span>  
 <span data-ttu-id="5fadc-106">В следующем примере кода показано создание пользовательского класса <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="5fadc-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="5fadc-107">В этом примере элемент управления `GridStrip` реализует головоломку "Пятнашки", которая позволяет пользователю перемещать элементы мозаики в табличном макете для формирования изображения.</span><span class="sxs-lookup"><span data-stu-id="5fadc-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="5fadc-108">Пользовательский элемент управления <xref:System.Windows.Forms.ToolStrip> упорядочивает элементы управления <xref:System.Windows.Forms.ToolStripButton> в виде сетки.</span><span class="sxs-lookup"><span data-stu-id="5fadc-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="5fadc-109">Макет содержит одну пустую ячейку, в которую можно сдвинуть соседний элемент мозаики, используя операцию перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="5fadc-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="5fadc-110">Элементы мозаики, которые пользователь может перемещать, выделяются.</span><span class="sxs-lookup"><span data-stu-id="5fadc-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="5fadc-111">Класс `GridStripRenderer` настраивает три характеристики внешнего вида элемента управления `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="5fadc-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="5fadc-112">граница `GridStrip`;</span><span class="sxs-lookup"><span data-stu-id="5fadc-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="5fadc-113">граница <xref:System.Windows.Forms.ToolStripButton>;</span><span class="sxs-lookup"><span data-stu-id="5fadc-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="5fadc-114">изображение <xref:System.Windows.Forms.ToolStripButton>.</span><span class="sxs-lookup"><span data-stu-id="5fadc-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5fadc-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5fadc-115">Compiling the Code</span></span>  
 <span data-ttu-id="5fadc-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="5fadc-116">This example requires:</span></span>  
  
-   <span data-ttu-id="5fadc-117">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5fadc-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5fadc-118">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5fadc-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5fadc-119">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="5fadc-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fadc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5fadc-120">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="5fadc-121">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5fadc-121">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
