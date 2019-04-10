---
title: Практическое руководство. Закрепление элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 61ccad615eec81eb1aa77e6a99d48ef29ecb5be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231530"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="22158-102">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="22158-103">Вы можете закрепление элементов управления по границам формы или заполнить ими контейнера элемента управления (форму или контейнерный элемент управления).</span><span class="sxs-lookup"><span data-stu-id="22158-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="22158-104">Например, Windows Explorer закрепляет его <xref:System.Windows.Forms.TreeView> элемента управления в левой части окна и его <xref:System.Windows.Forms.ListView> элемента управления в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="22158-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="22158-105">Используйте <xref:System.Windows.Forms.Control.Dock%2A> свойство для всех видимых элементов управления Windows Forms для определения режима закрепления.</span><span class="sxs-lookup"><span data-stu-id="22158-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22158-106">Элементы управления закрепляются в обратном z порядке.</span><span class="sxs-lookup"><span data-stu-id="22158-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="22158-107"><xref:System.Windows.Forms.Control.Dock%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="22158-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="22158-108">Дополнительные сведения см. в разделе [Общие](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="22158-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="22158-109">Чтобы закрепить элемент управления</span><span class="sxs-lookup"><span data-stu-id="22158-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="22158-110">Выберите элемент управления, который требуется закрепить.</span><span class="sxs-lookup"><span data-stu-id="22158-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="22158-111">В окне «Свойства» щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="22158-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="22158-112">Отображается редактор, показывающий набор полей, соответствующих краям и центру формы.</span><span class="sxs-lookup"><span data-stu-id="22158-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="22158-113">Нажмите кнопку, представляющий границы формы, в которой вы хотите закрепить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="22158-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="22158-114">Чтобы заполнить содержимое формы элемента управления или контейнерный элемент управления, щелкните поле center.</span><span class="sxs-lookup"><span data-stu-id="22158-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="22158-115">Нажмите кнопку **(нет)** для запрещения закрепления.</span><span class="sxs-lookup"><span data-stu-id="22158-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="22158-116">Элемент управления изменяется автоматически в соответствии с границами закрепленной позиции.</span><span class="sxs-lookup"><span data-stu-id="22158-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22158-117">Наследуемые элементы управления должны быть `Protected` могла быть закреплено.</span><span class="sxs-lookup"><span data-stu-id="22158-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="22158-118">Чтобы изменить уровень доступа для элемента управления, установите его **модификатор** свойства в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="22158-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22158-119">См. также</span><span class="sxs-lookup"><span data-stu-id="22158-119">See also</span></span>

- [<span data-ttu-id="22158-120">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="22158-121">Расположение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="22158-122">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="22158-123">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="22158-124">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="22158-125">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="22158-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="22158-126">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="22158-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="22158-127">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="22158-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="22158-128">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22158-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
