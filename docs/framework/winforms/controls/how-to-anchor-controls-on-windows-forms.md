---
title: Привязка элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747185"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="4cbf8-102">Как привязать элементы управления к Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cbf8-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="4cbf8-103">Если вы разрабатываете форму, размер которой может изменить пользователь во время выполнения, элементы управления в форме должны изменить его размер и правильно изменить расположение.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="4cbf8-104">Для динамического изменения размера элементов управления с помощью формы можно использовать свойство <xref:System.Windows.Forms.Control.Anchor%2A> элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="4cbf8-105">Свойство <xref:System.Windows.Forms.Control.Anchor%2A> определяет точку привязки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="4cbf8-106">Когда элемент управления привязан к форме и изменяется размер формы, элемент управления сохраняет расстояние между элементом управления и положением привязки.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="4cbf8-107">Например, если имеется элемент управления <xref:System.Windows.Forms.TextBox>, привязанный к левому, правому и нижнему краю формы при изменении размера формы, элемент управления <xref:System.Windows.Forms.TextBox> изменяет размер по горизонтали таким образом, чтобы он удерживает то же расстояние от правой и левой сторон формы.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="4cbf8-108">Кроме того, элемент управления располагается по вертикали, чтобы его положение всегда совпадало с нижним ребром формы.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="4cbf8-109">Если элемент управления не привязан и размеры формы изменяются, изменяется расположение элемента управления относительно границ формы.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="4cbf8-110">Свойство <xref:System.Windows.Forms.Control.Anchor%2A> взаимодействует со свойством <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="4cbf8-111">Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4cbf8-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="4cbf8-112">Привязка элемента управления к форме</span><span class="sxs-lookup"><span data-stu-id="4cbf8-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="4cbf8-113">В Visual Studio выберите элемент управления, который необходимо привязать.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4cbf8-114">Можно закрепить несколько элементов управления одновременно, нажав клавишу CTRL, щелкнув каждый из них, а затем выполнив оставшуюся часть этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="4cbf8-115">В окне **Свойства** щелкните стрелку справа от свойства <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="4cbf8-116">Откроется редактор, в котором отображается крестик.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="4cbf8-117">Чтобы задать привязку, щелкните верхнюю, левую, правую или нижнюю часть крестика.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="4cbf8-118">По умолчанию элементы управления привязаны к верхнему и левому краю.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="4cbf8-119">Чтобы очистить сторону привязанного элемента управления, щелкните точку пересечения.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="4cbf8-120">Чтобы закрыть редактор свойств <xref:System.Windows.Forms.Control.Anchor%2A>, снова щелкните имя свойства <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="4cbf8-121">Когда форма отображается во время выполнения, размер элемента управления изменяется так, чтобы оставаться расположенными на том же расстоянии от края формы.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="4cbf8-122">Расстояние от привязанного периметра всегда остается таким же, как и расстояние, определенное при размещении элемента управления в конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="4cbf8-123">Некоторые элементы управления, такие как элемент управления <xref:System.Windows.Forms.ComboBox>, имеют ограничения по высоте.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="4cbf8-124">Привязка элемента управления к нижней части его формы или контейнера не может привести к превышению предельной высоты элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="4cbf8-125">Наследуемые элементы управления должны быть `Protected` для привязки.</span><span class="sxs-lookup"><span data-stu-id="4cbf8-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="4cbf8-126">Чтобы изменить уровень доступа элемента управления, задайте его свойство `Modifiers` в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="4cbf8-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cbf8-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cbf8-127">See also</span></span>

- [<span data-ttu-id="4cbf8-128">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cbf8-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="4cbf8-129">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="4cbf8-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="4cbf8-130">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cbf8-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="4cbf8-131">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4cbf8-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="4cbf8-132">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4cbf8-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="4cbf8-133">Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize</span><span class="sxs-lookup"><span data-stu-id="4cbf8-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
