---
title: Практическое руководство. Привязка элементов управления в формах Windows Forms
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94fa6fe90e5583a3bfecf376af59d53f6d8528af
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987501"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="ff2a6-102">Практическое руководство. Привязка элементов управления к Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff2a6-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="ff2a6-103">Если вы разрабатываете форму, размер которой может изменить пользователь во время выполнения, элементы управления в форме должны изменить его размер и правильно изменить расположение.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="ff2a6-104">Для динамического изменения размера элементов управления с помощью формы можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> свойство элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="ff2a6-105"><xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет точку привязки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="ff2a6-106">Когда элемент управления привязан к форме и изменяется размер формы, элемент управления сохраняет расстояние между элементом управления и положением привязки.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="ff2a6-107">Например, если имеется <xref:System.Windows.Forms.TextBox> элемент управления, привязанный к левому, правому и нижнему краю формы при изменении размера формы, то <xref:System.Windows.Forms.TextBox> элемент управления изменяет свой размер по горизонтали таким образом, чтобы он удерживает то же расстояние от правой и левой сторон формы.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="ff2a6-108">Кроме того, элемент управления располагается по вертикали, чтобы его положение всегда совпадало с нижним ребром формы.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="ff2a6-109">Если элемент управления не привязан и размеры формы изменяются, изменяется расположение элемента управления относительно границ формы.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="ff2a6-110">Свойство взаимодействует со <xref:System.Windows.Forms.Control.AutoSize%2A>свойством. <xref:System.Windows.Forms.Control.Anchor%2A></span><span class="sxs-lookup"><span data-stu-id="ff2a6-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="ff2a6-111">Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff2a6-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="ff2a6-112">Привязка элемента управления к форме</span><span class="sxs-lookup"><span data-stu-id="ff2a6-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="ff2a6-113">В Visual Studio выберите элемент управления, который необходимо привязать.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff2a6-114">Можно закрепить несколько элементов управления одновременно, нажав клавишу CTRL, щелкнув каждый из них, а затем выполнив оставшуюся часть этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="ff2a6-115">В окне **Свойства** щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="ff2a6-116">Откроется редактор, в котором отображается крестик.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="ff2a6-117">Чтобы задать привязку, щелкните верхнюю, левую, правую или нижнюю часть крестика.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="ff2a6-118">По умолчанию элементы управления привязаны к верхнему и левому краю.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="ff2a6-119">Чтобы очистить сторону привязанного элемента управления, щелкните точку пересечения.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="ff2a6-120">Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> редактор свойств, еще раз <xref:System.Windows.Forms.Control.Anchor%2A> щелкните имя свойства.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="ff2a6-121">Когда форма отображается во время выполнения, размер элемента управления изменяется так, чтобы оставаться расположенными на том же расстоянии от края формы.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="ff2a6-122">Расстояние от привязанного периметра всегда остается таким же, как и расстояние, определенное при размещении элемента управления в конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="ff2a6-123">Некоторые элементы управления, такие как <xref:System.Windows.Forms.ComboBox> элемент управления, имеют ограничение по высоте.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="ff2a6-124">Привязка элемента управления к нижней части его формы или контейнера не может привести к превышению предельной высоты элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="ff2a6-125">Наследуемые элементы `Protected` управления должны быть доступны для привязки.</span><span class="sxs-lookup"><span data-stu-id="ff2a6-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="ff2a6-126">Чтобы изменить уровень доступа элемента управления, задайте его `Modifiers` свойство в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="ff2a6-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff2a6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ff2a6-127">See also</span></span>

- [<span data-ttu-id="ff2a6-128">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff2a6-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="ff2a6-129">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="ff2a6-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="ff2a6-130">Практическое руководство. Закреплять элементы управления на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff2a6-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="ff2a6-131">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ff2a6-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="ff2a6-132">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ff2a6-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="ff2a6-133">Пошаговое руководство: Разметка элементов управления Windows Forms с заполнением, полями и свойством AutoSize</span><span class="sxs-lookup"><span data-stu-id="ff2a6-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
