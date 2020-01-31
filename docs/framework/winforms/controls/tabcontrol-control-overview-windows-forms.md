---
title: Общие сведения об элементе управления TabControl
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 2668169488b4087673fbf2552650c23cda780642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742830"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="9cb40-102">Общие сведения об элементе управления TabControl (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9cb40-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="9cb40-103">Элемент управления <xref:System.Windows.Forms.TabControl> Windows Forms используется для отображения нескольких вкладок, аналогичных разделителям в записной книжке или меткам в наборе папок в картотеке.</span><span class="sxs-lookup"><span data-stu-id="9cb40-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="9cb40-104">Вкладки могут содержать изображения и другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="9cb40-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="9cb40-105">Элемент управления "Вкладка" можно использовать для создания многостраничного диалогового окна, которое появляется во многих местах в операционной системе Windows, например в свойствах панели управления.</span><span class="sxs-lookup"><span data-stu-id="9cb40-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="9cb40-106">Кроме того, <xref:System.Windows.Forms.TabControl> можно использовать для создания страниц свойств, которые используются для задания группы связанных свойств.</span><span class="sxs-lookup"><span data-stu-id="9cb40-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="9cb40-107">Работа с TabControl</span><span class="sxs-lookup"><span data-stu-id="9cb40-107">Working with TabControl</span></span>  
 <span data-ttu-id="9cb40-108">Наиболее важным свойством <xref:System.Windows.Forms.TabControl> является <xref:System.Windows.Forms.TabControl.TabPages%2A>, который содержит отдельные вкладки.</span><span class="sxs-lookup"><span data-stu-id="9cb40-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="9cb40-109">Каждая отдельная вкладка является объектом <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="9cb40-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="9cb40-110">При нажатии на вкладку вызывается событие <xref:System.Windows.Forms.Control.Click> для этого <xref:System.Windows.Forms.TabPage> объекта.</span><span class="sxs-lookup"><span data-stu-id="9cb40-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb40-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9cb40-111">See also</span></span>

- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="9cb40-112">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="9cb40-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="9cb40-113">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cb40-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="9cb40-114">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="9cb40-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="9cb40-115">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cb40-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="9cb40-116">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="9cb40-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="9cb40-117">Диалоговые окна в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cb40-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
