---
title: Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d6343-102">Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d6343-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d6343-103">Помимо связанные элементы управления, вы можете добавить другие элементы управления для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d6343-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6343-104">Также необходимо иметь по крайней мере один связанный элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> или ничего не будет отображаться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6343-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="d6343-105">Добавление несвязанных элементов управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d6343-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="d6343-106">Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d6343-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="d6343-107">Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d6343-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="d6343-108">Можно также изменить размер и расположение элемента управления, изменив **размер** и **позиции** свойств в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="d6343-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="d6343-109">Добавьте по крайней мере один элемент управления с привязкой к данным в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d6343-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d6343-110">Дополнительные сведения см. в разделе [как: отображение привязки данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6343-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="d6343-111">Перетащите элемент управления с **элементов** область шаблона элемента из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d6343-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d6343-112">Обратите внимание, что элемент управления имеет двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="d6343-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="d6343-113">Внутренняя область — *шаблона элемента*; элементы управления, добавленные в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6343-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="d6343-114">Внешняя область является *просмотра*, где будут отображены элементы; элементы управления, добавленные к этой области будет отображаться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6343-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6343-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d6343-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="d6343-116">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d6343-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6343-117">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d6343-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6343-118">Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d6343-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6343-119">Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d6343-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="d6343-120">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d6343-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
