---
title: Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210372"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="ce2a3-102">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="ce2a3-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="ce2a3-103">Чтобы выровнять по границе формы, задав значение элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="ce2a3-104">Это свойство определяет, в каком месте формы будет размещаться элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="ce2a3-105">Свойство <xref:System.Windows.Forms.Control.Dock%2A> может принимать указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="ce2a3-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="ce2a3-106">Setting</span></span>|<span data-ttu-id="ce2a3-107">Влияние на элемент управления</span><span class="sxs-lookup"><span data-stu-id="ce2a3-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="ce2a3-108">Фиксирует элемент управления у нижнего края формы.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="ce2a3-109">Заполняет все свободное пространство формы.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="ce2a3-110">Фиксирует элемент управления у левого края формы.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="ce2a3-111">Не фиксирует элемент нигде; он отображается в расположении, указанном путем его <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="ce2a3-112">Фиксирует элемент управления у правого края формы.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="ce2a3-113">Фиксирует элемент управления у верхнего края формы.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="ce2a3-114">Эти значения можно также задать в коде.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-114">These values can also be set in code.</span></span> <span data-ttu-id="ce2a3-115">Дополнительные сведения см. в разделе [Как Выравнивание элементов управления по границам формы](how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ce2a3-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="ce2a3-116">Задание свойства Dock для элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="ce2a3-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="ce2a3-117">В конструкторе Windows Forms в Visual Studio выберите элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="ce2a3-118">В **свойства** окно, щелкните в раскрывающемся поле рядом с <xref:System.Windows.Forms.Control.Dock%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="ce2a3-119">Графический интерфейс с шестью возможными <xref:System.Windows.Forms.Control.Dock%2A> параметров отображается.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="ce2a3-120">Выберите соответствующий параметр.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="ce2a3-121">Элемент управления будет зафиксировано в отношении, определенном с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="ce2a3-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce2a3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ce2a3-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ce2a3-123">Практическое руководство. Выравнивание элементов управления по границам формы</span><span class="sxs-lookup"><span data-stu-id="ce2a3-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="ce2a3-124">Пошаговое руководство: Упорядочение элементов управления в формах Windows Forms, с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="ce2a3-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="ce2a3-125">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce2a3-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="ce2a3-126">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ce2a3-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ce2a3-127">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ce2a3-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="ce2a3-128">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ce2a3-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="ce2a3-129">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ce2a3-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="ce2a3-130">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="ce2a3-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
