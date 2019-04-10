---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 3fde9779205ea7d0902ddd99ed192f097a159d2c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221483"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="1033a-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="1033a-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="1033a-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="1033a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1033a-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="1033a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="1033a-105">В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1033a-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="1033a-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="1033a-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="1033a-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1033a-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="1033a-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1033a-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="1033a-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="1033a-109">Win32 Controls</span></span>  
 <span data-ttu-id="1033a-110">Большинство элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="1033a-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="1033a-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1033a-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="1033a-112">Полная поддержка предоставляется только для элементов управления с версии 6 ComCtrl32.dll (доступной в [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="1033a-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="1033a-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="1033a-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="1033a-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="1033a-114">Class name</span></span>|<span data-ttu-id="1033a-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="1033a-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="1033a-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-116">Button</span></span>|<span data-ttu-id="1033a-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-117">Button</span></span>|  
|<span data-ttu-id="1033a-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-118">Button</span></span>|<span data-ttu-id="1033a-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="1033a-119">RadioButton</span></span>|  
|<span data-ttu-id="1033a-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-120">Button</span></span>|<span data-ttu-id="1033a-121">Группа</span><span class="sxs-lookup"><span data-stu-id="1033a-121">Group</span></span>|  
|<span data-ttu-id="1033a-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-122">Button</span></span>|<span data-ttu-id="1033a-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="1033a-123">CheckBox</span></span>|  
|<span data-ttu-id="1033a-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-124">Button</span></span>|<span data-ttu-id="1033a-125">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="1033a-125">Hyperlink</span></span>|  
|<span data-ttu-id="1033a-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-126">Button</span></span>|<span data-ttu-id="1033a-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="1033a-127">SplitButton</span></span>|  
|<span data-ttu-id="1033a-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-128">Button</span></span>|<span data-ttu-id="1033a-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="1033a-129">CheckBox</span></span>|  
|<span data-ttu-id="1033a-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="1033a-130">ComboBoxEx32</span></span>|<span data-ttu-id="1033a-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="1033a-131">ComboBox</span></span>|  
|<span data-ttu-id="1033a-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="1033a-132">ComboBox</span></span>|<span data-ttu-id="1033a-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="1033a-133">ComboBox</span></span>|  
|<span data-ttu-id="1033a-134">Правка</span><span class="sxs-lookup"><span data-stu-id="1033a-134">Edit</span></span>|<span data-ttu-id="1033a-135">Document</span><span class="sxs-lookup"><span data-stu-id="1033a-135">Document</span></span>|  
|<span data-ttu-id="1033a-136">Правка</span><span class="sxs-lookup"><span data-stu-id="1033a-136">Edit</span></span>|<span data-ttu-id="1033a-137">Правка</span><span class="sxs-lookup"><span data-stu-id="1033a-137">Edit</span></span>|  
|<span data-ttu-id="1033a-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="1033a-138">SysLink</span></span>|<span data-ttu-id="1033a-139">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="1033a-139">Hyperlink</span></span>|  
|<span data-ttu-id="1033a-140">Static</span><span class="sxs-lookup"><span data-stu-id="1033a-140">Static</span></span>|<span data-ttu-id="1033a-141">Текста</span><span class="sxs-lookup"><span data-stu-id="1033a-141">Text</span></span>|  
|<span data-ttu-id="1033a-142">Static</span><span class="sxs-lookup"><span data-stu-id="1033a-142">Static</span></span>|<span data-ttu-id="1033a-143">Изображение</span><span class="sxs-lookup"><span data-stu-id="1033a-143">Image</span></span>|  
|<span data-ttu-id="1033a-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="1033a-144">SysIPAddress32</span></span>|<span data-ttu-id="1033a-145">Другой</span><span class="sxs-lookup"><span data-stu-id="1033a-145">Custom</span></span>|  
|<span data-ttu-id="1033a-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="1033a-146">SysHeader32</span></span>|<span data-ttu-id="1033a-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="1033a-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="1033a-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="1033a-148">SysListView32</span></span>|<span data-ttu-id="1033a-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="1033a-149">DataGrid</span></span>|  
|<span data-ttu-id="1033a-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="1033a-150">SysListView32</span></span>|<span data-ttu-id="1033a-151">Список</span><span class="sxs-lookup"><span data-stu-id="1033a-151">List</span></span>|  
|<span data-ttu-id="1033a-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="1033a-152">ListBox</span></span>|<span data-ttu-id="1033a-153">Список</span><span class="sxs-lookup"><span data-stu-id="1033a-153">List</span></span>|  
|<span data-ttu-id="1033a-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="1033a-154">ListBox</span></span>|<span data-ttu-id="1033a-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="1033a-155">ListItem</span></span>|  
|<span data-ttu-id="1033a-156">#32768</span><span class="sxs-lookup"><span data-stu-id="1033a-156">#32768</span></span>|<span data-ttu-id="1033a-157">Меню</span><span class="sxs-lookup"><span data-stu-id="1033a-157">Menu</span></span>|  
|<span data-ttu-id="1033a-158">#32768</span><span class="sxs-lookup"><span data-stu-id="1033a-158">#32768</span></span>|<span data-ttu-id="1033a-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="1033a-159">MenuItem</span></span>|  
|<span data-ttu-id="1033a-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="1033a-160">msctls_progress32</span></span>|<span data-ttu-id="1033a-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="1033a-161">ProgressBar</span></span>|  
|<span data-ttu-id="1033a-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="1033a-162">RichEdit</span></span>|<span data-ttu-id="1033a-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="1033a-163">Document.</span></span> <span data-ttu-id="1033a-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="1033a-164">See note.</span></span>|  
|<span data-ttu-id="1033a-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="1033a-165">RichEdit20A</span></span>|<span data-ttu-id="1033a-166">Document</span><span class="sxs-lookup"><span data-stu-id="1033a-166">Document</span></span>|  
|<span data-ttu-id="1033a-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="1033a-167">RichEdit20W</span></span>|<span data-ttu-id="1033a-168">Document</span><span class="sxs-lookup"><span data-stu-id="1033a-168">Document</span></span>|  
|<span data-ttu-id="1033a-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="1033a-169">RichEdit50W</span></span>|<span data-ttu-id="1033a-170">Document</span><span class="sxs-lookup"><span data-stu-id="1033a-170">Document</span></span>|  
|<span data-ttu-id="1033a-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="1033a-171">ScrollBar</span></span>|<span data-ttu-id="1033a-172">Slider</span><span class="sxs-lookup"><span data-stu-id="1033a-172">Slider</span></span>|  
|<span data-ttu-id="1033a-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="1033a-173">msctls_trackbar32</span></span>|<span data-ttu-id="1033a-174">Slider</span><span class="sxs-lookup"><span data-stu-id="1033a-174">Slider</span></span>|  
|<span data-ttu-id="1033a-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="1033a-175">msctls_updown32</span></span>|<span data-ttu-id="1033a-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="1033a-176">Spinner</span></span>|  
|<span data-ttu-id="1033a-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="1033a-177">msctls_statusbar32</span></span>|<span data-ttu-id="1033a-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="1033a-178">StatusBar</span></span>|  
|<span data-ttu-id="1033a-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="1033a-179">SysTabControl32</span></span>|<span data-ttu-id="1033a-180">Tab</span><span class="sxs-lookup"><span data-stu-id="1033a-180">Tab</span></span>|  
|<span data-ttu-id="1033a-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="1033a-181">SysTabControl32</span></span>|<span data-ttu-id="1033a-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="1033a-182">TabItem</span></span>|  
|<span data-ttu-id="1033a-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-183">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="1033a-184">ToolBar</span></span>|  
|<span data-ttu-id="1033a-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-185">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="1033a-186">MenuItem</span></span>|  
|<span data-ttu-id="1033a-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-187">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-188">Button</span></span>|  
|<span data-ttu-id="1033a-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-189">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="1033a-190">CheckBox</span></span>|  
|<span data-ttu-id="1033a-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-191">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="1033a-192">RadioButton</span></span>|  
|<span data-ttu-id="1033a-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-193">ToolbarWindow32</span></span>|<span data-ttu-id="1033a-194">Separator</span><span class="sxs-lookup"><span data-stu-id="1033a-194">Separator</span></span>|  
|<span data-ttu-id="1033a-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="1033a-195">tooltips_class32</span></span>|<span data-ttu-id="1033a-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="1033a-196">ToolTip</span></span>|  
|<span data-ttu-id="1033a-197">#32774</span><span class="sxs-lookup"><span data-stu-id="1033a-197">#32774</span></span>|<span data-ttu-id="1033a-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="1033a-198">ToolTip</span></span>|  
|<span data-ttu-id="1033a-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="1033a-199">ReBarWindow32</span></span>|<span data-ttu-id="1033a-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="1033a-200">Toolbar</span></span>|  
|<span data-ttu-id="1033a-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="1033a-201">SysTreeView32</span></span>|<span data-ttu-id="1033a-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="1033a-202">Tree</span></span>|  
|<span data-ttu-id="1033a-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="1033a-203">SysTreeView32</span></span>|<span data-ttu-id="1033a-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="1033a-204">TreeItem</span></span>|  
  
 <span data-ttu-id="1033a-205">**Примечание.** Элемент управления RichEdit поддерживается только для версий, поставляемых в составе [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (в RichEd20.dll версии 3.1 и более поздних версий и MsftEdit.dll версии 4.1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="1033a-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="1033a-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1033a-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="1033a-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="1033a-207">Class name</span></span>|<span data-ttu-id="1033a-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="1033a-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="1033a-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="1033a-209">SysAnimate32</span></span>|<span data-ttu-id="1033a-210">Изображение</span><span class="sxs-lookup"><span data-stu-id="1033a-210">Image</span></span>|  
|<span data-ttu-id="1033a-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="1033a-211">SysPager</span></span>|<span data-ttu-id="1033a-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="1033a-212">Spinner</span></span>|  
|<span data-ttu-id="1033a-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="1033a-213">SysDateTimePick32</span></span>|<span data-ttu-id="1033a-214">Другой</span><span class="sxs-lookup"><span data-stu-id="1033a-214">Custom</span></span>|  
|<span data-ttu-id="1033a-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="1033a-215">SysMonthCal32</span></span>|<span data-ttu-id="1033a-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="1033a-216">Calendar</span></span>|  
|<span data-ttu-id="1033a-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="1033a-217">MS_WINNOTE</span></span>|<span data-ttu-id="1033a-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="1033a-218">Tooltip</span></span>|  
|<span data-ttu-id="1033a-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="1033a-219">VBBubble</span></span>|<span data-ttu-id="1033a-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="1033a-220">Tooltip</span></span>|  
|<span data-ttu-id="1033a-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="1033a-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="1033a-222">Slider</span><span class="sxs-lookup"><span data-stu-id="1033a-222">Slider</span></span>|  
|<span data-ttu-id="1033a-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="1033a-223">SuperGrid</span></span>|<span data-ttu-id="1033a-224">Другой</span><span class="sxs-lookup"><span data-stu-id="1033a-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="1033a-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1033a-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="1033a-226">Элементы управления Windows Forms предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="1033a-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="1033a-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1033a-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="1033a-228">Как правило, элементы управления Windows Forms, которые являются управляемыми оболочками для [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] поддерживаются стандартные элементы управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1033a-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="1033a-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="1033a-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="1033a-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="1033a-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="1033a-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="1033a-231">Button</span></span>|  
|<span data-ttu-id="1033a-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="1033a-232">CheckBox</span></span>|  
|<span data-ttu-id="1033a-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="1033a-233">CheckedListBox</span></span>|  
|<span data-ttu-id="1033a-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-234">ColorDialog</span></span>|  
|<span data-ttu-id="1033a-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="1033a-235">ComboBox</span></span>|  
|<span data-ttu-id="1033a-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="1033a-236">FolderBrowser</span></span>|  
|<span data-ttu-id="1033a-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-237">FontDialog</span></span>|  
|<span data-ttu-id="1033a-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="1033a-238">GroupBox</span></span>|  
|<span data-ttu-id="1033a-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="1033a-239">HscrollBar</span></span>|  
|<span data-ttu-id="1033a-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="1033a-240">ImageList</span></span>|  
|<span data-ttu-id="1033a-241">Метка</span><span class="sxs-lookup"><span data-stu-id="1033a-241">Label</span></span>|  
|<span data-ttu-id="1033a-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="1033a-242">ListBox</span></span>|  
|<span data-ttu-id="1033a-243">ListView</span><span class="sxs-lookup"><span data-stu-id="1033a-243">ListView</span></span>|  
|<span data-ttu-id="1033a-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1033a-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="1033a-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="1033a-245">MonthCalendar</span></span>|  
|<span data-ttu-id="1033a-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="1033a-246">NotifyIcon</span></span>|  
|<span data-ttu-id="1033a-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="1033a-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="1033a-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-249">PrintDialog</span></span>|  
|<span data-ttu-id="1033a-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="1033a-250">ProgressBar</span></span>|  
|<span data-ttu-id="1033a-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="1033a-251">RadioButton</span></span>|  
|<span data-ttu-id="1033a-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="1033a-252">RichTextBox</span></span>|  
|<span data-ttu-id="1033a-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="1033a-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="1033a-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="1033a-254">ScrollableControl</span></span>|  
|<span data-ttu-id="1033a-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="1033a-255">SoundPlayer</span></span>|  
|<span data-ttu-id="1033a-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="1033a-256">StatusBar</span></span>|  
|<span data-ttu-id="1033a-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="1033a-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="1033a-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="1033a-258">TextBox</span></span>|  
|<span data-ttu-id="1033a-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="1033a-259">Timer</span></span>|  
|<span data-ttu-id="1033a-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="1033a-260">Toolbar</span></span>|  
|<span data-ttu-id="1033a-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="1033a-261">ToolTip</span></span>|  
|<span data-ttu-id="1033a-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="1033a-262">TrackBar</span></span>|  
|<span data-ttu-id="1033a-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="1033a-263">TreeView</span></span>|  
|<span data-ttu-id="1033a-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="1033a-264">VscrollBar</span></span>|  
|<span data-ttu-id="1033a-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="1033a-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="1033a-266">Следующие элементы управления предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через их поддержку [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1033a-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="1033a-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="1033a-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="1033a-268">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="1033a-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="1033a-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="1033a-269">BindingSource</span></span>|  
|<span data-ttu-id="1033a-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="1033a-270">DataGrid</span></span>|  
|<span data-ttu-id="1033a-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="1033a-271">DataGridView</span></span>|  
|<span data-ttu-id="1033a-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="1033a-272">DataNavigator</span></span>|  
|<span data-ttu-id="1033a-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="1033a-273">DomainUpDown</span></span>|  
|<span data-ttu-id="1033a-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="1033a-274">ErrorProvider</span></span>|  
|<span data-ttu-id="1033a-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1033a-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="1033a-276">Form</span><span class="sxs-lookup"><span data-stu-id="1033a-276">Form</span></span>|  
|<span data-ttu-id="1033a-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="1033a-277">LinkLabel</span></span>|  
|<span data-ttu-id="1033a-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="1033a-278">HelpProvider</span></span>|  
|<span data-ttu-id="1033a-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="1033a-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="1033a-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="1033a-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="1033a-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="1033a-281">NumericUpDown</span></span>|  
|<span data-ttu-id="1033a-282">Panel</span><span class="sxs-lookup"><span data-stu-id="1033a-282">Panel</span></span>|  
|<span data-ttu-id="1033a-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="1033a-283">PictureBox</span></span>|  
|<span data-ttu-id="1033a-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="1033a-284">PrintDocument</span></span>|  
|<span data-ttu-id="1033a-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="1033a-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="1033a-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="1033a-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="1033a-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="1033a-287">PropertyGrid</span></span>|  
|<span data-ttu-id="1033a-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="1033a-288">UserControl</span></span>|  
|<span data-ttu-id="1033a-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1033a-289">ToolStrip</span></span>|  
|<span data-ttu-id="1033a-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1033a-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="1033a-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="1033a-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="1033a-292">Разделитель</span><span class="sxs-lookup"><span data-stu-id="1033a-292">Splitter</span></span>|  
|<span data-ttu-id="1033a-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="1033a-293">RaftingContainer</span></span>|  
|<span data-ttu-id="1033a-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="1033a-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1033a-295">См. также</span><span class="sxs-lookup"><span data-stu-id="1033a-295">See also</span></span>

- [<span data-ttu-id="1033a-296">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1033a-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
