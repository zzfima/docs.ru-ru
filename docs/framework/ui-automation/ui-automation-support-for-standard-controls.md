---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179853"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="e3812-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="e3812-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="e3812-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="e3812-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e3812-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e3812-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e3812-105">Эта тема содержит [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] информацию о поддержке [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]стандартных элементов управления в приложениях, разработанных для платформ Форм Win32 и Windows.</span><span class="sxs-lookup"><span data-stu-id="e3812-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="e3812-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="e3812-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="e3812-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3812-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="e3812-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3812-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="e3812-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="e3812-109">Win32 Controls</span></span>  
 <span data-ttu-id="e3812-110">Большинство элементов управления Win32 подвергаются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через клиентов-поставщиков в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="e3812-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="e3812-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e3812-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="e3812-112">Полная поддержка обеспечивается только для элементов управления из версии 6 *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="e3812-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="e3812-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="e3812-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="e3812-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="e3812-114">Class name</span></span>|<span data-ttu-id="e3812-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="e3812-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="e3812-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-116">Button</span></span>|<span data-ttu-id="e3812-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-117">Button</span></span>|  
|<span data-ttu-id="e3812-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-118">Button</span></span>|<span data-ttu-id="e3812-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e3812-119">RadioButton</span></span>|  
|<span data-ttu-id="e3812-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-120">Button</span></span>|<span data-ttu-id="e3812-121">Группа</span><span class="sxs-lookup"><span data-stu-id="e3812-121">Group</span></span>|  
|<span data-ttu-id="e3812-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-122">Button</span></span>|<span data-ttu-id="e3812-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e3812-123">CheckBox</span></span>|  
|<span data-ttu-id="e3812-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-124">Button</span></span>|<span data-ttu-id="e3812-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="e3812-125">Hyperlink</span></span>|  
|<span data-ttu-id="e3812-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-126">Button</span></span>|<span data-ttu-id="e3812-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="e3812-127">SplitButton</span></span>|  
|<span data-ttu-id="e3812-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-128">Button</span></span>|<span data-ttu-id="e3812-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e3812-129">CheckBox</span></span>|  
|<span data-ttu-id="e3812-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="e3812-130">ComboBoxEx32</span></span>|<span data-ttu-id="e3812-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e3812-131">ComboBox</span></span>|  
|<span data-ttu-id="e3812-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e3812-132">ComboBox</span></span>|<span data-ttu-id="e3812-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e3812-133">ComboBox</span></span>|  
|<span data-ttu-id="e3812-134">Изменить</span><span class="sxs-lookup"><span data-stu-id="e3812-134">Edit</span></span>|<span data-ttu-id="e3812-135">Документ</span><span class="sxs-lookup"><span data-stu-id="e3812-135">Document</span></span>|  
|<span data-ttu-id="e3812-136">Изменить</span><span class="sxs-lookup"><span data-stu-id="e3812-136">Edit</span></span>|<span data-ttu-id="e3812-137">Изменить</span><span class="sxs-lookup"><span data-stu-id="e3812-137">Edit</span></span>|  
|<span data-ttu-id="e3812-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="e3812-138">SysLink</span></span>|<span data-ttu-id="e3812-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="e3812-139">Hyperlink</span></span>|  
|<span data-ttu-id="e3812-140">Статические</span><span class="sxs-lookup"><span data-stu-id="e3812-140">Static</span></span>|<span data-ttu-id="e3812-141">текст</span><span class="sxs-lookup"><span data-stu-id="e3812-141">Text</span></span>|  
|<span data-ttu-id="e3812-142">Статические</span><span class="sxs-lookup"><span data-stu-id="e3812-142">Static</span></span>|<span data-ttu-id="e3812-143">Образ —</span><span class="sxs-lookup"><span data-stu-id="e3812-143">Image</span></span>|  
|<span data-ttu-id="e3812-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="e3812-144">SysIPAddress32</span></span>|<span data-ttu-id="e3812-145">Другой</span><span class="sxs-lookup"><span data-stu-id="e3812-145">Custom</span></span>|  
|<span data-ttu-id="e3812-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="e3812-146">SysHeader32</span></span>|<span data-ttu-id="e3812-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="e3812-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="e3812-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="e3812-148">SysListView32</span></span>|<span data-ttu-id="e3812-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="e3812-149">DataGrid</span></span>|  
|<span data-ttu-id="e3812-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="e3812-150">SysListView32</span></span>|<span data-ttu-id="e3812-151">Список</span><span class="sxs-lookup"><span data-stu-id="e3812-151">List</span></span>|  
|<span data-ttu-id="e3812-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="e3812-152">ListBox</span></span>|<span data-ttu-id="e3812-153">Список</span><span class="sxs-lookup"><span data-stu-id="e3812-153">List</span></span>|  
|<span data-ttu-id="e3812-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="e3812-154">ListBox</span></span>|<span data-ttu-id="e3812-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="e3812-155">ListItem</span></span>|  
|<span data-ttu-id="e3812-156">#32768</span><span class="sxs-lookup"><span data-stu-id="e3812-156">#32768</span></span>|<span data-ttu-id="e3812-157">Меню</span><span class="sxs-lookup"><span data-stu-id="e3812-157">Menu</span></span>|  
|<span data-ttu-id="e3812-158">#32768</span><span class="sxs-lookup"><span data-stu-id="e3812-158">#32768</span></span>|<span data-ttu-id="e3812-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="e3812-159">MenuItem</span></span>|  
|<span data-ttu-id="e3812-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="e3812-160">msctls_progress32</span></span>|<span data-ttu-id="e3812-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e3812-161">ProgressBar</span></span>|  
|<span data-ttu-id="e3812-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="e3812-162">RichEdit</span></span>|<span data-ttu-id="e3812-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="e3812-163">Document.</span></span> <span data-ttu-id="e3812-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="e3812-164">See note.</span></span>|  
|<span data-ttu-id="e3812-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="e3812-165">RichEdit20A</span></span>|<span data-ttu-id="e3812-166">Документ</span><span class="sxs-lookup"><span data-stu-id="e3812-166">Document</span></span>|  
|<span data-ttu-id="e3812-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="e3812-167">RichEdit20W</span></span>|<span data-ttu-id="e3812-168">Документ</span><span class="sxs-lookup"><span data-stu-id="e3812-168">Document</span></span>|  
|<span data-ttu-id="e3812-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="e3812-169">RichEdit50W</span></span>|<span data-ttu-id="e3812-170">Документ</span><span class="sxs-lookup"><span data-stu-id="e3812-170">Document</span></span>|  
|<span data-ttu-id="e3812-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e3812-171">ScrollBar</span></span>|<span data-ttu-id="e3812-172">Ползунок</span><span class="sxs-lookup"><span data-stu-id="e3812-172">Slider</span></span>|  
|<span data-ttu-id="e3812-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="e3812-173">msctls_trackbar32</span></span>|<span data-ttu-id="e3812-174">Ползунок</span><span class="sxs-lookup"><span data-stu-id="e3812-174">Slider</span></span>|  
|<span data-ttu-id="e3812-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="e3812-175">msctls_updown32</span></span>|<span data-ttu-id="e3812-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="e3812-176">Spinner</span></span>|  
|<span data-ttu-id="e3812-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="e3812-177">msctls_statusbar32</span></span>|<span data-ttu-id="e3812-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="e3812-178">StatusBar</span></span>|  
|<span data-ttu-id="e3812-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="e3812-179">SysTabControl32</span></span>|<span data-ttu-id="e3812-180">Вкладка</span><span class="sxs-lookup"><span data-stu-id="e3812-180">Tab</span></span>|  
|<span data-ttu-id="e3812-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="e3812-181">SysTabControl32</span></span>|<span data-ttu-id="e3812-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="e3812-182">TabItem</span></span>|  
|<span data-ttu-id="e3812-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-183">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="e3812-184">ToolBar</span></span>|  
|<span data-ttu-id="e3812-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-185">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="e3812-186">MenuItem</span></span>|  
|<span data-ttu-id="e3812-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-187">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-188">Button</span></span>|  
|<span data-ttu-id="e3812-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-189">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e3812-190">CheckBox</span></span>|  
|<span data-ttu-id="e3812-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-191">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e3812-192">RadioButton</span></span>|  
|<span data-ttu-id="e3812-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-193">ToolbarWindow32</span></span>|<span data-ttu-id="e3812-194">Разделитель</span><span class="sxs-lookup"><span data-stu-id="e3812-194">Separator</span></span>|  
|<span data-ttu-id="e3812-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="e3812-195">tooltips_class32</span></span>|<span data-ttu-id="e3812-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="e3812-196">ToolTip</span></span>|  
|<span data-ttu-id="e3812-197">#32774</span><span class="sxs-lookup"><span data-stu-id="e3812-197">#32774</span></span>|<span data-ttu-id="e3812-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="e3812-198">ToolTip</span></span>|  
|<span data-ttu-id="e3812-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="e3812-199">ReBarWindow32</span></span>|<span data-ttu-id="e3812-200">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="e3812-200">Toolbar</span></span>|  
|<span data-ttu-id="e3812-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="e3812-201">SysTreeView32</span></span>|<span data-ttu-id="e3812-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="e3812-202">Tree</span></span>|  
|<span data-ttu-id="e3812-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="e3812-203">SysTreeView32</span></span>|<span data-ttu-id="e3812-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="e3812-204">TreeItem</span></span>|  
  
 <span data-ttu-id="e3812-205">**Заметка** Управление RichEdit поддерживается только для версий, поставляемых с Windows Vista (в версии RichEd20.dll 3.1 и позже, и MsftEdit.dll версии 4.1 и позже).</span><span class="sxs-lookup"><span data-stu-id="e3812-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="e3812-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e3812-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="e3812-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="e3812-207">Class name</span></span>|<span data-ttu-id="e3812-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="e3812-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="e3812-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="e3812-209">SysAnimate32</span></span>|<span data-ttu-id="e3812-210">Образ —</span><span class="sxs-lookup"><span data-stu-id="e3812-210">Image</span></span>|  
|<span data-ttu-id="e3812-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="e3812-211">SysPager</span></span>|<span data-ttu-id="e3812-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="e3812-212">Spinner</span></span>|  
|<span data-ttu-id="e3812-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="e3812-213">SysDateTimePick32</span></span>|<span data-ttu-id="e3812-214">Другой</span><span class="sxs-lookup"><span data-stu-id="e3812-214">Custom</span></span>|  
|<span data-ttu-id="e3812-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="e3812-215">SysMonthCal32</span></span>|<span data-ttu-id="e3812-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="e3812-216">Calendar</span></span>|  
|<span data-ttu-id="e3812-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="e3812-217">MS_WINNOTE</span></span>|<span data-ttu-id="e3812-218">Подсказка</span><span class="sxs-lookup"><span data-stu-id="e3812-218">Tooltip</span></span>|  
|<span data-ttu-id="e3812-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="e3812-219">VBBubble</span></span>|<span data-ttu-id="e3812-220">Подсказка</span><span class="sxs-lookup"><span data-stu-id="e3812-220">Tooltip</span></span>|  
|<span data-ttu-id="e3812-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="e3812-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="e3812-222">Ползунок</span><span class="sxs-lookup"><span data-stu-id="e3812-222">Slider</span></span>|  
|<span data-ttu-id="e3812-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="e3812-223">SuperGrid</span></span>|<span data-ttu-id="e3812-224">Другой</span><span class="sxs-lookup"><span data-stu-id="e3812-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="e3812-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3812-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="e3812-226">Элементы управления Windows [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Forms подвергаются воздействию через поставщиков со стороны клиентов в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="e3812-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="e3812-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e3812-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="e3812-228">Как правило, элементы управления Windows Forms, управляемые обертками для общих элементов управления Win32, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e3812-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="e3812-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="e3812-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="e3812-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="e3812-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="e3812-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="e3812-231">Button</span></span>|  
|<span data-ttu-id="e3812-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e3812-232">CheckBox</span></span>|  
|<span data-ttu-id="e3812-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="e3812-233">CheckedListBox</span></span>|  
|<span data-ttu-id="e3812-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-234">ColorDialog</span></span>|  
|<span data-ttu-id="e3812-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e3812-235">ComboBox</span></span>|  
|<span data-ttu-id="e3812-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="e3812-236">FolderBrowser</span></span>|  
|<span data-ttu-id="e3812-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-237">FontDialog</span></span>|  
|<span data-ttu-id="e3812-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="e3812-238">GroupBox</span></span>|  
|<span data-ttu-id="e3812-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="e3812-239">HscrollBar</span></span>|  
|<span data-ttu-id="e3812-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="e3812-240">ImageList</span></span>|  
|<span data-ttu-id="e3812-241">Метка</span><span class="sxs-lookup"><span data-stu-id="e3812-241">Label</span></span>|  
|<span data-ttu-id="e3812-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="e3812-242">ListBox</span></span>|  
|<span data-ttu-id="e3812-243">ListView</span><span class="sxs-lookup"><span data-stu-id="e3812-243">ListView</span></span>|  
|<span data-ttu-id="e3812-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e3812-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="e3812-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="e3812-245">MonthCalendar</span></span>|  
|<span data-ttu-id="e3812-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="e3812-246">NotifyIcon</span></span>|  
|<span data-ttu-id="e3812-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="e3812-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="e3812-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-249">PrintDialog</span></span>|  
|<span data-ttu-id="e3812-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e3812-250">ProgressBar</span></span>|  
|<span data-ttu-id="e3812-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e3812-251">RadioButton</span></span>|  
|<span data-ttu-id="e3812-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e3812-252">RichTextBox</span></span>|  
|<span data-ttu-id="e3812-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="e3812-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="e3812-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="e3812-254">ScrollableControl</span></span>|  
|<span data-ttu-id="e3812-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="e3812-255">SoundPlayer</span></span>|  
|<span data-ttu-id="e3812-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="e3812-256">StatusBar</span></span>|  
|<span data-ttu-id="e3812-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="e3812-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="e3812-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="e3812-258">TextBox</span></span>|  
|<span data-ttu-id="e3812-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="e3812-259">Timer</span></span>|  
|<span data-ttu-id="e3812-260">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="e3812-260">Toolbar</span></span>|  
|<span data-ttu-id="e3812-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="e3812-261">ToolTip</span></span>|  
|<span data-ttu-id="e3812-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="e3812-262">TrackBar</span></span>|  
|<span data-ttu-id="e3812-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="e3812-263">TreeView</span></span>|  
|<span data-ttu-id="e3812-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="e3812-264">VscrollBar</span></span>|  
|<span data-ttu-id="e3812-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="e3812-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="e3812-266">Следующие элементы [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] управления подвергаются только через их поддержку Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="e3812-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="e3812-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="e3812-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="e3812-268">Имя элемента управления</span><span class="sxs-lookup"><span data-stu-id="e3812-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="e3812-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="e3812-269">BindingSource</span></span>|  
|<span data-ttu-id="e3812-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="e3812-270">DataGrid</span></span>|  
|<span data-ttu-id="e3812-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="e3812-271">DataGridView</span></span>|  
|<span data-ttu-id="e3812-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="e3812-272">DataNavigator</span></span>|  
|<span data-ttu-id="e3812-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e3812-273">DomainUpDown</span></span>|  
|<span data-ttu-id="e3812-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="e3812-274">ErrorProvider</span></span>|  
|<span data-ttu-id="e3812-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e3812-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="e3812-276">Форма</span><span class="sxs-lookup"><span data-stu-id="e3812-276">Form</span></span>|  
|<span data-ttu-id="e3812-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="e3812-277">LinkLabel</span></span>|  
|<span data-ttu-id="e3812-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="e3812-278">HelpProvider</span></span>|  
|<span data-ttu-id="e3812-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="e3812-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="e3812-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="e3812-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="e3812-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="e3812-281">NumericUpDown</span></span>|  
|<span data-ttu-id="e3812-282">Panel</span><span class="sxs-lookup"><span data-stu-id="e3812-282">Panel</span></span>|  
|<span data-ttu-id="e3812-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="e3812-283">PictureBox</span></span>|  
|<span data-ttu-id="e3812-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="e3812-284">PrintDocument</span></span>|  
|<span data-ttu-id="e3812-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="e3812-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="e3812-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="e3812-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="e3812-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="e3812-287">PropertyGrid</span></span>|  
|<span data-ttu-id="e3812-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="e3812-288">UserControl</span></span>|  
|<span data-ttu-id="e3812-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e3812-289">ToolStrip</span></span>|  
|<span data-ttu-id="e3812-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e3812-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="e3812-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="e3812-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="e3812-292">Разделитель</span><span class="sxs-lookup"><span data-stu-id="e3812-292">Splitter</span></span>|  
|<span data-ttu-id="e3812-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="e3812-293">RaftingContainer</span></span>|  
|<span data-ttu-id="e3812-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="e3812-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3812-295">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e3812-295">See also</span></span>

- [<span data-ttu-id="e3812-296">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e3812-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
