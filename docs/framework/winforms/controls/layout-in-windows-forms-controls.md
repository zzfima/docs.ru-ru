---
title: Макет элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: ed8603e997e7d0c1ed7a2ebda6dc960726d32f45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745247"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="bb192-102">Размещение элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb192-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="bb192-103">Точное расположение элементов управления на форме является важным для многих приложений.</span><span class="sxs-lookup"><span data-stu-id="bb192-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="bb192-104">Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> предоставляет множество инструментов макета для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="bb192-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bb192-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bb192-105">In This Section</span></span>

<span data-ttu-id="bb192-106">[Общие сведения о свойстве AutoSize](autosize-property-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bb192-106">[AutoSize Property Overview](autosize-property-overview.md)</span></span>\
<span data-ttu-id="bb192-107">Описывает свойство <xref:System.Windows.Forms.Control.AutoSize%2A> и его роль в макете.</span><span class="sxs-lookup"><span data-stu-id="bb192-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="bb192-108">[Поля и заполнения в элементах управления Windows Forms](margin-and-padding-in-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="bb192-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)</span></span>\
<span data-ttu-id="bb192-109">Описывает свойства <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> и их роли в макете.</span><span class="sxs-lookup"><span data-stu-id="bb192-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="bb192-110">[Как выровняйте элемент управления по краям форм](how-to-align-a-control-to-the-edges-of-forms.md)</span><span class="sxs-lookup"><span data-stu-id="bb192-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)</span></span>\
<span data-ttu-id="bb192-111">Демонстрирует использование свойства <xref:System.Windows.Forms.Control.Dock%2A> для согласования элемента управления с границей занимаемой им формы.</span><span class="sxs-lookup"><span data-stu-id="bb192-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="bb192-112">[Как создать границу вокруг элемента управления Windows Forms с помощью заполнения](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span><span class="sxs-lookup"><span data-stu-id="bb192-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span></span>\
<span data-ttu-id="bb192-113">Демонстрирует использование свойства <xref:System.Windows.Forms.Control.Padding%2A> для структурирования элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bb192-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="bb192-114">[Как реализовать пользовательский обработчик макетов](how-to-implement-a-custom-layout-engine.md)</span><span class="sxs-lookup"><span data-stu-id="bb192-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)</span></span>\
<span data-ttu-id="bb192-115">Демонстрирует реализацию <xref:System.Windows.Forms.Layout.LayoutEngine> для упорядочения элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb192-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="bb192-116">Справочник</span><span class="sxs-lookup"><span data-stu-id="bb192-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="bb192-117">Справочная документация по элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bb192-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="bb192-118">Справочная документация по элементу управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bb192-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb192-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb192-119">See also</span></span>

- [<span data-ttu-id="bb192-120">Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bb192-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="bb192-121">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bb192-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="bb192-122">Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="bb192-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="bb192-123">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bb192-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
