---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 30b84f05898f823227415c410dc7ba5f89d58664
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504709"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="816a7-102">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="816a7-102">Using WPF Controls</span></span>
<span data-ttu-id="816a7-103">Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="816a7-104">Несмотря на то, что они являются две различные технологии, они взаимодействуют.</span><span class="sxs-lookup"><span data-stu-id="816a7-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="816a7-105">В конструкторе Windows Forms предоставляет среду визуальной разработки для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="816a7-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="816a7-106">Элемент управления WPF размещается в специальный элемент управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="816a7-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="816a7-107">Этот элемент управления включает элемент управления WPF в участвуют в макете формы и получать сообщения клавиатуры и мыши.</span><span class="sxs-lookup"><span data-stu-id="816a7-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="816a7-108">Во время разработки, можно упорядочить <xref:System.Windows.Forms.Integration.ElementHost> управления так же, как и любой элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="816a7-109">Можно также использовать элементы управления Windows Forms в WPF-приложениях.</span><span class="sxs-lookup"><span data-stu-id="816a7-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="816a7-110">Дополнительные сведения см. в разделе [конструктора XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="816a7-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="816a7-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="816a7-111">In This Section</span></span>  
 [<span data-ttu-id="816a7-112">Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки</span><span class="sxs-lookup"><span data-stu-id="816a7-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="816a7-113">Показано, как скопировать элемент управления Windows Presentation Foundation в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="816a7-114">Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="816a7-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="816a7-115">Показано, как использовать возможности макета Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="816a7-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="816a7-116">Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки</span><span class="sxs-lookup"><span data-stu-id="816a7-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="816a7-117">Показывает рабочий процесс между в конструкторе Windows Forms и [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] по изменению свойств для элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="816a7-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="816a7-118">Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="816a7-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="816a7-119">В этой статье демонстрируется создание элемента управления Windows Presentation Foundation для использования в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="816a7-120">Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="816a7-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="816a7-121">Показано, как скопировать элемент управления Windows Presentation Foundation из одной формы Windows в другую.</span><span class="sxs-lookup"><span data-stu-id="816a7-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="816a7-122">Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="816a7-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="816a7-123">Показано, как выбрать типы элементов управления Windows Presentation Foundation, который будет отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="816a7-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="816a7-124">Пошаговое руководство. Применение стилей к содержимому WPF</span><span class="sxs-lookup"><span data-stu-id="816a7-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="816a7-125">Показывает рабочий процесс между в конструкторе Windows Forms и [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] применения стилей к элементам управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="816a7-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="816a7-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="816a7-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="816a7-127">Описывает класс, который можно использовать для размещения элементов управления Windows Presentation Foundation в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="816a7-128">Описывает класс, который можно использовать для размещения элементов управления Windows Forms в приложении Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="816a7-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="816a7-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="816a7-129">Related Sections</span></span>  
 [<span data-ttu-id="816a7-130">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="816a7-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="816a7-131">Содержит описание взаимодействия между технологиями Windows Presentation Foundation и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="816a7-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="816a7-132">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="816a7-132">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 <span data-ttu-id="816a7-133">Инструкции по разработке элементов управления Windows Presentation Foundation в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="816a7-133">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
