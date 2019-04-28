---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 24b88e456628c5a0bdc3cded60b0e52a92057851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747619"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="2c3c6-102">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="2c3c6-102">Using WPF Controls</span></span>
<span data-ttu-id="2c3c6-103">Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="2c3c6-104">Несмотря на то, что они являются две различные технологии, они взаимодействуют.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="2c3c6-105">В конструкторе Windows Forms предоставляет среду визуальной разработки для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="2c3c6-106">Элемент управления WPF размещается в специальный элемент управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="2c3c6-107">Этот элемент управления включает элемент управления WPF в участвуют в макете формы и получать сообщения клавиатуры и мыши.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="2c3c6-108">Во время разработки, можно упорядочить <xref:System.Windows.Forms.Integration.ElementHost> управления так же, как и любой элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="2c3c6-109">Можно также использовать элементы управления Windows Forms в WPF-приложениях.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="2c3c6-110">Дополнительные сведения см. в разделе [конструктора XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="2c3c6-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c3c6-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2c3c6-111">In This Section</span></span>  
 [<span data-ttu-id="2c3c6-112">Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки</span><span class="sxs-lookup"><span data-stu-id="2c3c6-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="2c3c6-113">Показано, как скопировать элемент управления Windows Presentation Foundation в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="2c3c6-114">Пошаговое руководство: Упорядочение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2c3c6-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="2c3c6-115">Показано, как использовать возможности макета Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>
  
 [<span data-ttu-id="2c3c6-116">Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2c3c6-116">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="2c3c6-117">В этой статье демонстрируется создание элемента управления Windows Presentation Foundation для использования в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>
  
 [<span data-ttu-id="2c3c6-118">Пошаговое руководство: Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2c3c6-118">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="2c3c6-119">Показано, как выбрать типы элементов управления Windows Presentation Foundation, который будет отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="2c3c6-120">Пошаговое руководство: Применение стилей к содержимому WPF</span><span class="sxs-lookup"><span data-stu-id="2c3c6-120">Walkthrough: Styling WPF Content</span></span>](walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="2c3c6-121">Показывает рабочий процесс между в конструкторе Windows Forms и [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] применения стилей к элементам управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2c3c6-122">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2c3c6-122">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="2c3c6-123">Описывает класс, который можно использовать для размещения элементов управления Windows Presentation Foundation в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="2c3c6-124">Описывает класс, который можно использовать для размещения элементов управления Windows Forms в приложении Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2c3c6-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2c3c6-125">Related Sections</span></span>  
 [<span data-ttu-id="2c3c6-126">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="2c3c6-126">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="2c3c6-127">Содержит описание взаимодействия между технологиями Windows Presentation Foundation и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="2c3c6-128">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2c3c6-128">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 <span data-ttu-id="2c3c6-129">Инструкции по разработке элементов управления Windows Presentation Foundation в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
