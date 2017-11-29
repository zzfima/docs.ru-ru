---
title: "Практическое руководство. Привязка элементов управления в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c6f7cc527c7409ffecab2ac67386d0f819cce3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="c9d9c-102">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9d9c-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="c9d9c-103">При разработке формы, пользователь может сделать во время выполнения, элементы управления формы следует изменять размер и положение должным образом.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="c9d9c-104">Чтобы изменить размер элементов управления, динамически с формой, можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> свойства элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="c9d9c-105"><xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет положение прикрепления для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="c9d9c-106">Если элемент управления привязан к форме и изменении размера формы, элемент управления поддерживает расстояние между элементом управления и положениями прикрепления.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="c9d9c-107">Например, если у вас есть <xref:System.Windows.Forms.TextBox> управления, привязанный к левое, правое и нижней границ формы как формы изменяется, <xref:System.Windows.Forms.TextBox> элемент управления по горизонтали таким образом, чтобы сохранить одинаковое расстояние до правой и левой сторон формы.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="c9d9c-108">Кроме того элемент управления размещает сам по вертикали, чтобы ее расположение всегда такое же расстояние от нижнего края формы.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="c9d9c-109">Если элемент управления не привязан и изменении размера формы, изменяется положение элемента управления относительно края формы.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="c9d9c-110"><xref:System.Windows.Forms.Control.Anchor%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="c9d9c-111">Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c9d9c-111">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9d9c-112">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c9d9c-113">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c9d9c-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c9d9c-114">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c9d9c-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="c9d9c-115">Чтобы привязать элемент управления на форме</span><span class="sxs-lookup"><span data-stu-id="c9d9c-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="c9d9c-116">Выберите элемент управления, который нужно закрепить.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c9d9c-117">Можно прикрепить несколько элементов одновременно, при нажатой клавише CTRL, щелкните каждый элемент управления, чтобы выбрать его и выполнив оставшуюся часть этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="c9d9c-118">В **свойства** окно, щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="c9d9c-119">Откроется редактор покажет крестик.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="c9d9c-120">Чтобы задать элемент привязки, щелкните сверху, слева, справа или нижнюю часть крестика.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="c9d9c-121">Элементы управления привязаны к верхней и оставить по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="c9d9c-122">Чтобы очистить стороны элемента управления, была привязана, щелкните соответствующую часть крестика.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="c9d9c-123">Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> редактор свойств, нажмите кнопку <xref:System.Windows.Forms.Control.Anchor%2A> снова имя свойства.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="c9d9c-124">При отображении формы во время выполнения элемент управления меняет размер, оставаясь на одинаковом расстоянии от края формы.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="c9d9c-125">Расстояние от прикрепленного края всегда остается равным расстоянию, определенному при расположении элемента управления в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9d9c-126">Некоторые элементы управления, такие как <xref:System.Windows.Forms.ComboBox> контроля, ограничен по высоте.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="c9d9c-127">Прикреплением элемента управления в нижней части формы или контейнера нельзя к превышению ограничения высоты.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="c9d9c-128">Наследуемые элементы управления должны быть `Protected` могли быть прикреплены.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="c9d9c-129">Чтобы изменить уровень доступа элемента управления, установите его `Modifiers` свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="c9d9c-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d9c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c9d9c-130">See Also</span></span>  
 [<span data-ttu-id="c9d9c-131">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9d9c-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="c9d9c-132">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9d9c-132">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="c9d9c-133">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="c9d9c-133">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="c9d9c-134">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9d9c-134">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="c9d9c-135">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c9d9c-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="c9d9c-136">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c9d9c-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="c9d9c-137">Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize</span><span class="sxs-lookup"><span data-stu-id="c9d9c-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
