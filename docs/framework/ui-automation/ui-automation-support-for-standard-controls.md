---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 3ccd6e1348125f5d901e0f093d2b5483b818719f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="14cb7-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="14cb7-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="14cb7-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="14cb7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="14cb7-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="14cb7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="14cb7-105">В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14cb7-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="14cb7-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="14cb7-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="14cb7-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14cb7-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="14cb7-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14cb7-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="14cb7-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="14cb7-109">Win32 Controls</span></span>  
 <span data-ttu-id="14cb7-110">Большинство элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="14cb7-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="14cb7-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="14cb7-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="14cb7-112">Полная поддержка предоставляется только для элементов управления с версии 6 ComCtrl32.dll (доступной в [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="14cb7-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="14cb7-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="14cb7-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="14cb7-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="14cb7-114">Class name</span></span>|<span data-ttu-id="14cb7-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="14cb7-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="14cb7-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-116">Button</span></span>|<span data-ttu-id="14cb7-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-117">Button</span></span>|  
|<span data-ttu-id="14cb7-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-118">Button</span></span>|<span data-ttu-id="14cb7-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="14cb7-119">RadioButton</span></span>|  
|<span data-ttu-id="14cb7-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-120">Button</span></span>|<span data-ttu-id="14cb7-121">Группа</span><span class="sxs-lookup"><span data-stu-id="14cb7-121">Group</span></span>|  
|<span data-ttu-id="14cb7-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-122">Button</span></span>|<span data-ttu-id="14cb7-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-123">CheckBox</span></span>|  
|<span data-ttu-id="14cb7-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-124">Button</span></span>|<span data-ttu-id="14cb7-125">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="14cb7-125">Hyperlink</span></span>|  
|<span data-ttu-id="14cb7-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-126">Button</span></span>|<span data-ttu-id="14cb7-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="14cb7-127">SplitButton</span></span>|  
|<span data-ttu-id="14cb7-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-128">Button</span></span>|<span data-ttu-id="14cb7-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-129">CheckBox</span></span>|  
|<span data-ttu-id="14cb7-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="14cb7-130">ComboBoxEx32</span></span>|<span data-ttu-id="14cb7-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-131">ComboBox</span></span>|  
|<span data-ttu-id="14cb7-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-132">ComboBox</span></span>|<span data-ttu-id="14cb7-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-133">ComboBox</span></span>|  
|<span data-ttu-id="14cb7-134">Правка</span><span class="sxs-lookup"><span data-stu-id="14cb7-134">Edit</span></span>|<span data-ttu-id="14cb7-135">Document</span><span class="sxs-lookup"><span data-stu-id="14cb7-135">Document</span></span>|  
|<span data-ttu-id="14cb7-136">Правка</span><span class="sxs-lookup"><span data-stu-id="14cb7-136">Edit</span></span>|<span data-ttu-id="14cb7-137">Правка</span><span class="sxs-lookup"><span data-stu-id="14cb7-137">Edit</span></span>|  
|<span data-ttu-id="14cb7-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="14cb7-138">SysLink</span></span>|<span data-ttu-id="14cb7-139">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="14cb7-139">Hyperlink</span></span>|  
|<span data-ttu-id="14cb7-140">Static</span><span class="sxs-lookup"><span data-stu-id="14cb7-140">Static</span></span>|<span data-ttu-id="14cb7-141">Text</span><span class="sxs-lookup"><span data-stu-id="14cb7-141">Text</span></span>|  
|<span data-ttu-id="14cb7-142">Static</span><span class="sxs-lookup"><span data-stu-id="14cb7-142">Static</span></span>|<span data-ttu-id="14cb7-143">Изображение</span><span class="sxs-lookup"><span data-stu-id="14cb7-143">Image</span></span>|  
|<span data-ttu-id="14cb7-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="14cb7-144">SysIPAddress32</span></span>|<span data-ttu-id="14cb7-145">Другой</span><span class="sxs-lookup"><span data-stu-id="14cb7-145">Custom</span></span>|  
|<span data-ttu-id="14cb7-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="14cb7-146">SysHeader32</span></span>|<span data-ttu-id="14cb7-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="14cb7-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="14cb7-148">SysListView32</span></span>|<span data-ttu-id="14cb7-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="14cb7-149">DataGrid</span></span>|  
|<span data-ttu-id="14cb7-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="14cb7-150">SysListView32</span></span>|<span data-ttu-id="14cb7-151">Список</span><span class="sxs-lookup"><span data-stu-id="14cb7-151">List</span></span>|  
|<span data-ttu-id="14cb7-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-152">ListBox</span></span>|<span data-ttu-id="14cb7-153">Список</span><span class="sxs-lookup"><span data-stu-id="14cb7-153">List</span></span>|  
|<span data-ttu-id="14cb7-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-154">ListBox</span></span>|<span data-ttu-id="14cb7-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-155">ListItem</span></span>|  
|<span data-ttu-id="14cb7-156">#32768</span><span class="sxs-lookup"><span data-stu-id="14cb7-156">#32768</span></span>|<span data-ttu-id="14cb7-157">Меню</span><span class="sxs-lookup"><span data-stu-id="14cb7-157">Menu</span></span>|  
|<span data-ttu-id="14cb7-158">#32768</span><span class="sxs-lookup"><span data-stu-id="14cb7-158">#32768</span></span>|<span data-ttu-id="14cb7-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-159">MenuItem</span></span>|  
|<span data-ttu-id="14cb7-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="14cb7-160">msctls_progress32</span></span>|<span data-ttu-id="14cb7-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-161">ProgressBar</span></span>|  
|<span data-ttu-id="14cb7-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="14cb7-162">RichEdit</span></span>|<span data-ttu-id="14cb7-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="14cb7-163">Document.</span></span> <span data-ttu-id="14cb7-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="14cb7-164">See note.</span></span>|  
|<span data-ttu-id="14cb7-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="14cb7-165">RichEdit20A</span></span>|<span data-ttu-id="14cb7-166">Document</span><span class="sxs-lookup"><span data-stu-id="14cb7-166">Document</span></span>|  
|<span data-ttu-id="14cb7-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="14cb7-167">RichEdit20W</span></span>|<span data-ttu-id="14cb7-168">Document</span><span class="sxs-lookup"><span data-stu-id="14cb7-168">Document</span></span>|  
|<span data-ttu-id="14cb7-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="14cb7-169">RichEdit50W</span></span>|<span data-ttu-id="14cb7-170">Document</span><span class="sxs-lookup"><span data-stu-id="14cb7-170">Document</span></span>|  
|<span data-ttu-id="14cb7-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-171">ScrollBar</span></span>|<span data-ttu-id="14cb7-172">Slider</span><span class="sxs-lookup"><span data-stu-id="14cb7-172">Slider</span></span>|  
|<span data-ttu-id="14cb7-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="14cb7-173">msctls_trackbar32</span></span>|<span data-ttu-id="14cb7-174">Slider</span><span class="sxs-lookup"><span data-stu-id="14cb7-174">Slider</span></span>|  
|<span data-ttu-id="14cb7-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="14cb7-175">msctls_updown32</span></span>|<span data-ttu-id="14cb7-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="14cb7-176">Spinner</span></span>|  
|<span data-ttu-id="14cb7-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="14cb7-177">msctls_statusbar32</span></span>|<span data-ttu-id="14cb7-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-178">StatusBar</span></span>|  
|<span data-ttu-id="14cb7-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="14cb7-179">SysTabControl32</span></span>|<span data-ttu-id="14cb7-180">Tab</span><span class="sxs-lookup"><span data-stu-id="14cb7-180">Tab</span></span>|  
|<span data-ttu-id="14cb7-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="14cb7-181">SysTabControl32</span></span>|<span data-ttu-id="14cb7-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-182">TabItem</span></span>|  
|<span data-ttu-id="14cb7-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-183">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-184">ToolBar</span></span>|  
|<span data-ttu-id="14cb7-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-185">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-186">MenuItem</span></span>|  
|<span data-ttu-id="14cb7-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-187">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-188">Button</span></span>|  
|<span data-ttu-id="14cb7-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-189">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-190">CheckBox</span></span>|  
|<span data-ttu-id="14cb7-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-191">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="14cb7-192">RadioButton</span></span>|  
|<span data-ttu-id="14cb7-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-193">ToolbarWindow32</span></span>|<span data-ttu-id="14cb7-194">Separator</span><span class="sxs-lookup"><span data-stu-id="14cb7-194">Separator</span></span>|  
|<span data-ttu-id="14cb7-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="14cb7-195">tooltips_class32</span></span>|<span data-ttu-id="14cb7-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="14cb7-196">ToolTip</span></span>|  
|<span data-ttu-id="14cb7-197">#32774</span><span class="sxs-lookup"><span data-stu-id="14cb7-197">#32774</span></span>|<span data-ttu-id="14cb7-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="14cb7-198">ToolTip</span></span>|  
|<span data-ttu-id="14cb7-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="14cb7-199">ReBarWindow32</span></span>|<span data-ttu-id="14cb7-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="14cb7-200">Toolbar</span></span>|  
|<span data-ttu-id="14cb7-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="14cb7-201">SysTreeView32</span></span>|<span data-ttu-id="14cb7-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="14cb7-202">Tree</span></span>|  
|<span data-ttu-id="14cb7-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="14cb7-203">SysTreeView32</span></span>|<span data-ttu-id="14cb7-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="14cb7-204">TreeItem</span></span>|  
  
 <span data-ttu-id="14cb7-205">**Примечание.** Элемент управления RichEdit поддерживается только для версий, поставляемых в составе [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (в RichEd20.dll версии 3.1 и более поздних версий и MsftEdit.dll версии 4.1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="14cb7-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="14cb7-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="14cb7-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="14cb7-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="14cb7-207">Class name</span></span>|<span data-ttu-id="14cb7-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="14cb7-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="14cb7-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="14cb7-209">SysAnimate32</span></span>|<span data-ttu-id="14cb7-210">Изображение</span><span class="sxs-lookup"><span data-stu-id="14cb7-210">Image</span></span>|  
|<span data-ttu-id="14cb7-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="14cb7-211">SysPager</span></span>|<span data-ttu-id="14cb7-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="14cb7-212">Spinner</span></span>|  
|<span data-ttu-id="14cb7-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="14cb7-213">SysDateTimePick32</span></span>|<span data-ttu-id="14cb7-214">Другой</span><span class="sxs-lookup"><span data-stu-id="14cb7-214">Custom</span></span>|  
|<span data-ttu-id="14cb7-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="14cb7-215">SysMonthCal32</span></span>|<span data-ttu-id="14cb7-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="14cb7-216">Calendar</span></span>|  
|<span data-ttu-id="14cb7-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="14cb7-217">MS_WINNOTE</span></span>|<span data-ttu-id="14cb7-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="14cb7-218">Tooltip</span></span>|  
|<span data-ttu-id="14cb7-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="14cb7-219">VBBubble</span></span>|<span data-ttu-id="14cb7-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="14cb7-220">Tooltip</span></span>|  
|<span data-ttu-id="14cb7-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="14cb7-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="14cb7-222">Slider</span><span class="sxs-lookup"><span data-stu-id="14cb7-222">Slider</span></span>|  
|<span data-ttu-id="14cb7-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="14cb7-223">SuperGrid</span></span>|<span data-ttu-id="14cb7-224">Другой</span><span class="sxs-lookup"><span data-stu-id="14cb7-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="14cb7-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14cb7-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="14cb7-226">Элементы управления Windows Forms предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="14cb7-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="14cb7-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="14cb7-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="14cb7-228">Как правило, элементы управления Windows Forms, которые являются управляемыми оболочками для [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] стандартных элементов управления поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14cb7-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="14cb7-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="14cb7-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="14cb7-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="14cb7-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="14cb7-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="14cb7-231">Button</span></span>|  
|<span data-ttu-id="14cb7-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-232">CheckBox</span></span>|  
|<span data-ttu-id="14cb7-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-233">CheckedListBox</span></span>|  
|<span data-ttu-id="14cb7-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-234">ColorDialog</span></span>|  
|<span data-ttu-id="14cb7-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-235">ComboBox</span></span>|  
|<span data-ttu-id="14cb7-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="14cb7-236">FolderBrowser</span></span>|  
|<span data-ttu-id="14cb7-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-237">FontDialog</span></span>|  
|<span data-ttu-id="14cb7-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-238">GroupBox</span></span>|  
|<span data-ttu-id="14cb7-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-239">HscrollBar</span></span>|  
|<span data-ttu-id="14cb7-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="14cb7-240">ImageList</span></span>|  
|<span data-ttu-id="14cb7-241">Метка</span><span class="sxs-lookup"><span data-stu-id="14cb7-241">Label</span></span>|  
|<span data-ttu-id="14cb7-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-242">ListBox</span></span>|  
|<span data-ttu-id="14cb7-243">ListView</span><span class="sxs-lookup"><span data-stu-id="14cb7-243">ListView</span></span>|  
|<span data-ttu-id="14cb7-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="14cb7-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="14cb7-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="14cb7-245">MonthCalendar</span></span>|  
|<span data-ttu-id="14cb7-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="14cb7-246">NotifyIcon</span></span>|  
|<span data-ttu-id="14cb7-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="14cb7-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="14cb7-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-249">PrintDialog</span></span>|  
|<span data-ttu-id="14cb7-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-250">ProgressBar</span></span>|  
|<span data-ttu-id="14cb7-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="14cb7-251">RadioButton</span></span>|  
|<span data-ttu-id="14cb7-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-252">RichTextBox</span></span>|  
|<span data-ttu-id="14cb7-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="14cb7-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="14cb7-254">ScrollableControl</span></span>|  
|<span data-ttu-id="14cb7-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="14cb7-255">SoundPlayer</span></span>|  
|<span data-ttu-id="14cb7-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-256">StatusBar</span></span>|  
|<span data-ttu-id="14cb7-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="14cb7-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="14cb7-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-258">TextBox</span></span>|  
|<span data-ttu-id="14cb7-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="14cb7-259">Timer</span></span>|  
|<span data-ttu-id="14cb7-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-260">Toolbar</span></span>|  
|<span data-ttu-id="14cb7-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="14cb7-261">ToolTip</span></span>|  
|<span data-ttu-id="14cb7-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-262">TrackBar</span></span>|  
|<span data-ttu-id="14cb7-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="14cb7-263">TreeView</span></span>|  
|<span data-ttu-id="14cb7-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="14cb7-264">VscrollBar</span></span>|  
|<span data-ttu-id="14cb7-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="14cb7-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="14cb7-266">Следующие элементы управления предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через их поддержку [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14cb7-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="14cb7-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="14cb7-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="14cb7-268">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="14cb7-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="14cb7-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="14cb7-269">BindingSource</span></span>|  
|<span data-ttu-id="14cb7-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="14cb7-270">DataGrid</span></span>|  
|<span data-ttu-id="14cb7-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="14cb7-271">DataGridView</span></span>|  
|<span data-ttu-id="14cb7-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="14cb7-272">DataNavigator</span></span>|  
|<span data-ttu-id="14cb7-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="14cb7-273">DomainUpDown</span></span>|  
|<span data-ttu-id="14cb7-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="14cb7-274">ErrorProvider</span></span>|  
|<span data-ttu-id="14cb7-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14cb7-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="14cb7-276">Form</span><span class="sxs-lookup"><span data-stu-id="14cb7-276">Form</span></span>|  
|<span data-ttu-id="14cb7-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="14cb7-277">LinkLabel</span></span>|  
|<span data-ttu-id="14cb7-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="14cb7-278">HelpProvider</span></span>|  
|<span data-ttu-id="14cb7-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="14cb7-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="14cb7-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="14cb7-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="14cb7-281">NumericUpDown</span></span>|  
|<span data-ttu-id="14cb7-282">Panel</span><span class="sxs-lookup"><span data-stu-id="14cb7-282">Panel</span></span>|  
|<span data-ttu-id="14cb7-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="14cb7-283">PictureBox</span></span>|  
|<span data-ttu-id="14cb7-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="14cb7-284">PrintDocument</span></span>|  
|<span data-ttu-id="14cb7-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="14cb7-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="14cb7-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="14cb7-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="14cb7-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="14cb7-287">PropertyGrid</span></span>|  
|<span data-ttu-id="14cb7-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="14cb7-288">UserControl</span></span>|  
|<span data-ttu-id="14cb7-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="14cb7-289">ToolStrip</span></span>|  
|<span data-ttu-id="14cb7-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14cb7-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="14cb7-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="14cb7-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="14cb7-292">Разделитель</span><span class="sxs-lookup"><span data-stu-id="14cb7-292">Splitter</span></span>|  
|<span data-ttu-id="14cb7-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="14cb7-293">RaftingContainer</span></span>|  
|<span data-ttu-id="14cb7-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="14cb7-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14cb7-295">См. также</span><span class="sxs-lookup"><span data-stu-id="14cb7-295">See Also</span></span>  
 [<span data-ttu-id="14cb7-296">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="14cb7-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
