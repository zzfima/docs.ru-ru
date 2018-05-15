---
title: Разработка пользовательских элементов управления Windows Forms в .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 935358664f93b6428b9153a9bcbed862aeee07ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="a33d9-102">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a33d9-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="a33d9-103">Элементы управления Windows Forms — это многократно используемые компоненты, которые инкапсулируют функциональность пользовательского интерфейса и используются в клиентских приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="a33d9-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="a33d9-104">Windows Forms предоставляет не только множество готовых к использованию элементов управления, но и инфраструктуру для разработки собственных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a33d9-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="a33d9-105">Вы можете объединять существующие элементы управления, расширять существующие или создавать пользовательские элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a33d9-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="a33d9-106">В этом разделе приводятся дополнительные сведения и образцы, которые помогут вам в разработке элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a33d9-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a33d9-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a33d9-107">In This Section</span></span>  
 [<span data-ttu-id="a33d9-108">Общие сведения об использовании элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-108">Overview of Using Controls in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="a33d9-109">Освещены главные особенности использования элементов управления в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a33d9-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="a33d9-110">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="a33d9-110">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="a33d9-111">Описываются различные типы пользовательских элементов управления, которые можно создать с помощью пространства имен <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a33d9-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="a33d9-112">Основы разработки элементов управления форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-112">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 <span data-ttu-id="a33d9-113">Обсуждаются первые шаги в разработке элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a33d9-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="a33d9-114">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-114">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 <span data-ttu-id="a33d9-115">Показано, как добавлять свойства в элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a33d9-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="a33d9-116">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-116">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 <span data-ttu-id="a33d9-117">Показано, как обрабатывать и определять события в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a33d9-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="a33d9-118">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-118">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="a33d9-119">Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.</span><span class="sxs-lookup"><span data-stu-id="a33d9-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="a33d9-120">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="a33d9-120">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="a33d9-121">Показано, как настраивать внешний вид элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a33d9-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="a33d9-122">Размещение элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-122">Layout in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)  
 <span data-ttu-id="a33d9-123">Показано, как создавать сложные макеты для элементов управления и форм.</span><span class="sxs-lookup"><span data-stu-id="a33d9-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="a33d9-124">Многопоточность в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a33d9-124">Multithreading in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="a33d9-125">Показано, как реализовать многопоточные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a33d9-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a33d9-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a33d9-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="a33d9-127">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="a33d9-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="a33d9-128">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="a33d9-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a33d9-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a33d9-129">Related Sections</span></span>  
 [<span data-ttu-id="a33d9-130">Атрибуты времени разработки для компонентов</span><span class="sxs-lookup"><span data-stu-id="a33d9-130">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="a33d9-131">Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.</span><span class="sxs-lookup"><span data-stu-id="a33d9-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="a33d9-132">Расширения поддержки времени разработки</span><span class="sxs-lookup"><span data-stu-id="a33d9-132">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="a33d9-133">Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.</span><span class="sxs-lookup"><span data-stu-id="a33d9-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 [<span data-ttu-id="a33d9-134">Практическое руководство. Лицензирование компонентов и элементов управления</span><span class="sxs-lookup"><span data-stu-id="a33d9-134">How to: License Components and Controls</span></span>](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 <span data-ttu-id="a33d9-135">Описывается, как реализовать лицензирование в элементе управления или компоненте.</span><span class="sxs-lookup"><span data-stu-id="a33d9-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="a33d9-136">См. также [Создание элементов управления Windows Forms во время разработки](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="a33d9-136">Also see [Developing Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span></span>
