---
title: Общие сведения о свойствах автоматизированного пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 8a44fd89017002ae51d9b15a22bac97668d0ff90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179871"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="0be9b-102">Общие сведения о свойствах автоматизированного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0be9b-102">UI Automation Properties Overview</span></span>
> [!NOTE]
> <span data-ttu-id="0be9b-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="0be9b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0be9b-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0be9b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0be9b-105">Поставщики автоматизации пользовательского интерфейса предоставляют свойства в элементах [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0be9b-105">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="0be9b-106">Эти свойства позволяют клиентским приложениям модели автоматизации пользовательского интерфейса обнаруживать сведения о частях [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], особенно элементах управления, включая статические и динамические данные.</span><span class="sxs-lookup"><span data-stu-id="0be9b-106">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="0be9b-107">В этом разделе приводится расширенный обзор свойств [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0be9b-107">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="0be9b-108">Более конкретные сведения даются в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="0be9b-108">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="0be9b-109">Свойства автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="0be9b-109">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="0be9b-110">Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="0be9b-110">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>
## <a name="property-identifiers"></a><span data-ttu-id="0be9b-111">Идентификаторы свойств</span><span class="sxs-lookup"><span data-stu-id="0be9b-111">Property Identifiers</span></span>  
 <span data-ttu-id="0be9b-112">Каждое свойство определяется номером и именем.</span><span class="sxs-lookup"><span data-stu-id="0be9b-112">Every property is identified by a number and a name.</span></span> <span data-ttu-id="0be9b-113">Имена свойств используются только для отладки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="0be9b-113">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="0be9b-114">Поставщики используют числовые идолы для идентификации входящих запросов свойств.</span><span class="sxs-lookup"><span data-stu-id="0be9b-114">Providers use the numeric IDs to identify incoming property requests.</span></span> <span data-ttu-id="0be9b-115">Однако клиентские приложения используют для идентификации свойств, которые им требуется получить, только ссылку <xref:System.Windows.Automation.AutomationProperty>, которая включает номер и имя.</span><span class="sxs-lookup"><span data-stu-id="0be9b-115">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="0be9b-116">Объекты<xref:System.Windows.Automation.AutomationProperty> , представляющие конкретные свойства, доступны как поля в различных классах.</span><span class="sxs-lookup"><span data-stu-id="0be9b-116"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="0be9b-117">По соображениям безопасности поставщики автоматизации пользовательского интерфейса получают эти объекты из отдельного набора классов, содержащихся в Uiautomationtypes.dll.</span><span class="sxs-lookup"><span data-stu-id="0be9b-117">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="0be9b-118">В следующей таблице классифицируются свойства <xref:System.Windows.Automation.AutomationProperty>по классам, содержащим итоговые иудиции.</span><span class="sxs-lookup"><span data-stu-id="0be9b-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span></span>  
  
|<span data-ttu-id="0be9b-119">Виды свойств</span><span class="sxs-lookup"><span data-stu-id="0be9b-119">Kinds of properties</span></span>|<span data-ttu-id="0be9b-120">Клиенты получают идентификаторы из</span><span class="sxs-lookup"><span data-stu-id="0be9b-120">Clients get IDs from</span></span>|<span data-ttu-id="0be9b-121">Поставщики получают идентификаторы из</span><span class="sxs-lookup"><span data-stu-id="0be9b-121">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="0be9b-122">Свойства, общие для всех элементов (см. следующие таблицы)</span><span class="sxs-lookup"><span data-stu-id="0be9b-122">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="0be9b-123">Положение закрепленного окна</span><span class="sxs-lookup"><span data-stu-id="0be9b-123">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="0be9b-124">Состояние элемента, который можно разворачивать и сворачивать</span><span class="sxs-lookup"><span data-stu-id="0be9b-124">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="0be9b-125">Свойства элемента в сетке</span><span class="sxs-lookup"><span data-stu-id="0be9b-125">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="0be9b-126">Свойства сетки</span><span class="sxs-lookup"><span data-stu-id="0be9b-126">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="0be9b-127">Текущее и поддерживаемое представление элемента, который имеет несколько представлений</span><span class="sxs-lookup"><span data-stu-id="0be9b-127">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="0be9b-128">Свойства элемента, который перемещается по диапазону значений, такого как ползунок</span><span class="sxs-lookup"><span data-stu-id="0be9b-128">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="0be9b-129">Свойства прокручиваемого окна</span><span class="sxs-lookup"><span data-stu-id="0be9b-129">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="0be9b-130">Состояние и контейнер элемента, который может быть выбран, например в списке</span><span class="sxs-lookup"><span data-stu-id="0be9b-130">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="0be9b-131">Свойства элемента управления, содержащего элементы выделения</span><span class="sxs-lookup"><span data-stu-id="0be9b-131">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="0be9b-132">Заголовки столбцов и строк элемента в таблице</span><span class="sxs-lookup"><span data-stu-id="0be9b-132">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="0be9b-133">Заголовки столбцов и строк, а также ориентация таблицы</span><span class="sxs-lookup"><span data-stu-id="0be9b-133">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="0be9b-134">Состояние элемента управления "Переключатель"</span><span class="sxs-lookup"><span data-stu-id="0be9b-134">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="0be9b-135">Возможности элемента, который поддерживает перемещение, поворот или изменение размера</span><span class="sxs-lookup"><span data-stu-id="0be9b-135">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="0be9b-136">Значение и возможности чтения/записи элемента, который имеет значение</span><span class="sxs-lookup"><span data-stu-id="0be9b-136">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="0be9b-137">Возможности и состояние окна</span><span class="sxs-lookup"><span data-stu-id="0be9b-137">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>
## <a name="properties-by-category"></a><span data-ttu-id="0be9b-138">Свойства, упорядоченные по категориям</span><span class="sxs-lookup"><span data-stu-id="0be9b-138">Properties by Category</span></span>  
 <span data-ttu-id="0be9b-139">Следующие таблицы классифицируют свойства, идентифицированные в исследуемые <xref:System.Windows.Automation.AutomationElement> <xref:System.Windows.Automation.AutomationElementIdentifiers>ими</span><span class="sxs-lookup"><span data-stu-id="0be9b-139">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="0be9b-140">Эти свойства являются общими для всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="0be9b-140">These properties are common to all controls.</span></span> <span data-ttu-id="0be9b-141">Почти все из них, скорее всего, будут статическими во время существования приложения поставщика; большинство динамических свойств связано с шаблонами элементов управления.</span><span class="sxs-lookup"><span data-stu-id="0be9b-141">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="0be9b-142">В столбце **Доступ к свойству** перечислены другие методы доступа для каждого свойства, в дополнение к <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> и <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="0be9b-142">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="0be9b-143">Дополнительные сведения о получении свойств в клиентском приложении см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0be9b-143">For more information on getting properties in a client application, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0be9b-144">Чтобы получить сведения о конкретном свойстве, используйте ссылку в столбце **Доступ к свойству** .</span><span class="sxs-lookup"><span data-stu-id="0be9b-144">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="0be9b-145">Характеристики отображения</span><span class="sxs-lookup"><span data-stu-id="0be9b-145">Display Characteristics</span></span>  
  
|<span data-ttu-id="0be9b-146">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-146">Property identifier</span></span>|<span data-ttu-id="0be9b-147">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-147">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="0be9b-148">Недоступно</span><span class="sxs-lookup"><span data-stu-id="0be9b-148">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="0be9b-149">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="0be9b-149">Element Type</span></span>  
  
|<span data-ttu-id="0be9b-150">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-150">Property identifier</span></span>|<span data-ttu-id="0be9b-151">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-151">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="0be9b-152">Идентификация</span><span class="sxs-lookup"><span data-stu-id="0be9b-152">Identification</span></span>  
  
|<span data-ttu-id="0be9b-153">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-153">Property identifier</span></span>|<span data-ttu-id="0be9b-154">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-154">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="0be9b-155">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="0be9b-155">Interaction</span></span>  
  
|<span data-ttu-id="0be9b-156">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-156">Property identifier</span></span>|<span data-ttu-id="0be9b-157">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-157">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="0be9b-158">Поддержка шаблонов</span><span class="sxs-lookup"><span data-stu-id="0be9b-158">Support for Patterns</span></span>  
  
|<span data-ttu-id="0be9b-159">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-159">Property identifier</span></span>|<span data-ttu-id="0be9b-160">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-160">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="0be9b-161">Разное</span><span class="sxs-lookup"><span data-stu-id="0be9b-161">Miscellaneous</span></span>  
  
|<span data-ttu-id="0be9b-162">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-162">Property identifier</span></span>|<span data-ttu-id="0be9b-163">Доступ к свойству</span><span class="sxs-lookup"><span data-stu-id="0be9b-163">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>
## <a name="localization"></a><span data-ttu-id="0be9b-164">Локализация</span><span class="sxs-lookup"><span data-stu-id="0be9b-164">Localization</span></span>  
 <span data-ttu-id="0be9b-165">Поставщики[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны представлять следующие свойства на языке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="0be9b-165">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>
## <a name="properties-and-events"></a><span data-ttu-id="0be9b-166">Свойства и события</span><span class="sxs-lookup"><span data-stu-id="0be9b-166">Properties and Events</span></span>  
 <span data-ttu-id="0be9b-167">Тесная связь со свойствами в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — это концепция событий изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="0be9b-167">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="0be9b-168">Для динамических свойств клиентскому приложению требуется способ узнать об изменении значения свойства, чтобы оно могло обновить свой кэш данных или отреагировать на новые сведения другим способом.</span><span class="sxs-lookup"><span data-stu-id="0be9b-168">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="0be9b-169">Поставщики вызывают события, когда что-нибудь в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] изменяется.</span><span class="sxs-lookup"><span data-stu-id="0be9b-169">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="0be9b-170">Например, если флажок устанавливается или снимается, реализация поставщика шаблона Toggle вызывает событие изменения свойства.</span><span class="sxs-lookup"><span data-stu-id="0be9b-170">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="0be9b-171">Поставщики могут вызывать события выборочно, в зависимости от наличия клиентов, прослушивающих события или прослушивающих определенные события.</span><span class="sxs-lookup"><span data-stu-id="0be9b-171">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="0be9b-172">Не все изменения свойств порождают события; это полностью зависит от реализации поставщика автоматизации пользовательского интерфейса для элемента.</span><span class="sxs-lookup"><span data-stu-id="0be9b-172">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="0be9b-173">Например, поставщики стандартных прокси для списков не вызывают событие, когда изменяется <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> .</span><span class="sxs-lookup"><span data-stu-id="0be9b-173">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="0be9b-174">В этом случае приложение должно прослушивать <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span><span class="sxs-lookup"><span data-stu-id="0be9b-174">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="0be9b-175">Клиенты прослушивают события, подписавшись на их.</span><span class="sxs-lookup"><span data-stu-id="0be9b-175">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="0be9b-176">Подписка на события означает создание методов делегата, могущих обрабатывать эти события, и затем передачу этих методов в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] вместе с конкретными событиями, которые будут обработаны в этих методах.</span><span class="sxs-lookup"><span data-stu-id="0be9b-176">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="0be9b-177">В частности, для событий изменения свойств клиенты должны реализовать <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="0be9b-177">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be9b-178">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0be9b-178">See also</span></span>

- [<span data-ttu-id="0be9b-179">Кэширование в клиентах автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0be9b-179">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
- [<span data-ttu-id="0be9b-180">Свойства автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="0be9b-180">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="0be9b-181">Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="0be9b-181">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="0be9b-182">Нахождение элемента модели автоматизации пользовательского интерфейса в зависимости от состояния свойства</span><span class="sxs-lookup"><span data-stu-id="0be9b-182">Find a UI Automation Element Based on a Property Condition</span></span>](find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="0be9b-183">Возврат свойств от поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0be9b-183">Return Properties from a UI Automation Provider</span></span>](return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="0be9b-184">Вызов событий из поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0be9b-184">Raise Events from a UI Automation Provider</span></span>](raise-events-from-a-ui-automation-provider.md)
