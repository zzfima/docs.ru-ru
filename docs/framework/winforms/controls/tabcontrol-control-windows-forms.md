---
title: "Элемент управления TabControl (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabControl control [Windows Forms]
- tab controls
- tab controls [Windows Forms], creating
- multipage dialog boxes
- dialog boxes [Windows Forms], creating multipage
- property pages [Windows Forms], creating
- tab dialog boxes
ms.assetid: 915091af-93ac-4d3d-8283-738dd2d21ea7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 705f9dbb8ea7f4d462a2b19cc0c6b845ae8f578b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="tabcontrol-control-windows-forms"></a><span data-ttu-id="dc0f0-102">Элемент управления TabControl (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dc0f0-102">TabControl Control (Windows Forms)</span></span>
<span data-ttu-id="dc0f0-103">Элемент управления `TabControl` Windows Forms используется для отображения нескольких вкладок, аналогичных разделителям в записной книжке или меткам в наборе папок в картотеке.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-103">The Windows Forms `TabControl` displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="dc0f0-104">Вкладки могут содержать изображения и другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="dc0f0-105">Используйте элемент управления `TabControl` для создания страниц свойств.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-105">Use the `TabControl` to create property pages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc0f0-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="dc0f0-106">In This Section</span></span>  
 [<span data-ttu-id="dc0f0-107">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="dc0f0-107">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="dc0f0-108">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="dc0f0-109">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="dc0f0-109">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 <span data-ttu-id="dc0f0-110">Инструкции по отображению элементов управления на страницах вкладок.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-110">Gives directions for displaying controls on tab pages.</span></span>  
  
 [<span data-ttu-id="dc0f0-111">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc0f0-111">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="dc0f0-112">Инструкции по добавлению и удалению вкладок в конструкторе или в коде.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-112">Gives directions for adding and removing tabs in the designer or in code.</span></span>  
  
 [<span data-ttu-id="dc0f0-113">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc0f0-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="dc0f0-114">Инструкции по настройке свойств, которые влияют на внешний вид отдельных вкладок.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-114">Gives directions for adjusting properties that affect the appearance of individual tabs.</span></span>  
  
 [<span data-ttu-id="dc0f0-115">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="dc0f0-115">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 <span data-ttu-id="dc0f0-116">Объясняется, как ограничить доступ к вкладке, например на основе учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-116">Explains how to restrict access to a tab page, possibly based on user credentials.</span></span>  
  
 <span data-ttu-id="dc0f0-117">См. также [как: Добавление и удаление вкладок с Windows Forms TabControl с помощью конструктора](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [как: добавьте элемент управления вкладки страницы с помощью конструктора](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="dc0f0-117">Also see [How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [How to: Add a Control to a Tab Page Using the Designer](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dc0f0-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="dc0f0-118">Reference</span></span>  
 <span data-ttu-id="dc0f0-119">Класс <xref:System.Windows.Forms.TabControl></span><span class="sxs-lookup"><span data-stu-id="dc0f0-119"><xref:System.Windows.Forms.TabControl> class</span></span>  
 <span data-ttu-id="dc0f0-120">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dc0f0-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="dc0f0-121">Related Sections</span></span>  
 [<span data-ttu-id="dc0f0-122">Диалоговые окна в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc0f0-122">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)  
 <span data-ttu-id="dc0f0-123">Список задач для диалоговых окон, в которых часто отображаются вкладки.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-123">Provides a list of tasks for dialog boxes, which often display tabs.</span></span>  
  
 [<span data-ttu-id="dc0f0-124">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc0f0-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="dc0f0-125">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
