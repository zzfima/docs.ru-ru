---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 8dcf79d449a8f8443774b133904e819dfd925288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526608"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="6ce50-102">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="6ce50-102">Using WPF Controls</span></span>
<span data-ttu-id="6ce50-103">Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ce50-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="6ce50-104">Хотя эти две различные технологии, они взаимодействуют.</span><span class="sxs-lookup"><span data-stu-id="6ce50-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="6ce50-105">Конструктор Windows Forms предоставляет визуальную среду проектирования для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="6ce50-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="6ce50-106">Элемент управления WPF размещается специальных элементов управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="6ce50-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="6ce50-107">Этот элемент управления позволяет участвовать в макет формы и получать сообщения клавиатуры и мыши элемента управления WPF.</span><span class="sxs-lookup"><span data-stu-id="6ce50-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="6ce50-108">Во время разработки, вы можете упорядочить <xref:System.Windows.Forms.Integration.ElementHost> управления так же, как и любой элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ce50-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="6ce50-109">Можно также использовать элементы управления Windows Forms в приложениях WPF.</span><span class="sxs-lookup"><span data-stu-id="6ce50-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="6ce50-110">Дополнительные сведения см. в разделе [конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span><span class="sxs-lookup"><span data-stu-id="6ce50-110">For more information, see [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ce50-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6ce50-111">In This Section</span></span>  
 [<span data-ttu-id="6ce50-112">Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ce50-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="6ce50-113">Показано, как скопировать элемент управления Windows Presentation Foundation в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ce50-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="6ce50-114">Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ce50-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="6ce50-115">Показано, как использовать функции структуры Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="6ce50-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="6ce50-116">Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ce50-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="6ce50-117">Показан рабочий процесс между конструктор Windows Forms и [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] по изменению свойств для элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="6ce50-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="6ce50-118">Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ce50-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="6ce50-119">Показано, как создать элемент управления Windows Presentation Foundation для использования в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ce50-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="6ce50-120">Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ce50-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="6ce50-121">Показано, как скопировать элемент управления Windows Presentation Foundation из одной формы Windows Forms в другую.</span><span class="sxs-lookup"><span data-stu-id="6ce50-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="6ce50-122">Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ce50-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="6ce50-123">Показано, как выбрать типы элементов управления Windows Presentation Foundation, который будет отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="6ce50-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="6ce50-124">Пошаговое руководство. Применение стилей к содержимому WPF</span><span class="sxs-lookup"><span data-stu-id="6ce50-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="6ce50-125">Показан рабочий процесс между конструктор Windows Forms и [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] применения стилей к элементам управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="6ce50-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6ce50-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6ce50-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="6ce50-127">Описывает класс, который можно использовать в приложениях Windows Forms для размещения элементов управления Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="6ce50-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="6ce50-128">Описывает класс, который можно использовать для размещения элементов управления Windows Forms в приложении Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="6ce50-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ce50-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6ce50-129">Related Sections</span></span>  
 [<span data-ttu-id="6ce50-130">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="6ce50-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="6ce50-131">Описывает взаимодействие между технологиями Windows Presentation Foundation и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ce50-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="6ce50-132">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="6ce50-132">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="6ce50-133">Инструкции по разработке элементов управления Windows Presentation Foundation в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ce50-133">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
