---
title: Реализация шаблона элемента управления MultipleView модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 9decb617e30a340d3e73e911f7848110de5599e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180168"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="c41c5-102">Реализация шаблона элемента управления MultipleView модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c41c5-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="c41c5-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="c41c5-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c41c5-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="c41c5-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c41c5-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, включая сведения о событиях и свойствах.</span><span class="sxs-lookup"><span data-stu-id="c41c5-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="c41c5-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="c41c5-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="c41c5-107">Шаблон элемента управления <xref:System.Windows.Automation.MultipleViewPattern> используется для поддержки элементов управления, которые предоставляют несколько представлений одного набора сведений или дочерних элементов управления и способны переключаться между ними.</span><span class="sxs-lookup"><span data-stu-id="c41c5-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="c41c5-108">Примеры элементов управления, которые могут представлять несколько представлений, включают представление списка (которое может отображать его содержимое в виде эскизов, плиток, иконок или деталей), диаграммы Microsoft Excel (пирог, строка, бар, значение ячейки с формулой), документы Microsoft Word (нормальный, веб-макет, печать макет, макет чтения, наброски), календарь Microsoft Outlook (год, месяц, неделя, день) и сконы Microsoft Windows Media Player.</span><span class="sxs-lookup"><span data-stu-id="c41c5-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="c41c5-109">Поддерживаемые представления определяются разработчиками элементов управления и относятся к конкретному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="c41c5-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="c41c5-110">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="c41c5-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="c41c5-111">При реализации шаблона элемента управления Multiple View обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="c41c5-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="c41c5-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> также должен быть реализован в контейнере, который управляет текущим представлением, если он отличается от элемента управления, обеспечивающего текущее представление.</span><span class="sxs-lookup"><span data-stu-id="c41c5-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="c41c5-113">Например, проводник содержит элемент управления "Список" для текущего содержимого папки, а представлением для этого элемента управления управляет приложение проводника.</span><span class="sxs-lookup"><span data-stu-id="c41c5-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="c41c5-114">Элемент управления, который может сортировать свое содержимое, не считается поддерживающим несколько представлений.</span><span class="sxs-lookup"><span data-stu-id="c41c5-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="c41c5-115">Коллекция представлений должна быть идентичной во всех экземплярах.</span><span class="sxs-lookup"><span data-stu-id="c41c5-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="c41c5-116">Имена представлений должны быть подходящими для использования в приложениях преобразования текста в речь, шрифта Брайля и других приложениях для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="c41c5-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="c41c5-117">Обязательные члены для IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="c41c5-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="c41c5-118">Следующие свойства и методы обязательны для реализации IMultipleViewProvider.</span><span class="sxs-lookup"><span data-stu-id="c41c5-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="c41c5-119">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="c41c5-119">Required members</span></span>|<span data-ttu-id="c41c5-120">Тип члена</span><span class="sxs-lookup"><span data-stu-id="c41c5-120">Member type</span></span>|<span data-ttu-id="c41c5-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="c41c5-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="c41c5-122">Свойство</span><span class="sxs-lookup"><span data-stu-id="c41c5-122">Property</span></span>|<span data-ttu-id="c41c5-123">None</span><span class="sxs-lookup"><span data-stu-id="c41c5-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="c41c5-124">Метод</span><span class="sxs-lookup"><span data-stu-id="c41c5-124">Method</span></span>|<span data-ttu-id="c41c5-125">None</span><span class="sxs-lookup"><span data-stu-id="c41c5-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="c41c5-126">Метод</span><span class="sxs-lookup"><span data-stu-id="c41c5-126">Method</span></span>|<span data-ttu-id="c41c5-127">None</span><span class="sxs-lookup"><span data-stu-id="c41c5-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="c41c5-128">Метод</span><span class="sxs-lookup"><span data-stu-id="c41c5-128">Method</span></span>|<span data-ttu-id="c41c5-129">None</span><span class="sxs-lookup"><span data-stu-id="c41c5-129">None</span></span>|  
  
 <span data-ttu-id="c41c5-130">Отсутствуют события, связанные с этим шаблоном элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c41c5-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="c41c5-131">Исключения</span><span class="sxs-lookup"><span data-stu-id="c41c5-131">Exceptions</span></span>  
 <span data-ttu-id="c41c5-132">Поставщик должен вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="c41c5-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="c41c5-133">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="c41c5-133">Exception type</span></span>|<span data-ttu-id="c41c5-134">Условие</span><span class="sxs-lookup"><span data-stu-id="c41c5-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="c41c5-135">Когда метод <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> или <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> вызывается с параметром, который не является членом коллекции поддерживаемых представлений.</span><span class="sxs-lookup"><span data-stu-id="c41c5-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c41c5-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c41c5-136">See also</span></span>

- [<span data-ttu-id="c41c5-137">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="c41c5-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="c41c5-138">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c41c5-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="c41c5-139">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="c41c5-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="c41c5-140">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="c41c5-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="c41c5-141">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c41c5-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
