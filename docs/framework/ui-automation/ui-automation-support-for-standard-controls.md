---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 641fc3f8dfca3ff6506354c076b98cc88073a1b7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802120"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="d1e31-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="d1e31-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="d1e31-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="d1e31-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d1e31-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d1e31-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d1e31-105">В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1e31-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="d1e31-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="d1e31-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="d1e31-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e31-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d1e31-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e31-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="d1e31-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="d1e31-109">Win32 Controls</span></span>  
 <span data-ttu-id="d1e31-110">Большинство элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="d1e31-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d1e31-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1e31-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d1e31-112">Полная поддержка предоставляется только для элементов управления с версии 6 ComCtrl32.dll (доступной в [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] и более поздних версиях).</span><span class="sxs-lookup"><span data-stu-id="d1e31-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="d1e31-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="d1e31-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d1e31-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="d1e31-114">Class name</span></span>|<span data-ttu-id="d1e31-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="d1e31-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d1e31-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-116">Button</span></span>|<span data-ttu-id="d1e31-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-117">Button</span></span>|  
|<span data-ttu-id="d1e31-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-118">Button</span></span>|<span data-ttu-id="d1e31-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d1e31-119">RadioButton</span></span>|  
|<span data-ttu-id="d1e31-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-120">Button</span></span>|<span data-ttu-id="d1e31-121">Группа</span><span class="sxs-lookup"><span data-stu-id="d1e31-121">Group</span></span>|  
|<span data-ttu-id="d1e31-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-122">Button</span></span>|<span data-ttu-id="d1e31-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-123">CheckBox</span></span>|  
|<span data-ttu-id="d1e31-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-124">Button</span></span>|<span data-ttu-id="d1e31-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="d1e31-125">Hyperlink</span></span>|  
|<span data-ttu-id="d1e31-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-126">Button</span></span>|<span data-ttu-id="d1e31-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="d1e31-127">SplitButton</span></span>|  
|<span data-ttu-id="d1e31-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-128">Button</span></span>|<span data-ttu-id="d1e31-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-129">CheckBox</span></span>|  
|<span data-ttu-id="d1e31-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="d1e31-130">ComboBoxEx32</span></span>|<span data-ttu-id="d1e31-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-131">ComboBox</span></span>|  
|<span data-ttu-id="d1e31-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-132">ComboBox</span></span>|<span data-ttu-id="d1e31-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-133">ComboBox</span></span>|  
|<span data-ttu-id="d1e31-134">Правка</span><span class="sxs-lookup"><span data-stu-id="d1e31-134">Edit</span></span>|<span data-ttu-id="d1e31-135">Document</span><span class="sxs-lookup"><span data-stu-id="d1e31-135">Document</span></span>|  
|<span data-ttu-id="d1e31-136">Правка</span><span class="sxs-lookup"><span data-stu-id="d1e31-136">Edit</span></span>|<span data-ttu-id="d1e31-137">Правка</span><span class="sxs-lookup"><span data-stu-id="d1e31-137">Edit</span></span>|  
|<span data-ttu-id="d1e31-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="d1e31-138">SysLink</span></span>|<span data-ttu-id="d1e31-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="d1e31-139">Hyperlink</span></span>|  
|<span data-ttu-id="d1e31-140">Статические</span><span class="sxs-lookup"><span data-stu-id="d1e31-140">Static</span></span>|<span data-ttu-id="d1e31-141">Текст</span><span class="sxs-lookup"><span data-stu-id="d1e31-141">Text</span></span>|  
|<span data-ttu-id="d1e31-142">Статические</span><span class="sxs-lookup"><span data-stu-id="d1e31-142">Static</span></span>|<span data-ttu-id="d1e31-143">Изображение</span><span class="sxs-lookup"><span data-stu-id="d1e31-143">Image</span></span>|  
|<span data-ttu-id="d1e31-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="d1e31-144">SysIPAddress32</span></span>|<span data-ttu-id="d1e31-145">Другой</span><span class="sxs-lookup"><span data-stu-id="d1e31-145">Custom</span></span>|  
|<span data-ttu-id="d1e31-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="d1e31-146">SysHeader32</span></span>|<span data-ttu-id="d1e31-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="d1e31-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d1e31-148">SysListView32</span></span>|<span data-ttu-id="d1e31-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d1e31-149">DataGrid</span></span>|  
|<span data-ttu-id="d1e31-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d1e31-150">SysListView32</span></span>|<span data-ttu-id="d1e31-151">Список</span><span class="sxs-lookup"><span data-stu-id="d1e31-151">List</span></span>|  
|<span data-ttu-id="d1e31-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-152">ListBox</span></span>|<span data-ttu-id="d1e31-153">Список</span><span class="sxs-lookup"><span data-stu-id="d1e31-153">List</span></span>|  
|<span data-ttu-id="d1e31-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-154">ListBox</span></span>|<span data-ttu-id="d1e31-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-155">ListItem</span></span>|  
|<span data-ttu-id="d1e31-156">#32768</span><span class="sxs-lookup"><span data-stu-id="d1e31-156">#32768</span></span>|<span data-ttu-id="d1e31-157">Меню</span><span class="sxs-lookup"><span data-stu-id="d1e31-157">Menu</span></span>|  
|<span data-ttu-id="d1e31-158">#32768</span><span class="sxs-lookup"><span data-stu-id="d1e31-158">#32768</span></span>|<span data-ttu-id="d1e31-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-159">MenuItem</span></span>|  
|<span data-ttu-id="d1e31-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="d1e31-160">msctls_progress32</span></span>|<span data-ttu-id="d1e31-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-161">ProgressBar</span></span>|  
|<span data-ttu-id="d1e31-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="d1e31-162">RichEdit</span></span>|<span data-ttu-id="d1e31-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="d1e31-163">Document.</span></span> <span data-ttu-id="d1e31-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="d1e31-164">See note.</span></span>|  
|<span data-ttu-id="d1e31-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="d1e31-165">RichEdit20A</span></span>|<span data-ttu-id="d1e31-166">Document</span><span class="sxs-lookup"><span data-stu-id="d1e31-166">Document</span></span>|  
|<span data-ttu-id="d1e31-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="d1e31-167">RichEdit20W</span></span>|<span data-ttu-id="d1e31-168">Document</span><span class="sxs-lookup"><span data-stu-id="d1e31-168">Document</span></span>|  
|<span data-ttu-id="d1e31-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="d1e31-169">RichEdit50W</span></span>|<span data-ttu-id="d1e31-170">Document</span><span class="sxs-lookup"><span data-stu-id="d1e31-170">Document</span></span>|  
|<span data-ttu-id="d1e31-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-171">ScrollBar</span></span>|<span data-ttu-id="d1e31-172">Slider</span><span class="sxs-lookup"><span data-stu-id="d1e31-172">Slider</span></span>|  
|<span data-ttu-id="d1e31-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="d1e31-173">msctls_trackbar32</span></span>|<span data-ttu-id="d1e31-174">Slider</span><span class="sxs-lookup"><span data-stu-id="d1e31-174">Slider</span></span>|  
|<span data-ttu-id="d1e31-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="d1e31-175">msctls_updown32</span></span>|<span data-ttu-id="d1e31-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="d1e31-176">Spinner</span></span>|  
|<span data-ttu-id="d1e31-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="d1e31-177">msctls_statusbar32</span></span>|<span data-ttu-id="d1e31-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-178">StatusBar</span></span>|  
|<span data-ttu-id="d1e31-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d1e31-179">SysTabControl32</span></span>|<span data-ttu-id="d1e31-180">Вкладка</span><span class="sxs-lookup"><span data-stu-id="d1e31-180">Tab</span></span>|  
|<span data-ttu-id="d1e31-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d1e31-181">SysTabControl32</span></span>|<span data-ttu-id="d1e31-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-182">TabItem</span></span>|  
|<span data-ttu-id="d1e31-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-183">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-184">ToolBar</span></span>|  
|<span data-ttu-id="d1e31-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-185">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-186">MenuItem</span></span>|  
|<span data-ttu-id="d1e31-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-187">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-188">Button</span></span>|  
|<span data-ttu-id="d1e31-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-189">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-190">CheckBox</span></span>|  
|<span data-ttu-id="d1e31-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-191">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d1e31-192">RadioButton</span></span>|  
|<span data-ttu-id="d1e31-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-193">ToolbarWindow32</span></span>|<span data-ttu-id="d1e31-194">Separator</span><span class="sxs-lookup"><span data-stu-id="d1e31-194">Separator</span></span>|  
|<span data-ttu-id="d1e31-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="d1e31-195">tooltips_class32</span></span>|<span data-ttu-id="d1e31-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d1e31-196">ToolTip</span></span>|  
|<span data-ttu-id="d1e31-197">#32774</span><span class="sxs-lookup"><span data-stu-id="d1e31-197">#32774</span></span>|<span data-ttu-id="d1e31-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d1e31-198">ToolTip</span></span>|  
|<span data-ttu-id="d1e31-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="d1e31-199">ReBarWindow32</span></span>|<span data-ttu-id="d1e31-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="d1e31-200">Toolbar</span></span>|  
|<span data-ttu-id="d1e31-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d1e31-201">SysTreeView32</span></span>|<span data-ttu-id="d1e31-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="d1e31-202">Tree</span></span>|  
|<span data-ttu-id="d1e31-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d1e31-203">SysTreeView32</span></span>|<span data-ttu-id="d1e31-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="d1e31-204">TreeItem</span></span>|  
  
 <span data-ttu-id="d1e31-205">**Примечание.** Элемент управления RichEdit поддерживается только для версий, поставляемых в составе [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (в RichEd20.dll версии 3.1 и более поздних версий и MsftEdit.dll версии 4.1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="d1e31-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="d1e31-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d1e31-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="d1e31-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="d1e31-207">Class name</span></span>|<span data-ttu-id="d1e31-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="d1e31-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d1e31-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="d1e31-209">SysAnimate32</span></span>|<span data-ttu-id="d1e31-210">Изображение</span><span class="sxs-lookup"><span data-stu-id="d1e31-210">Image</span></span>|  
|<span data-ttu-id="d1e31-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="d1e31-211">SysPager</span></span>|<span data-ttu-id="d1e31-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="d1e31-212">Spinner</span></span>|  
|<span data-ttu-id="d1e31-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="d1e31-213">SysDateTimePick32</span></span>|<span data-ttu-id="d1e31-214">Другой</span><span class="sxs-lookup"><span data-stu-id="d1e31-214">Custom</span></span>|  
|<span data-ttu-id="d1e31-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="d1e31-215">SysMonthCal32</span></span>|<span data-ttu-id="d1e31-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="d1e31-216">Calendar</span></span>|  
|<span data-ttu-id="d1e31-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="d1e31-217">MS_WINNOTE</span></span>|<span data-ttu-id="d1e31-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d1e31-218">Tooltip</span></span>|  
|<span data-ttu-id="d1e31-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="d1e31-219">VBBubble</span></span>|<span data-ttu-id="d1e31-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d1e31-220">Tooltip</span></span>|  
|<span data-ttu-id="d1e31-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="d1e31-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="d1e31-222">Slider</span><span class="sxs-lookup"><span data-stu-id="d1e31-222">Slider</span></span>|  
|<span data-ttu-id="d1e31-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="d1e31-223">SuperGrid</span></span>|<span data-ttu-id="d1e31-224">Другой</span><span class="sxs-lookup"><span data-stu-id="d1e31-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="d1e31-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1e31-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="d1e31-226">Элементы управления Windows Forms предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="d1e31-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d1e31-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1e31-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d1e31-228">Как правило, элементы управления Windows Forms, которые являются управляемыми оболочками для [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] поддерживаются стандартные элементы управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e31-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d1e31-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="d1e31-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d1e31-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="d1e31-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="d1e31-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d1e31-231">Button</span></span>|  
|<span data-ttu-id="d1e31-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-232">CheckBox</span></span>|  
|<span data-ttu-id="d1e31-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-233">CheckedListBox</span></span>|  
|<span data-ttu-id="d1e31-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-234">ColorDialog</span></span>|  
|<span data-ttu-id="d1e31-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-235">ComboBox</span></span>|  
|<span data-ttu-id="d1e31-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="d1e31-236">FolderBrowser</span></span>|  
|<span data-ttu-id="d1e31-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-237">FontDialog</span></span>|  
|<span data-ttu-id="d1e31-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-238">GroupBox</span></span>|  
|<span data-ttu-id="d1e31-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-239">HscrollBar</span></span>|  
|<span data-ttu-id="d1e31-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="d1e31-240">ImageList</span></span>|  
|<span data-ttu-id="d1e31-241">Метка</span><span class="sxs-lookup"><span data-stu-id="d1e31-241">Label</span></span>|  
|<span data-ttu-id="d1e31-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-242">ListBox</span></span>|  
|<span data-ttu-id="d1e31-243">ListView</span><span class="sxs-lookup"><span data-stu-id="d1e31-243">ListView</span></span>|  
|<span data-ttu-id="d1e31-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d1e31-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="d1e31-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="d1e31-245">MonthCalendar</span></span>|  
|<span data-ttu-id="d1e31-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d1e31-246">NotifyIcon</span></span>|  
|<span data-ttu-id="d1e31-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="d1e31-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="d1e31-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-249">PrintDialog</span></span>|  
|<span data-ttu-id="d1e31-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-250">ProgressBar</span></span>|  
|<span data-ttu-id="d1e31-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d1e31-251">RadioButton</span></span>|  
|<span data-ttu-id="d1e31-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-252">RichTextBox</span></span>|  
|<span data-ttu-id="d1e31-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="d1e31-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="d1e31-254">ScrollableControl</span></span>|  
|<span data-ttu-id="d1e31-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="d1e31-255">SoundPlayer</span></span>|  
|<span data-ttu-id="d1e31-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-256">StatusBar</span></span>|  
|<span data-ttu-id="d1e31-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="d1e31-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="d1e31-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-258">TextBox</span></span>|  
|<span data-ttu-id="d1e31-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="d1e31-259">Timer</span></span>|  
|<span data-ttu-id="d1e31-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-260">Toolbar</span></span>|  
|<span data-ttu-id="d1e31-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d1e31-261">ToolTip</span></span>|  
|<span data-ttu-id="d1e31-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-262">TrackBar</span></span>|  
|<span data-ttu-id="d1e31-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="d1e31-263">TreeView</span></span>|  
|<span data-ttu-id="d1e31-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="d1e31-264">VscrollBar</span></span>|  
|<span data-ttu-id="d1e31-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="d1e31-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="d1e31-266">Следующие элементы управления имеют доступ к [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через их поддержку Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="d1e31-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="d1e31-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="d1e31-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="d1e31-268">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="d1e31-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="d1e31-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="d1e31-269">BindingSource</span></span>|  
|<span data-ttu-id="d1e31-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d1e31-270">DataGrid</span></span>|  
|<span data-ttu-id="d1e31-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="d1e31-271">DataGridView</span></span>|  
|<span data-ttu-id="d1e31-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="d1e31-272">DataNavigator</span></span>|  
|<span data-ttu-id="d1e31-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="d1e31-273">DomainUpDown</span></span>|  
|<span data-ttu-id="d1e31-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="d1e31-274">ErrorProvider</span></span>|  
|<span data-ttu-id="d1e31-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1e31-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="d1e31-276">Form</span><span class="sxs-lookup"><span data-stu-id="d1e31-276">Form</span></span>|  
|<span data-ttu-id="d1e31-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d1e31-277">LinkLabel</span></span>|  
|<span data-ttu-id="d1e31-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="d1e31-278">HelpProvider</span></span>|  
|<span data-ttu-id="d1e31-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="d1e31-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d1e31-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="d1e31-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d1e31-281">NumericUpDown</span></span>|  
|<span data-ttu-id="d1e31-282">Panel</span><span class="sxs-lookup"><span data-stu-id="d1e31-282">Panel</span></span>|  
|<span data-ttu-id="d1e31-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="d1e31-283">PictureBox</span></span>|  
|<span data-ttu-id="d1e31-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="d1e31-284">PrintDocument</span></span>|  
|<span data-ttu-id="d1e31-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="d1e31-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="d1e31-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="d1e31-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="d1e31-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="d1e31-287">PropertyGrid</span></span>|  
|<span data-ttu-id="d1e31-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="d1e31-288">UserControl</span></span>|  
|<span data-ttu-id="d1e31-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d1e31-289">ToolStrip</span></span>|  
|<span data-ttu-id="d1e31-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1e31-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="d1e31-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="d1e31-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="d1e31-292">Разделитель</span><span class="sxs-lookup"><span data-stu-id="d1e31-292">Splitter</span></span>|  
|<span data-ttu-id="d1e31-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="d1e31-293">RaftingContainer</span></span>|  
|<span data-ttu-id="d1e31-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="d1e31-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1e31-295">См. также</span><span class="sxs-lookup"><span data-stu-id="d1e31-295">See also</span></span>

- [<span data-ttu-id="d1e31-296">Типы элементов управления автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d1e31-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
