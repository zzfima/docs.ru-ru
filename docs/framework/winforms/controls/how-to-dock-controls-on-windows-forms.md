---
title: Закрепление элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745519"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="cf5c7-102">Как закреплять элементы управления на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="cf5c7-103">Можно закреплять элементы управления на краях формы или заполнять их контейнером элемента управления (формой или контейнерным элементом управления).</span><span class="sxs-lookup"><span data-stu-id="cf5c7-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="cf5c7-104">Например, проводник закрепляет свой <xref:System.Windows.Forms.TreeView> элемент управления в левой части окна, а элемент управления <xref:System.Windows.Forms.ListView> — в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="cf5c7-105">Используйте свойство <xref:System.Windows.Forms.Control.Dock%2A> для всех видимых Windows Forms элементов управления, чтобы определить режим закрепления.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="cf5c7-106">Элементы управления закрепляются в обратном z-порядке.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="cf5c7-107">Свойство <xref:System.Windows.Forms.Control.Dock%2A> взаимодействует со свойством <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="cf5c7-108">Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cf5c7-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="cf5c7-109">Закрепление элемента управления</span><span class="sxs-lookup"><span data-stu-id="cf5c7-109">To dock a control</span></span>

1. <span data-ttu-id="cf5c7-110">В Visual Studio выберите элемент управления, который необходимо закрепить.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="cf5c7-111">В окне **Свойства** щелкните стрелку справа от свойства <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="cf5c7-112">Отобразится редактор, показывающий ряд прямоугольников, представляющих края и центр формы.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="cf5c7-113">Нажмите кнопку, представляющую границу формы, в которой необходимо закрепить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="cf5c7-114">Чтобы заполнить содержимое формы элемента управления или элемента управления контейнера, щелкните центральную рамку.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="cf5c7-115">Щелкните **(нет)** , чтобы отключить закрепление.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="cf5c7-116">Размер элемента управления автоматически изменяется в соответствии с границами закрепленной границы.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cf5c7-117">Наследуемые элементы управления должны быть `Protected`, чтобы их можно было закрепить.</span><span class="sxs-lookup"><span data-stu-id="cf5c7-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="cf5c7-118">Чтобы изменить уровень доступа элемента управления, установите его свойство **Modifiers** в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="cf5c7-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf5c7-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf5c7-119">See also</span></span>

- [<span data-ttu-id="cf5c7-120">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="cf5c7-121">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="cf5c7-122">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="cf5c7-123">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="cf5c7-124">Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf5c7-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="cf5c7-125">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf5c7-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="cf5c7-126">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="cf5c7-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="cf5c7-127">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf5c7-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
