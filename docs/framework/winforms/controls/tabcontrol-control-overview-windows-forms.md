---
title: "Общие сведения об элементе управления TabControl (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 04407ca8ddb51658ffd9cc4078d8f545c08e9312
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="8e48a-102">Общие сведения об элементе управления TabControl (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8e48a-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="8e48a-103">Элемент управления <xref:System.Windows.Forms.TabControl> Windows Forms используется для отображения нескольких вкладок, аналогичных разделителям в записной книжке или меткам в наборе папок в картотеке.</span><span class="sxs-lookup"><span data-stu-id="8e48a-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="8e48a-104">Вкладки могут содержать изображения и другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="8e48a-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="8e48a-105">Можно использовать набор вкладок для создания многостраничных диалоговых окон, отображаются во многих компонентах в операционной системе Windows, например свойства отображения панели управления.</span><span class="sxs-lookup"><span data-stu-id="8e48a-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="8e48a-106">Кроме того <xref:System.Windows.Forms.TabControl> можно использовать для создания страниц свойств, которые используются для настройки группы связанных свойств.</span><span class="sxs-lookup"><span data-stu-id="8e48a-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="8e48a-107">Работа с TabControl</span><span class="sxs-lookup"><span data-stu-id="8e48a-107">Working with TabControl</span></span>  
 <span data-ttu-id="8e48a-108">Наиболее важным свойством <xref:System.Windows.Forms.TabControl> — <xref:System.Windows.Forms.TabControl.TabPages%2A>, который содержит отдельные вкладки.</span><span class="sxs-lookup"><span data-stu-id="8e48a-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="8e48a-109">Каждая вкладка представляет <xref:System.Windows.Forms.TabPage> объекта.</span><span class="sxs-lookup"><span data-stu-id="8e48a-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="8e48a-110">При щелчке вкладки вызывает <xref:System.Windows.Forms.Control.Click> событий для этого <xref:System.Windows.Forms.TabPage> объекта.</span><span class="sxs-lookup"><span data-stu-id="8e48a-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e48a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8e48a-111">See Also</span></span>  
 <xref:System.Windows.Forms.TabControl>  
 [<span data-ttu-id="8e48a-112">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="8e48a-112">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="8e48a-113">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8e48a-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="8e48a-114">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="8e48a-114">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="8e48a-115">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8e48a-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="8e48a-116">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="8e48a-116">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="8e48a-117">Диалоговые окна в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8e48a-117">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)
