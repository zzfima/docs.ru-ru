---
title: "Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 71a5a2e4319debf1a4d8ddd08d7f0979443682b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="13cee-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="13cee-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="13cee-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="13cee-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="13cee-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="13cee-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="13cee-105">В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13cee-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="13cee-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="13cee-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="13cee-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cee-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="13cee-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cee-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="13cee-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="13cee-109">Win32 Controls</span></span>  
 <span data-ttu-id="13cee-110">Большинство элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="13cee-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="13cee-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="13cee-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="13cee-112">Полная поддержка предоставляется только для элементов управления с версии 6 ComCtrl32.dll (доступной в [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="13cee-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="13cee-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="13cee-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="13cee-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="13cee-114">Class name</span></span>|<span data-ttu-id="13cee-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="13cee-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="13cee-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-116">Button</span></span>|<span data-ttu-id="13cee-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-117">Button</span></span>|  
|<span data-ttu-id="13cee-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-118">Button</span></span>|<span data-ttu-id="13cee-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="13cee-119">RadioButton</span></span>|  
|<span data-ttu-id="13cee-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-120">Button</span></span>|<span data-ttu-id="13cee-121">Группа</span><span class="sxs-lookup"><span data-stu-id="13cee-121">Group</span></span>|  
|<span data-ttu-id="13cee-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-122">Button</span></span>|<span data-ttu-id="13cee-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="13cee-123">CheckBox</span></span>|  
|<span data-ttu-id="13cee-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-124">Button</span></span>|<span data-ttu-id="13cee-125">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="13cee-125">Hyperlink</span></span>|  
|<span data-ttu-id="13cee-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-126">Button</span></span>|<span data-ttu-id="13cee-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="13cee-127">SplitButton</span></span>|  
|<span data-ttu-id="13cee-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-128">Button</span></span>|<span data-ttu-id="13cee-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="13cee-129">CheckBox</span></span>|  
|<span data-ttu-id="13cee-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="13cee-130">ComboBoxEx32</span></span>|<span data-ttu-id="13cee-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="13cee-131">ComboBox</span></span>|  
|<span data-ttu-id="13cee-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="13cee-132">ComboBox</span></span>|<span data-ttu-id="13cee-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="13cee-133">ComboBox</span></span>|  
|<span data-ttu-id="13cee-134">Правка</span><span class="sxs-lookup"><span data-stu-id="13cee-134">Edit</span></span>|<span data-ttu-id="13cee-135">Document</span><span class="sxs-lookup"><span data-stu-id="13cee-135">Document</span></span>|  
|<span data-ttu-id="13cee-136">Правка</span><span class="sxs-lookup"><span data-stu-id="13cee-136">Edit</span></span>|<span data-ttu-id="13cee-137">Правка</span><span class="sxs-lookup"><span data-stu-id="13cee-137">Edit</span></span>|  
|<span data-ttu-id="13cee-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="13cee-138">SysLink</span></span>|<span data-ttu-id="13cee-139">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="13cee-139">Hyperlink</span></span>|  
|<span data-ttu-id="13cee-140">Static</span><span class="sxs-lookup"><span data-stu-id="13cee-140">Static</span></span>|<span data-ttu-id="13cee-141">Text</span><span class="sxs-lookup"><span data-stu-id="13cee-141">Text</span></span>|  
|<span data-ttu-id="13cee-142">Static</span><span class="sxs-lookup"><span data-stu-id="13cee-142">Static</span></span>|<span data-ttu-id="13cee-143">Изображение</span><span class="sxs-lookup"><span data-stu-id="13cee-143">Image</span></span>|  
|<span data-ttu-id="13cee-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="13cee-144">SysIPAddress32</span></span>|<span data-ttu-id="13cee-145">Другой</span><span class="sxs-lookup"><span data-stu-id="13cee-145">Custom</span></span>|  
|<span data-ttu-id="13cee-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="13cee-146">SysHeader32</span></span>|<span data-ttu-id="13cee-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="13cee-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="13cee-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="13cee-148">SysListView32</span></span>|<span data-ttu-id="13cee-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="13cee-149">DataGrid</span></span>|  
|<span data-ttu-id="13cee-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="13cee-150">SysListView32</span></span>|<span data-ttu-id="13cee-151">Список</span><span class="sxs-lookup"><span data-stu-id="13cee-151">List</span></span>|  
|<span data-ttu-id="13cee-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="13cee-152">ListBox</span></span>|<span data-ttu-id="13cee-153">Список</span><span class="sxs-lookup"><span data-stu-id="13cee-153">List</span></span>|  
|<span data-ttu-id="13cee-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="13cee-154">ListBox</span></span>|<span data-ttu-id="13cee-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="13cee-155">ListItem</span></span>|  
|<span data-ttu-id="13cee-156">#32768</span><span class="sxs-lookup"><span data-stu-id="13cee-156">#32768</span></span>|<span data-ttu-id="13cee-157">Меню</span><span class="sxs-lookup"><span data-stu-id="13cee-157">Menu</span></span>|  
|<span data-ttu-id="13cee-158">#32768</span><span class="sxs-lookup"><span data-stu-id="13cee-158">#32768</span></span>|<span data-ttu-id="13cee-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="13cee-159">MenuItem</span></span>|  
|<span data-ttu-id="13cee-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="13cee-160">msctls_progress32</span></span>|<span data-ttu-id="13cee-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="13cee-161">ProgressBar</span></span>|  
|<span data-ttu-id="13cee-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="13cee-162">RichEdit</span></span>|<span data-ttu-id="13cee-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="13cee-163">Document.</span></span> <span data-ttu-id="13cee-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="13cee-164">See note.</span></span>|  
|<span data-ttu-id="13cee-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="13cee-165">RichEdit20A</span></span>|<span data-ttu-id="13cee-166">Document</span><span class="sxs-lookup"><span data-stu-id="13cee-166">Document</span></span>|  
|<span data-ttu-id="13cee-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="13cee-167">RichEdit20W</span></span>|<span data-ttu-id="13cee-168">Document</span><span class="sxs-lookup"><span data-stu-id="13cee-168">Document</span></span>|  
|<span data-ttu-id="13cee-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="13cee-169">RichEdit50W</span></span>|<span data-ttu-id="13cee-170">Document</span><span class="sxs-lookup"><span data-stu-id="13cee-170">Document</span></span>|  
|<span data-ttu-id="13cee-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="13cee-171">ScrollBar</span></span>|<span data-ttu-id="13cee-172">Slider</span><span class="sxs-lookup"><span data-stu-id="13cee-172">Slider</span></span>|  
|<span data-ttu-id="13cee-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="13cee-173">msctls_trackbar32</span></span>|<span data-ttu-id="13cee-174">Slider</span><span class="sxs-lookup"><span data-stu-id="13cee-174">Slider</span></span>|  
|<span data-ttu-id="13cee-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="13cee-175">msctls_updown32</span></span>|<span data-ttu-id="13cee-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="13cee-176">Spinner</span></span>|  
|<span data-ttu-id="13cee-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="13cee-177">msctls_statusbar32</span></span>|<span data-ttu-id="13cee-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="13cee-178">StatusBar</span></span>|  
|<span data-ttu-id="13cee-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="13cee-179">SysTabControl32</span></span>|<span data-ttu-id="13cee-180">Вкладка</span><span class="sxs-lookup"><span data-stu-id="13cee-180">Tab</span></span>|  
|<span data-ttu-id="13cee-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="13cee-181">SysTabControl32</span></span>|<span data-ttu-id="13cee-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="13cee-182">TabItem</span></span>|  
|<span data-ttu-id="13cee-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-183">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="13cee-184">ToolBar</span></span>|  
|<span data-ttu-id="13cee-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-185">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="13cee-186">MenuItem</span></span>|  
|<span data-ttu-id="13cee-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-187">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-188">Button</span></span>|  
|<span data-ttu-id="13cee-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-189">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="13cee-190">CheckBox</span></span>|  
|<span data-ttu-id="13cee-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-191">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="13cee-192">RadioButton</span></span>|  
|<span data-ttu-id="13cee-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-193">ToolbarWindow32</span></span>|<span data-ttu-id="13cee-194">Separator</span><span class="sxs-lookup"><span data-stu-id="13cee-194">Separator</span></span>|  
|<span data-ttu-id="13cee-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="13cee-195">tooltips_class32</span></span>|<span data-ttu-id="13cee-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="13cee-196">ToolTip</span></span>|  
|<span data-ttu-id="13cee-197">#32774</span><span class="sxs-lookup"><span data-stu-id="13cee-197">#32774</span></span>|<span data-ttu-id="13cee-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="13cee-198">ToolTip</span></span>|  
|<span data-ttu-id="13cee-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="13cee-199">ReBarWindow32</span></span>|<span data-ttu-id="13cee-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="13cee-200">Toolbar</span></span>|  
|<span data-ttu-id="13cee-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="13cee-201">SysTreeView32</span></span>|<span data-ttu-id="13cee-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="13cee-202">Tree</span></span>|  
|<span data-ttu-id="13cee-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="13cee-203">SysTreeView32</span></span>|<span data-ttu-id="13cee-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="13cee-204">TreeItem</span></span>|  
  
 <span data-ttu-id="13cee-205">**Примечание.** Элемент управления RichEdit поддерживается только для версий, поставляемых в составе [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (в RichEd20.dll версии 3.1 и более поздних версий и MsftEdit.dll версии 4.1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="13cee-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="13cee-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="13cee-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="13cee-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="13cee-207">Class name</span></span>|<span data-ttu-id="13cee-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="13cee-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="13cee-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="13cee-209">SysAnimate32</span></span>|<span data-ttu-id="13cee-210">Изображение</span><span class="sxs-lookup"><span data-stu-id="13cee-210">Image</span></span>|  
|<span data-ttu-id="13cee-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="13cee-211">SysPager</span></span>|<span data-ttu-id="13cee-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="13cee-212">Spinner</span></span>|  
|<span data-ttu-id="13cee-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="13cee-213">SysDateTimePick32</span></span>|<span data-ttu-id="13cee-214">Другой</span><span class="sxs-lookup"><span data-stu-id="13cee-214">Custom</span></span>|  
|<span data-ttu-id="13cee-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="13cee-215">SysMonthCal32</span></span>|<span data-ttu-id="13cee-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="13cee-216">Calendar</span></span>|  
|<span data-ttu-id="13cee-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="13cee-217">MS_WINNOTE</span></span>|<span data-ttu-id="13cee-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="13cee-218">Tooltip</span></span>|  
|<span data-ttu-id="13cee-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="13cee-219">VBBubble</span></span>|<span data-ttu-id="13cee-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="13cee-220">Tooltip</span></span>|  
|<span data-ttu-id="13cee-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="13cee-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="13cee-222">Slider</span><span class="sxs-lookup"><span data-stu-id="13cee-222">Slider</span></span>|  
|<span data-ttu-id="13cee-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="13cee-223">SuperGrid</span></span>|<span data-ttu-id="13cee-224">Другой</span><span class="sxs-lookup"><span data-stu-id="13cee-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="13cee-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13cee-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="13cee-226">Элементы управления[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="13cee-226">[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="13cee-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="13cee-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="13cee-228">Как правило, элементы управления [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] , которые являются управляемыми оболочками для общих элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] , поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cee-228">Typically, [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="13cee-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="13cee-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="13cee-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="13cee-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="13cee-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="13cee-231">Button</span></span>|  
|<span data-ttu-id="13cee-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="13cee-232">CheckBox</span></span>|  
|<span data-ttu-id="13cee-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="13cee-233">CheckedListBox</span></span>|  
|<span data-ttu-id="13cee-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-234">ColorDialog</span></span>|  
|<span data-ttu-id="13cee-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="13cee-235">ComboBox</span></span>|  
|<span data-ttu-id="13cee-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="13cee-236">FolderBrowser</span></span>|  
|<span data-ttu-id="13cee-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-237">FontDialog</span></span>|  
|<span data-ttu-id="13cee-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="13cee-238">GroupBox</span></span>|  
|<span data-ttu-id="13cee-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="13cee-239">HscrollBar</span></span>|  
|<span data-ttu-id="13cee-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="13cee-240">ImageList</span></span>|  
|<span data-ttu-id="13cee-241">Метка</span><span class="sxs-lookup"><span data-stu-id="13cee-241">Label</span></span>|  
|<span data-ttu-id="13cee-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="13cee-242">ListBox</span></span>|  
|<span data-ttu-id="13cee-243">ListView</span><span class="sxs-lookup"><span data-stu-id="13cee-243">ListView</span></span>|  
|<span data-ttu-id="13cee-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="13cee-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="13cee-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="13cee-245">MonthCalendar</span></span>|  
|<span data-ttu-id="13cee-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="13cee-246">NotifyIcon</span></span>|  
|<span data-ttu-id="13cee-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="13cee-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="13cee-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-249">PrintDialog</span></span>|  
|<span data-ttu-id="13cee-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="13cee-250">ProgressBar</span></span>|  
|<span data-ttu-id="13cee-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="13cee-251">RadioButton</span></span>|  
|<span data-ttu-id="13cee-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="13cee-252">RichTextBox</span></span>|  
|<span data-ttu-id="13cee-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="13cee-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="13cee-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="13cee-254">ScrollableControl</span></span>|  
|<span data-ttu-id="13cee-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="13cee-255">SoundPlayer</span></span>|  
|<span data-ttu-id="13cee-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="13cee-256">StatusBar</span></span>|  
|<span data-ttu-id="13cee-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="13cee-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="13cee-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="13cee-258">TextBox</span></span>|  
|<span data-ttu-id="13cee-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="13cee-259">Timer</span></span>|  
|<span data-ttu-id="13cee-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="13cee-260">Toolbar</span></span>|  
|<span data-ttu-id="13cee-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="13cee-261">ToolTip</span></span>|  
|<span data-ttu-id="13cee-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="13cee-262">TrackBar</span></span>|  
|<span data-ttu-id="13cee-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="13cee-263">TreeView</span></span>|  
|<span data-ttu-id="13cee-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="13cee-264">VscrollBar</span></span>|  
|<span data-ttu-id="13cee-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="13cee-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="13cee-266">Следующие элементы управления предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через их поддержку [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cee-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="13cee-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="13cee-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="13cee-268">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="13cee-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="13cee-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="13cee-269">BindingSource</span></span>|  
|<span data-ttu-id="13cee-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="13cee-270">DataGrid</span></span>|  
|<span data-ttu-id="13cee-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="13cee-271">DataGridView</span></span>|  
|<span data-ttu-id="13cee-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="13cee-272">DataNavigator</span></span>|  
|<span data-ttu-id="13cee-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="13cee-273">DomainUpDown</span></span>|  
|<span data-ttu-id="13cee-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="13cee-274">ErrorProvider</span></span>|  
|<span data-ttu-id="13cee-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="13cee-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="13cee-276">Form</span><span class="sxs-lookup"><span data-stu-id="13cee-276">Form</span></span>|  
|<span data-ttu-id="13cee-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="13cee-277">LinkLabel</span></span>|  
|<span data-ttu-id="13cee-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="13cee-278">HelpProvider</span></span>|  
|<span data-ttu-id="13cee-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="13cee-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="13cee-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="13cee-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="13cee-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="13cee-281">NumericUpDown</span></span>|  
|<span data-ttu-id="13cee-282">Panel</span><span class="sxs-lookup"><span data-stu-id="13cee-282">Panel</span></span>|  
|<span data-ttu-id="13cee-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="13cee-283">PictureBox</span></span>|  
|<span data-ttu-id="13cee-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="13cee-284">PrintDocument</span></span>|  
|<span data-ttu-id="13cee-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="13cee-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="13cee-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="13cee-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="13cee-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="13cee-287">PropertyGrid</span></span>|  
|<span data-ttu-id="13cee-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="13cee-288">UserControl</span></span>|  
|<span data-ttu-id="13cee-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="13cee-289">ToolStrip</span></span>|  
|<span data-ttu-id="13cee-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="13cee-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="13cee-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="13cee-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="13cee-292">Разделитель</span><span class="sxs-lookup"><span data-stu-id="13cee-292">Splitter</span></span>|  
|<span data-ttu-id="13cee-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="13cee-293">RaftingContainer</span></span>|  
|<span data-ttu-id="13cee-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="13cee-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13cee-295">См. также</span><span class="sxs-lookup"><span data-stu-id="13cee-295">See Also</span></span>  
 [<span data-ttu-id="13cee-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="13cee-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
