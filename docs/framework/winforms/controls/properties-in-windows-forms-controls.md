---
title: Свойства элементов управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: b1f7e0f5c1c9a01e47d0d972c56db8da922d2d0b
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664579"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="3085e-102">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3085e-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="3085e-103">Элемент управления Windows Forms наследует многие свойства базового класса <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3085e-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3085e-104">К ним относятся свойства, такие как <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>и многие другие.</span><span class="sxs-lookup"><span data-stu-id="3085e-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="3085e-105">Дополнительные сведения о наследуемых свойствах см. в разделе <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3085e-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3085e-106">Вы можете переопределять наследуемые свойства в элементе управления, а также задавать новые свойства.</span><span class="sxs-lookup"><span data-stu-id="3085e-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3085e-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3085e-107">In This Section</span></span>  
 [<span data-ttu-id="3085e-108">Определение свойства</span><span class="sxs-lookup"><span data-stu-id="3085e-108">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="3085e-109">Показывает, как реализовать свойство настраиваемого элемента управления или компонента и интегрировать свойство в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="3085e-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="3085e-110">Определение значений по умолчанию с помощью методов ShouldSerialize и Reset</span><span class="sxs-lookup"><span data-stu-id="3085e-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="3085e-111">Показывает, как определить значения свойства по умолчанию для настраиваемого элемента управления или компонента.</span><span class="sxs-lookup"><span data-stu-id="3085e-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="3085e-112">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="3085e-112">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 <span data-ttu-id="3085e-113">Показывает, как включить уведомления об изменении свойств при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="3085e-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="3085e-114">Практическое руководство. Обеспечение доступа к свойствам составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="3085e-114">How to: Expose Properties of Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="3085e-115">Показывает, как предоставить доступ к свойствам составных элементов управления в настраиваемом составном элементе управления.</span><span class="sxs-lookup"><span data-stu-id="3085e-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="3085e-116">Реализация методов в специализированных элементах управления</span><span class="sxs-lookup"><span data-stu-id="3085e-116">Method Implementation in Custom Controls</span></span>](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 <span data-ttu-id="3085e-117">Показывает, как реализовывать методы в настраиваемых элементах управления и компонентах.</span><span class="sxs-lookup"><span data-stu-id="3085e-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3085e-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="3085e-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="3085e-119">Описание базового класса для реализации составных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="3085e-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="3085e-120">Описывает атрибут, задающий <xref:System.ComponentModel.TypeConverter> для типа настраиваемого свойства.</span><span class="sxs-lookup"><span data-stu-id="3085e-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="3085e-121">Описывает атрибут, задающий <xref:System.Drawing.Design.UITypeEditor> для пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="3085e-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3085e-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3085e-122">Related Sections</span></span>  
 [<span data-ttu-id="3085e-123">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3085e-123">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="3085e-124">Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.</span><span class="sxs-lookup"><span data-stu-id="3085e-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="3085e-125">[Атрибуты времени разработки для компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3085e-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="3085e-126">Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.</span><span class="sxs-lookup"><span data-stu-id="3085e-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="3085e-127">[Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3085e-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="3085e-128">Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.</span><span class="sxs-lookup"><span data-stu-id="3085e-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
