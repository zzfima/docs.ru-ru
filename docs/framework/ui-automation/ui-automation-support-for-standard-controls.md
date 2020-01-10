---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: ed5e4f6ab23fe9ae77c94616a668da8accb46d4b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741699"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="8f7f8-102">Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления</span><span class="sxs-lookup"><span data-stu-id="8f7f8-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="8f7f8-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="8f7f8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8f7f8-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8f7f8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8f7f8-105">В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f7f8-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="8f7f8-106">Элементы представления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="8f7f8-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="8f7f8-107">Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f7f8-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8f7f8-108">Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f7f8-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="8f7f8-109">Элементы управления Win32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-109">Win32 Controls</span></span>  
 <span data-ttu-id="8f7f8-110">Большинство элементов управления Win32 доступны для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] с помощью поставщиков на стороне клиента в UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8f7f8-111">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8f7f8-112">Полная поддержка предоставляется только для элементов управления из *ComCtrl32. dll*версии 6.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="8f7f8-113">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8f7f8-114">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8f7f8-114">Class name</span></span>|<span data-ttu-id="8f7f8-115">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="8f7f8-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8f7f8-116">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-116">Button</span></span>|<span data-ttu-id="8f7f8-117">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-117">Button</span></span>|  
|<span data-ttu-id="8f7f8-118">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-118">Button</span></span>|<span data-ttu-id="8f7f8-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8f7f8-119">RadioButton</span></span>|  
|<span data-ttu-id="8f7f8-120">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-120">Button</span></span>|<span data-ttu-id="8f7f8-121">Группа</span><span class="sxs-lookup"><span data-stu-id="8f7f8-121">Group</span></span>|  
|<span data-ttu-id="8f7f8-122">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-122">Button</span></span>|<span data-ttu-id="8f7f8-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-123">CheckBox</span></span>|  
|<span data-ttu-id="8f7f8-124">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-124">Button</span></span>|<span data-ttu-id="8f7f8-125">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-125">Hyperlink</span></span>|  
|<span data-ttu-id="8f7f8-126">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-126">Button</span></span>|<span data-ttu-id="8f7f8-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="8f7f8-127">SplitButton</span></span>|  
|<span data-ttu-id="8f7f8-128">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-128">Button</span></span>|<span data-ttu-id="8f7f8-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-129">CheckBox</span></span>|  
|<span data-ttu-id="8f7f8-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-130">ComboBoxEx32</span></span>|<span data-ttu-id="8f7f8-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-131">ComboBox</span></span>|  
|<span data-ttu-id="8f7f8-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-132">ComboBox</span></span>|<span data-ttu-id="8f7f8-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-133">ComboBox</span></span>|  
|<span data-ttu-id="8f7f8-134">Edit</span><span class="sxs-lookup"><span data-stu-id="8f7f8-134">Edit</span></span>|<span data-ttu-id="8f7f8-135">Document</span><span class="sxs-lookup"><span data-stu-id="8f7f8-135">Document</span></span>|  
|<span data-ttu-id="8f7f8-136">Edit</span><span class="sxs-lookup"><span data-stu-id="8f7f8-136">Edit</span></span>|<span data-ttu-id="8f7f8-137">Edit</span><span class="sxs-lookup"><span data-stu-id="8f7f8-137">Edit</span></span>|  
|<span data-ttu-id="8f7f8-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="8f7f8-138">SysLink</span></span>|<span data-ttu-id="8f7f8-139">Гиперссылка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-139">Hyperlink</span></span>|  
|<span data-ttu-id="8f7f8-140">Static</span><span class="sxs-lookup"><span data-stu-id="8f7f8-140">Static</span></span>|<span data-ttu-id="8f7f8-141">Текст</span><span class="sxs-lookup"><span data-stu-id="8f7f8-141">Text</span></span>|  
|<span data-ttu-id="8f7f8-142">Static</span><span class="sxs-lookup"><span data-stu-id="8f7f8-142">Static</span></span>|<span data-ttu-id="8f7f8-143">Изображение</span><span class="sxs-lookup"><span data-stu-id="8f7f8-143">Image</span></span>|  
|<span data-ttu-id="8f7f8-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-144">SysIPAddress32</span></span>|<span data-ttu-id="8f7f8-145">Другой</span><span class="sxs-lookup"><span data-stu-id="8f7f8-145">Custom</span></span>|  
|<span data-ttu-id="8f7f8-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-146">SysHeader32</span></span>|<span data-ttu-id="8f7f8-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="8f7f8-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-148">SysListView32</span></span>|<span data-ttu-id="8f7f8-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8f7f8-149">DataGrid</span></span>|  
|<span data-ttu-id="8f7f8-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-150">SysListView32</span></span>|<span data-ttu-id="8f7f8-151">Список</span><span class="sxs-lookup"><span data-stu-id="8f7f8-151">List</span></span>|  
|<span data-ttu-id="8f7f8-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-152">ListBox</span></span>|<span data-ttu-id="8f7f8-153">Список</span><span class="sxs-lookup"><span data-stu-id="8f7f8-153">List</span></span>|  
|<span data-ttu-id="8f7f8-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-154">ListBox</span></span>|<span data-ttu-id="8f7f8-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-155">ListItem</span></span>|  
|<span data-ttu-id="8f7f8-156">#32768</span><span class="sxs-lookup"><span data-stu-id="8f7f8-156">#32768</span></span>|<span data-ttu-id="8f7f8-157">Меню</span><span class="sxs-lookup"><span data-stu-id="8f7f8-157">Menu</span></span>|  
|<span data-ttu-id="8f7f8-158">#32768</span><span class="sxs-lookup"><span data-stu-id="8f7f8-158">#32768</span></span>|<span data-ttu-id="8f7f8-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-159">MenuItem</span></span>|  
|<span data-ttu-id="8f7f8-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-160">msctls_progress32</span></span>|<span data-ttu-id="8f7f8-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-161">ProgressBar</span></span>|  
|<span data-ttu-id="8f7f8-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="8f7f8-162">RichEdit</span></span>|<span data-ttu-id="8f7f8-163">Документ.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-163">Document.</span></span> <span data-ttu-id="8f7f8-164">См. примечание.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-164">See note.</span></span>|  
|<span data-ttu-id="8f7f8-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="8f7f8-165">RichEdit20A</span></span>|<span data-ttu-id="8f7f8-166">Document</span><span class="sxs-lookup"><span data-stu-id="8f7f8-166">Document</span></span>|  
|<span data-ttu-id="8f7f8-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="8f7f8-167">RichEdit20W</span></span>|<span data-ttu-id="8f7f8-168">Document</span><span class="sxs-lookup"><span data-stu-id="8f7f8-168">Document</span></span>|  
|<span data-ttu-id="8f7f8-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="8f7f8-169">RichEdit50W</span></span>|<span data-ttu-id="8f7f8-170">Document</span><span class="sxs-lookup"><span data-stu-id="8f7f8-170">Document</span></span>|  
|<span data-ttu-id="8f7f8-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-171">ScrollBar</span></span>|<span data-ttu-id="8f7f8-172">Slider</span><span class="sxs-lookup"><span data-stu-id="8f7f8-172">Slider</span></span>|  
|<span data-ttu-id="8f7f8-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-173">msctls_trackbar32</span></span>|<span data-ttu-id="8f7f8-174">Slider</span><span class="sxs-lookup"><span data-stu-id="8f7f8-174">Slider</span></span>|  
|<span data-ttu-id="8f7f8-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-175">msctls_updown32</span></span>|<span data-ttu-id="8f7f8-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="8f7f8-176">Spinner</span></span>|  
|<span data-ttu-id="8f7f8-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-177">msctls_statusbar32</span></span>|<span data-ttu-id="8f7f8-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-178">StatusBar</span></span>|  
|<span data-ttu-id="8f7f8-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-179">SysTabControl32</span></span>|<span data-ttu-id="8f7f8-180">Tab</span><span class="sxs-lookup"><span data-stu-id="8f7f8-180">Tab</span></span>|  
|<span data-ttu-id="8f7f8-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-181">SysTabControl32</span></span>|<span data-ttu-id="8f7f8-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-182">TabItem</span></span>|  
|<span data-ttu-id="8f7f8-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-183">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-184">ToolBar</span></span>|  
|<span data-ttu-id="8f7f8-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-185">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-186">MenuItem</span></span>|  
|<span data-ttu-id="8f7f8-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-187">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-188">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-188">Button</span></span>|  
|<span data-ttu-id="8f7f8-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-189">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-190">CheckBox</span></span>|  
|<span data-ttu-id="8f7f8-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-191">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8f7f8-192">RadioButton</span></span>|  
|<span data-ttu-id="8f7f8-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-193">ToolbarWindow32</span></span>|<span data-ttu-id="8f7f8-194">Separator</span><span class="sxs-lookup"><span data-stu-id="8f7f8-194">Separator</span></span>|  
|<span data-ttu-id="8f7f8-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-195">tooltips_class32</span></span>|<span data-ttu-id="8f7f8-196">Подсказка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-196">ToolTip</span></span>|  
|<span data-ttu-id="8f7f8-197">#32774</span><span class="sxs-lookup"><span data-stu-id="8f7f8-197">#32774</span></span>|<span data-ttu-id="8f7f8-198">Подсказка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-198">ToolTip</span></span>|  
|<span data-ttu-id="8f7f8-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-199">ReBarWindow32</span></span>|<span data-ttu-id="8f7f8-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-200">Toolbar</span></span>|  
|<span data-ttu-id="8f7f8-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-201">SysTreeView32</span></span>|<span data-ttu-id="8f7f8-202">Дерево</span><span class="sxs-lookup"><span data-stu-id="8f7f8-202">Tree</span></span>|  
|<span data-ttu-id="8f7f8-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-203">SysTreeView32</span></span>|<span data-ttu-id="8f7f8-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="8f7f8-204">TreeItem</span></span>|  
  
 <span data-ttu-id="8f7f8-205">**Примечание** . Элемент управления RichEdit поддерживается только для версий, поставляемых с Windows Vista (в библиотеки RICHED20. dll версии 3,1 и более поздних версий и Мсфтедит. dll версии 4,1 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="8f7f8-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="8f7f8-206">Следующие элементы управления не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="8f7f8-207">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8f7f8-207">Class name</span></span>|<span data-ttu-id="8f7f8-208">Тип элемента управления</span><span class="sxs-lookup"><span data-stu-id="8f7f8-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8f7f8-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-209">SysAnimate32</span></span>|<span data-ttu-id="8f7f8-210">Изображение</span><span class="sxs-lookup"><span data-stu-id="8f7f8-210">Image</span></span>|  
|<span data-ttu-id="8f7f8-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="8f7f8-211">SysPager</span></span>|<span data-ttu-id="8f7f8-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="8f7f8-212">Spinner</span></span>|  
|<span data-ttu-id="8f7f8-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-213">SysDateTimePick32</span></span>|<span data-ttu-id="8f7f8-214">Другой</span><span class="sxs-lookup"><span data-stu-id="8f7f8-214">Custom</span></span>|  
|<span data-ttu-id="8f7f8-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="8f7f8-215">SysMonthCal32</span></span>|<span data-ttu-id="8f7f8-216">Календарь</span><span class="sxs-lookup"><span data-stu-id="8f7f8-216">Calendar</span></span>|  
|<span data-ttu-id="8f7f8-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="8f7f8-217">MS_WINNOTE</span></span>|<span data-ttu-id="8f7f8-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8f7f8-218">Tooltip</span></span>|  
|<span data-ttu-id="8f7f8-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="8f7f8-219">VBBubble</span></span>|<span data-ttu-id="8f7f8-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8f7f8-220">Tooltip</span></span>|  
|<span data-ttu-id="8f7f8-221">ScrollBar (при использовании в качестве отдельного элемента управления)</span><span class="sxs-lookup"><span data-stu-id="8f7f8-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="8f7f8-222">Slider</span><span class="sxs-lookup"><span data-stu-id="8f7f8-222">Slider</span></span>|  
|<span data-ttu-id="8f7f8-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="8f7f8-223">SuperGrid</span></span>|<span data-ttu-id="8f7f8-224">Другой</span><span class="sxs-lookup"><span data-stu-id="8f7f8-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="8f7f8-225">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f7f8-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="8f7f8-226">Windows Forms элементы управления предоставляются для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] с помощью поставщиков на стороне клиента в UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8f7f8-227">Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8f7f8-228">Обычно [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]поддерживают элементы управления Windows Forms, которые являются управляемыми оболочками для стандартных элементов управления Win32.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8f7f8-229">Поддерживаются следующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8f7f8-230">Имя класса</span><span class="sxs-lookup"><span data-stu-id="8f7f8-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="8f7f8-231">Кнопка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-231">Button</span></span>|  
|<span data-ttu-id="8f7f8-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-232">CheckBox</span></span>|  
|<span data-ttu-id="8f7f8-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-233">CheckedListBox</span></span>|  
|<span data-ttu-id="8f7f8-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-234">ColorDialog</span></span>|  
|<span data-ttu-id="8f7f8-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-235">ComboBox</span></span>|  
|<span data-ttu-id="8f7f8-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="8f7f8-236">FolderBrowser</span></span>|  
|<span data-ttu-id="8f7f8-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-237">FontDialog</span></span>|  
|<span data-ttu-id="8f7f8-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-238">GroupBox</span></span>|  
|<span data-ttu-id="8f7f8-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-239">HscrollBar</span></span>|  
|<span data-ttu-id="8f7f8-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="8f7f8-240">ImageList</span></span>|  
|<span data-ttu-id="8f7f8-241">Метка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-241">Label</span></span>|  
|<span data-ttu-id="8f7f8-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-242">ListBox</span></span>|  
|<span data-ttu-id="8f7f8-243">ListView</span><span class="sxs-lookup"><span data-stu-id="8f7f8-243">ListView</span></span>|  
|<span data-ttu-id="8f7f8-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="8f7f8-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="8f7f8-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-245">MonthCalendar</span></span>|  
|<span data-ttu-id="8f7f8-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="8f7f8-246">NotifyIcon</span></span>|  
|<span data-ttu-id="8f7f8-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="8f7f8-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="8f7f8-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-249">PrintDialog</span></span>|  
|<span data-ttu-id="8f7f8-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-250">ProgressBar</span></span>|  
|<span data-ttu-id="8f7f8-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8f7f8-251">RadioButton</span></span>|  
|<span data-ttu-id="8f7f8-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-252">RichTextBox</span></span>|  
|<span data-ttu-id="8f7f8-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="8f7f8-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="8f7f8-254">ScrollableControl</span></span>|  
|<span data-ttu-id="8f7f8-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8f7f8-255">SoundPlayer</span></span>|  
|<span data-ttu-id="8f7f8-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-256">StatusBar</span></span>|  
|<span data-ttu-id="8f7f8-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="8f7f8-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="8f7f8-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-258">TextBox</span></span>|  
|<span data-ttu-id="8f7f8-259">Таймер</span><span class="sxs-lookup"><span data-stu-id="8f7f8-259">Timer</span></span>|  
|<span data-ttu-id="8f7f8-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-260">Toolbar</span></span>|  
|<span data-ttu-id="8f7f8-261">Подсказка</span><span class="sxs-lookup"><span data-stu-id="8f7f8-261">ToolTip</span></span>|  
|<span data-ttu-id="8f7f8-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-262">TrackBar</span></span>|  
|<span data-ttu-id="8f7f8-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="8f7f8-263">TreeView</span></span>|  
|<span data-ttu-id="8f7f8-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="8f7f8-264">VscrollBar</span></span>|  
|<span data-ttu-id="8f7f8-265">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="8f7f8-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="8f7f8-266">Следующие элементы управления доступны для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только с помощью поддержки Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="8f7f8-267">Некоторые функциональные возможности могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="8f7f8-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="8f7f8-268">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="8f7f8-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="8f7f8-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="8f7f8-269">BindingSource</span></span>|  
|<span data-ttu-id="8f7f8-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8f7f8-270">DataGrid</span></span>|  
|<span data-ttu-id="8f7f8-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="8f7f8-271">DataGridView</span></span>|  
|<span data-ttu-id="8f7f8-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="8f7f8-272">DataNavigator</span></span>|  
|<span data-ttu-id="8f7f8-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="8f7f8-273">DomainUpDown</span></span>|  
|<span data-ttu-id="8f7f8-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="8f7f8-274">ErrorProvider</span></span>|  
|<span data-ttu-id="8f7f8-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8f7f8-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="8f7f8-276">Form</span><span class="sxs-lookup"><span data-stu-id="8f7f8-276">Form</span></span>|  
|<span data-ttu-id="8f7f8-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8f7f8-277">LinkLabel</span></span>|  
|<span data-ttu-id="8f7f8-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="8f7f8-278">HelpProvider</span></span>|  
|<span data-ttu-id="8f7f8-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="8f7f8-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8f7f8-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="8f7f8-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="8f7f8-281">NumericUpDown</span></span>|  
|<span data-ttu-id="8f7f8-282">Panel</span><span class="sxs-lookup"><span data-stu-id="8f7f8-282">Panel</span></span>|  
|<span data-ttu-id="8f7f8-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="8f7f8-283">PictureBox</span></span>|  
|<span data-ttu-id="8f7f8-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="8f7f8-284">PrintDocument</span></span>|  
|<span data-ttu-id="8f7f8-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="8f7f8-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="8f7f8-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="8f7f8-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="8f7f8-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8f7f8-287">PropertyGrid</span></span>|  
|<span data-ttu-id="8f7f8-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="8f7f8-288">UserControl</span></span>|  
|<span data-ttu-id="8f7f8-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8f7f8-289">ToolStrip</span></span>|  
|<span data-ttu-id="8f7f8-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8f7f8-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="8f7f8-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="8f7f8-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="8f7f8-292">Функции разделения</span><span class="sxs-lookup"><span data-stu-id="8f7f8-292">Splitter</span></span>|  
|<span data-ttu-id="8f7f8-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="8f7f8-293">RaftingContainer</span></span>|  
|<span data-ttu-id="8f7f8-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="8f7f8-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f7f8-295">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f7f8-295">See also</span></span>

- [<span data-ttu-id="8f7f8-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="8f7f8-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
