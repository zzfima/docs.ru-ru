---
title: "Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a717f951e7e804a9f0e06cb51458d7d691632c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="d24ea-102">Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="d24ea-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="d24ea-103">Внешний вид элемента управления <xref:System.Windows.Forms.ToolStrip> можно настроить путем реализации класса, производного от <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="d24ea-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="d24ea-104">Это дает возможность создать внешний вид, который отличается от внешнего вида, предоставляемого классами <xref:System.Windows.Forms.ToolStripProfessionalRenderer> и <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="d24ea-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d24ea-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d24ea-105">Example</span></span>  
 <span data-ttu-id="d24ea-106">В следующем примере кода показано создание пользовательского класса <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="d24ea-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="d24ea-107">В этом примере элемент управления `GridStrip` реализует головоломку "Пятнашки", которая позволяет пользователю перемещать элементы мозаики в табличном макете для формирования изображения.</span><span class="sxs-lookup"><span data-stu-id="d24ea-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="d24ea-108">Пользовательский элемент управления <xref:System.Windows.Forms.ToolStrip> упорядочивает элементы управления <xref:System.Windows.Forms.ToolStripButton> в виде сетки.</span><span class="sxs-lookup"><span data-stu-id="d24ea-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="d24ea-109">Макет содержит одну пустую ячейку, в которую можно сдвинуть соседний элемент мозаики, используя операцию перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d24ea-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="d24ea-110">Элементы мозаики, которые пользователь может перемещать, выделяются.</span><span class="sxs-lookup"><span data-stu-id="d24ea-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="d24ea-111">Класс `GridStripRenderer` настраивает три характеристики внешнего вида элемента управления `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="d24ea-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="d24ea-112">граница `GridStrip`;</span><span class="sxs-lookup"><span data-stu-id="d24ea-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="d24ea-113">граница <xref:System.Windows.Forms.ToolStripButton>;</span><span class="sxs-lookup"><span data-stu-id="d24ea-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="d24ea-114">изображение <xref:System.Windows.Forms.ToolStripButton>.</span><span class="sxs-lookup"><span data-stu-id="d24ea-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d24ea-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d24ea-115">Compiling the Code</span></span>  
 <span data-ttu-id="d24ea-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d24ea-116">This example requires:</span></span>  
  
-   <span data-ttu-id="d24ea-117">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d24ea-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d24ea-118">Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d24ea-118">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d24ea-119">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="d24ea-119">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="d24ea-120">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d24ea-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24ea-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d24ea-121">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="d24ea-122">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d24ea-122">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
