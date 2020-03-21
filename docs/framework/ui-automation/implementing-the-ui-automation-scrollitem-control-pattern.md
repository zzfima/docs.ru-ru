---
title: Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 3a0647ab98dcb86306573a0e9826fa7232fa9ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180146"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="ff244-102">Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ff244-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ff244-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="ff244-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ff244-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ff244-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ff244-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IScrollItemProvider>, включая сведения о свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="ff244-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="ff244-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="ff244-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ff244-107">Шаблон элемента управления <xref:System.Windows.Automation.ScrollItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="ff244-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="ff244-108">Этот шаблон элемента управления действует как отдельный канал связи между дочерним элементом управления и его контейнером, чтобы контейнер гарантированно мог изменять видимое в настоящий момент содержимое (или область) в его области просмотра для отображения дочернего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff244-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="ff244-109">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ff244-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ff244-110">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="ff244-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ff244-111">При реализации шаблона элемента управления ScrollItem обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="ff244-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ff244-112">Не требуется, чтобы элементы, содержащиеся в элементе управления "Окно" или "Полотно", реализовывали интерфейс IScrollItemProvider.</span><span class="sxs-lookup"><span data-stu-id="ff244-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="ff244-113">Однако в качестве альтернативы они должны предоставлять действительное расположение для <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="ff244-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="ff244-114">Это позволит клиентскому приложению модели автоматизации пользовательского интерфейса использовать методы шаблона элемента управления <xref:System.Windows.Automation.ScrollPattern> в контейнере для отображения дочернего элемента шаблона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff244-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="ff244-115">Обязательные члены для IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="ff244-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="ff244-116">Следующий метод является обязательным для реализации интерфейса IScrollProvider.</span><span class="sxs-lookup"><span data-stu-id="ff244-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="ff244-117">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="ff244-117">Required members</span></span>|<span data-ttu-id="ff244-118">Тип члена</span><span class="sxs-lookup"><span data-stu-id="ff244-118">Member type</span></span>|<span data-ttu-id="ff244-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff244-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="ff244-120">- Метод</span><span class="sxs-lookup"><span data-stu-id="ff244-120">-   Method</span></span>|<span data-ttu-id="ff244-121">None</span><span class="sxs-lookup"><span data-stu-id="ff244-121">None</span></span>|  
  
 <span data-ttu-id="ff244-122">Этот шаблон элемента управления не имеет связанных свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="ff244-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="ff244-123">Исключения</span><span class="sxs-lookup"><span data-stu-id="ff244-123">Exceptions</span></span>  
 <span data-ttu-id="ff244-124">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="ff244-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ff244-125">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="ff244-125">Exception Type</span></span>|<span data-ttu-id="ff244-126">Условие</span><span class="sxs-lookup"><span data-stu-id="ff244-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="ff244-127">Если элемент не может быть прокручен в представлении:</span><span class="sxs-lookup"><span data-stu-id="ff244-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="ff244-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff244-128">See also</span></span>

- [<span data-ttu-id="ff244-129">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="ff244-129">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ff244-130">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ff244-130">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ff244-131">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="ff244-131">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ff244-132">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="ff244-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ff244-133">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ff244-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
