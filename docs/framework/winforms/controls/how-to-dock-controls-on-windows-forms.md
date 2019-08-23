---
title: Практическое руководство. Закрепление элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963629"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="0c051-102">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="0c051-103">Можно закреплять элементы управления на краях формы или заполнять их контейнером элемента управления (формой или контейнерным элементом управления).</span><span class="sxs-lookup"><span data-stu-id="0c051-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="0c051-104">Например, проводник закрепляет свой <xref:System.Windows.Forms.TreeView> элемент управления в левой части окна, а его <xref:System.Windows.Forms.ListView> элемент управления — в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="0c051-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="0c051-105"><xref:System.Windows.Forms.Control.Dock%2A> Используйте свойство для всех видимых Windows Forms элементов управления, чтобы определить режим закрепления.</span><span class="sxs-lookup"><span data-stu-id="0c051-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c051-106">Элементы управления закрепляются в обратном z-порядке.</span><span class="sxs-lookup"><span data-stu-id="0c051-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="0c051-107">Свойство взаимодействует со <xref:System.Windows.Forms.Control.AutoSize%2A>свойством. <xref:System.Windows.Forms.Control.Dock%2A></span><span class="sxs-lookup"><span data-stu-id="0c051-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="0c051-108">Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c051-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="0c051-109">Закрепление элемента управления</span><span class="sxs-lookup"><span data-stu-id="0c051-109">To dock a control</span></span>  
  
1. <span data-ttu-id="0c051-110">Выберите элемент управления, который требуется закрепить.</span><span class="sxs-lookup"><span data-stu-id="0c051-110">Select the control that you want to dock.</span></span>  
  
2. <span data-ttu-id="0c051-111">В окно свойств щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="0c051-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="0c051-112">Отобразится редактор, показывающий ряд прямоугольников, представляющих края и центр формы.</span><span class="sxs-lookup"><span data-stu-id="0c051-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3. <span data-ttu-id="0c051-113">Нажмите кнопку, представляющую границу формы, в которой необходимо закрепить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0c051-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="0c051-114">Чтобы заполнить содержимое формы элемента управления или элемента управления контейнера, щелкните центральную рамку.</span><span class="sxs-lookup"><span data-stu-id="0c051-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="0c051-115">Щелкните **(нет)** , чтобы отключить закрепление.</span><span class="sxs-lookup"><span data-stu-id="0c051-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="0c051-116">Размер элемента управления автоматически изменяется в соответствии с границами закрепленной границы.</span><span class="sxs-lookup"><span data-stu-id="0c051-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0c051-117">Наследуемые элементы `Protected` управления должны быть закрепленными.</span><span class="sxs-lookup"><span data-stu-id="0c051-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="0c051-118">Чтобы изменить уровень доступа элемента управления, установите его свойство **Modifiers** в окно свойств.</span><span class="sxs-lookup"><span data-stu-id="0c051-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c051-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0c051-119">See also</span></span>

- [<span data-ttu-id="0c051-120">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="0c051-121">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="0c051-122">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0c051-123">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0c051-124">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="0c051-125">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0c051-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="0c051-126">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0c051-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="0c051-127">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="0c051-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="0c051-128">Практическое руководство. Привязка элементов управления к Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c051-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
