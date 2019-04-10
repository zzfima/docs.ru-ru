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
ms.openlocfilehash: b5550aef220ece09d5486421275b19a37bfe9011
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329782"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="f00e6-102">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f00e6-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="f00e6-103">При разработке формы, в которой пользователь может сделать во время выполнения, элементы управления в форме следует изменить размер и местоположение.</span><span class="sxs-lookup"><span data-stu-id="f00e6-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="f00e6-104">Чтобы изменить размер элементов управления, динамически с формой, можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f00e6-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="f00e6-105"><xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет положение прикрепления для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f00e6-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="f00e6-106">Когда элемент управления привязан к форме и изменении размера формы, элемент управления поддерживает расстояние между элементом управления и положениями прикрепления.</span><span class="sxs-lookup"><span data-stu-id="f00e6-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="f00e6-107">Например, если у вас есть <xref:System.Windows.Forms.TextBox> элемент управления, привязанный к левой, правой и верхней границе формы, при изменении размера формы, <xref:System.Windows.Forms.TextBox> изменении размера элемента управления по горизонтали таким образом, чтобы сохранить такое же расстояние от правой и левой сторон формы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="f00e6-108">Кроме того элемент управления размещается по вертикали, чтобы она будет находиться всегда такое же расстояние от нижнего края формы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="f00e6-109">Если элемент управления не привязан и изменении размера формы, изменяется положение элемента управления относительно соответствующих краев формы.</span><span class="sxs-lookup"><span data-stu-id="f00e6-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="f00e6-110"><xref:System.Windows.Forms.Control.Anchor%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f00e6-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="f00e6-111">Дополнительные сведения см. в разделе [Общие](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f00e6-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f00e6-112">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="f00e6-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f00e6-113">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="f00e6-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f00e6-114">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f00e6-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="f00e6-115">Для привязки элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="f00e6-115">To anchor a control on a form</span></span>  
  
1. <span data-ttu-id="f00e6-116">Выберите элемент управления, который нужно закрепить.</span><span class="sxs-lookup"><span data-stu-id="f00e6-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f00e6-117">Можно прикрепить несколько элементов одновременно, удерживая нажатой клавишу CTRL, щелкнув каждый элемент управления, чтобы выбрать его и следуйте оставшуюся часть этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f00e6-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2. <span data-ttu-id="f00e6-118">В **свойства** окно, щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f00e6-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="f00e6-119">Отображается редактор, показывающий крест.</span><span class="sxs-lookup"><span data-stu-id="f00e6-119">An editor is displayed that shows a cross.</span></span>  
  
3. <span data-ttu-id="f00e6-120">Чтобы задать привязки, щелкните сверху, слева, справа или нижней части крестика.</span><span class="sxs-lookup"><span data-stu-id="f00e6-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="f00e6-121">Элементы управления, привязанный к верхней и левой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f00e6-121">Controls are anchored to the top and left by default.</span></span>  
  
4. <span data-ttu-id="f00e6-122">Чтобы очистить стороны элемента управления, который был прикреплен, щелкните соответствующую часть крестика.</span><span class="sxs-lookup"><span data-stu-id="f00e6-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5. <span data-ttu-id="f00e6-123">Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> щелкните редактор свойств <xref:System.Windows.Forms.Control.Anchor%2A> снова имя свойства.</span><span class="sxs-lookup"><span data-stu-id="f00e6-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="f00e6-124">При отображении формы во время выполнения, оставаясь на одинаковом расстоянии от края формы размера элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f00e6-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="f00e6-125">Расстояние от прикрепленного края всегда остается как расстояние определено, если элемент управления находится в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f00e6-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f00e6-126">Определенные элементы управления, такие как <xref:System.Windows.Forms.ComboBox> управления, ограничение для их высоту.</span><span class="sxs-lookup"><span data-stu-id="f00e6-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="f00e6-127">Привязка элемента управления в нижней части формы или контейнера не может принудительно требовать элементе управления превышает предельное значение высоты.</span><span class="sxs-lookup"><span data-stu-id="f00e6-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="f00e6-128">Наследуемые элементы управления должны быть `Protected` могла быть прикреплены.</span><span class="sxs-lookup"><span data-stu-id="f00e6-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="f00e6-129">Чтобы изменить уровень доступа для элемента управления, установите его `Modifiers` свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="f00e6-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00e6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f00e6-130">See also</span></span>

- [<span data-ttu-id="f00e6-131">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f00e6-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f00e6-132">Расположение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f00e6-132">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="f00e6-133">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="f00e6-133">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="f00e6-134">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f00e6-134">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="f00e6-135">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f00e6-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="f00e6-136">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f00e6-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="f00e6-137">Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize</span><span class="sxs-lookup"><span data-stu-id="f00e6-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
