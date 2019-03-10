---
title: Размещение элементов управления в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: d1a3954c8eda87bdda9fa17df1bd2b3858c43619
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711334"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="ac5c0-102">Размещение элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ac5c0-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="ac5c0-103">Точное расположение элементов управления на форме является важным для многих приложений.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="ac5c0-104"><xref:System.Windows.Forms?displayProperty=nameWithType> Пространство имен предоставляет множество средств форматирования для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ac5c0-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ac5c0-105">In This Section</span></span>

<span data-ttu-id="ac5c0-106">[Свойство AutoSize](autosize-property-overview.md)\\</span><span class="sxs-lookup"><span data-stu-id="ac5c0-106">[AutoSize Property Overview](autosize-property-overview.md)\\</span></span>
<span data-ttu-id="ac5c0-107">Описывает <xref:System.Windows.Forms.Control.AutoSize%2A> свойство и его роль в макете.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="ac5c0-108">[Поля и заполнение элементов управления в формах Windows Forms](margin-and-padding-in-windows-forms-controls.md)\\</span><span class="sxs-lookup"><span data-stu-id="ac5c0-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)\\</span></span>
<span data-ttu-id="ac5c0-109">Описывает <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> свойства и их роли в макете.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="ac5c0-110">[Практическое руководство. Выравнивание элементов управления по границам формы](how-to-align-a-control-to-the-edges-of-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ac5c0-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)\\</span></span>
<span data-ttu-id="ac5c0-111">Демонстрирует использование <xref:System.Windows.Forms.Control.Dock%2A> свойства выравнивания элемента управления по краю занимаемой им формы.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="ac5c0-112">[Практическое руководство. Создание рамки вокруг форм Windows элемента управления](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span><span class="sxs-lookup"><span data-stu-id="ac5c0-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span></span>
<span data-ttu-id="ac5c0-113">Демонстрирует использование <xref:System.Windows.Forms.Control.Padding%2A> свойств для структуры элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="ac5c0-114">[Практическое руководство. Реализация пользовательского механизма размещения](how-to-implement-a-custom-layout-engine.md)\\</span><span class="sxs-lookup"><span data-stu-id="ac5c0-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)\\</span></span>
<span data-ttu-id="ac5c0-115">Демонстрируется способ реализации <xref:System.Windows.Forms.Layout.LayoutEngine> для упорядочения элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="ac5c0-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="ac5c0-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="ac5c0-117">Справочная документация по элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="ac5c0-118">Справочная документация по элементу управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ac5c0-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac5c0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ac5c0-119">See also</span></span>

- [<span data-ttu-id="ac5c0-120">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ac5c0-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="ac5c0-121">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ac5c0-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ac5c0-122">Практическое руководство. Разработка макета формы Windows, с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="ac5c0-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="ac5c0-123">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ac5c0-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
