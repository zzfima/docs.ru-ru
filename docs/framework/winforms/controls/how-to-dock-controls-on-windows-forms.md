---
title: Практическое руководство. Закрепление элементов управления в формах Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 6cb4c982cb4c9e2df8d0335738ca087733209bdc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="3783a-102">Практическое руководство. Закрепление элементов управления в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3783a-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="3783a-103">Можно закрепить элементы управления по границам формы или их заполнения контейнера элемента управления (форму или контейнерный элемент управления).</span><span class="sxs-lookup"><span data-stu-id="3783a-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="3783a-104">Например, проводник закрепляет его <xref:System.Windows.Forms.TreeView> в левой части окна элемента управления и его <xref:System.Windows.Forms.ListView> элемента управления в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="3783a-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="3783a-105">Используйте <xref:System.Windows.Forms.Control.Dock%2A> свойство для всех видимых элементов управления Windows Forms для определения режима закрепления.</span><span class="sxs-lookup"><span data-stu-id="3783a-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3783a-106">Элементы управления закрепляются в обратном z порядке.</span><span class="sxs-lookup"><span data-stu-id="3783a-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="3783a-107"><xref:System.Windows.Forms.Control.Dock%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3783a-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="3783a-108">Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3783a-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="3783a-109">Чтобы закрепить элемент управления</span><span class="sxs-lookup"><span data-stu-id="3783a-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="3783a-110">Выберите элемент управления, который требуется закрепить.</span><span class="sxs-lookup"><span data-stu-id="3783a-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="3783a-111">В окне «Свойства» щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3783a-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="3783a-112">Откроется редактор, показывающий набор полей, соответствующих краям и центру формы.</span><span class="sxs-lookup"><span data-stu-id="3783a-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="3783a-113">Нажмите кнопку, которая представляет края формы, в которой вы хотите закрепить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="3783a-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="3783a-114">Чтобы заполнить содержимое элемента управления в форму или контейнерный элемент управления, щелкните поле center.</span><span class="sxs-lookup"><span data-stu-id="3783a-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="3783a-115">Нажмите кнопку **(нет)** для запрещения закрепления.</span><span class="sxs-lookup"><span data-stu-id="3783a-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="3783a-116">Элемент управления изменяется автоматически в соответствии с границами закрепленной позиции.</span><span class="sxs-lookup"><span data-stu-id="3783a-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3783a-117">Наследуемые элементы управления должны быть `Protected` могли быть закреплено.</span><span class="sxs-lookup"><span data-stu-id="3783a-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="3783a-118">Чтобы изменить уровень доступа элемента управления, установите его **модификатор** в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="3783a-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3783a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3783a-119">See Also</span></span>  
 [<span data-ttu-id="3783a-120">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="3783a-121">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="3783a-122">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="3783a-123">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="3783a-124">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="3783a-125">Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="3783a-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="3783a-126">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="3783a-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="3783a-127">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="3783a-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="3783a-128">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3783a-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
