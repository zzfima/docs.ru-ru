---
title: Свойства элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 82bfab15cef4946661a37d2d88fbe1b797f3d816
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741178"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="de107-102">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de107-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="de107-103">Windows Forms элемент управления наследует многие свойства, образуя базовый класс <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de107-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de107-104">К ним относятся такие свойства, как <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>и многие другие.</span><span class="sxs-lookup"><span data-stu-id="de107-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="de107-105">Дополнительные сведения о наследованных свойствах см. в разделе <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de107-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="de107-106">Вы можете переопределять наследуемые свойства в элементе управления, а также задавать новые свойства.</span><span class="sxs-lookup"><span data-stu-id="de107-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de107-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="de107-107">In This Section</span></span>  
 [<span data-ttu-id="de107-108">Определение свойства</span><span class="sxs-lookup"><span data-stu-id="de107-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="de107-109">Показывает, как реализовать свойство настраиваемого элемента управления или компонента и интегрировать свойство в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="de107-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="de107-110">Определение значений по умолчанию с помощью методов ShouldSerialize и Reset</span><span class="sxs-lookup"><span data-stu-id="de107-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="de107-111">Показывает, как определить значения свойства по умолчанию для настраиваемого элемента управления или компонента.</span><span class="sxs-lookup"><span data-stu-id="de107-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="de107-112">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="de107-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="de107-113">Показывает, как включить уведомления об изменении свойств при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="de107-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="de107-114">Практическое руководство. Обеспечение доступа к свойствам составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="de107-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="de107-115">Показывает, как предоставить доступ к свойствам составных элементов управления в настраиваемом составном элементе управления.</span><span class="sxs-lookup"><span data-stu-id="de107-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="de107-116">Реализация методов в специализированных элементах управления</span><span class="sxs-lookup"><span data-stu-id="de107-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="de107-117">Показывает, как реализовывать методы в настраиваемых элементах управления и компонентах.</span><span class="sxs-lookup"><span data-stu-id="de107-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="de107-118">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="de107-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="de107-119">Описание базового класса для реализации составных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="de107-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="de107-120">Документирует атрибут, указывающий <xref:System.ComponentModel.TypeConverter>, используемый для пользовательского типа свойства.</span><span class="sxs-lookup"><span data-stu-id="de107-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="de107-121">Документирует атрибут, указывающий <xref:System.Drawing.Design.UITypeEditor>, используемый для пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="de107-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de107-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="de107-122">Related Sections</span></span>  
 [<span data-ttu-id="de107-123">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de107-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="de107-124">Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.</span><span class="sxs-lookup"><span data-stu-id="de107-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="de107-125">[Атрибуты времени разработки для компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="de107-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="de107-126">Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.</span><span class="sxs-lookup"><span data-stu-id="de107-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="de107-127">[Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="de107-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="de107-128">Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.</span><span class="sxs-lookup"><span data-stu-id="de107-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
