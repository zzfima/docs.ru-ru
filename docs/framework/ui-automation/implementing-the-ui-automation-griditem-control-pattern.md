---
title: Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: d561587e6bb98ba857b27ba89b4c1a45ba964ffd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180189"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="ccfcd-102">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ccfcd-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ccfcd-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="ccfcd-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ccfcd-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ccfcd-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="ccfcd-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="ccfcd-107">Шаблон элемента управления <xref:System.Windows.Automation.GridItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="ccfcd-108">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ccfcd-109">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="ccfcd-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ccfcd-110">При реализации <xref:System.Windows.Automation.Provider.IGridProvider> обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ccfcd-111">Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="ccfcd-112">Объединенные ячейки будут передавать свои свойства <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> на основе свойств их базовой ячейки привязки в соответствии с определением в поставщике автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="ccfcd-113">Как правило, это будет самая верхняя строка и крайний левый столбец.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="ccfcd-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> не предусматривает активные манипуляции с сеткой, такие как объединение или разбиение ячеек.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="ccfcd-115">Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider>, обычно могут быть пройдены (то есть клиент автоматизации пользовательского интерфейса может переходить в соседние элементы управления) с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="ccfcd-116">Обязательные члены для IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="ccfcd-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="ccfcd-117">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="ccfcd-118">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="ccfcd-118">Required members</span></span>|<span data-ttu-id="ccfcd-119">Тип члена</span><span class="sxs-lookup"><span data-stu-id="ccfcd-119">Member type</span></span>|<span data-ttu-id="ccfcd-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccfcd-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="ccfcd-121">Свойство</span><span class="sxs-lookup"><span data-stu-id="ccfcd-121">Property</span></span>|<span data-ttu-id="ccfcd-122">None</span><span class="sxs-lookup"><span data-stu-id="ccfcd-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="ccfcd-123">Свойство</span><span class="sxs-lookup"><span data-stu-id="ccfcd-123">Property</span></span>|<span data-ttu-id="ccfcd-124">None</span><span class="sxs-lookup"><span data-stu-id="ccfcd-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="ccfcd-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="ccfcd-125">Property</span></span>|<span data-ttu-id="ccfcd-126">None</span><span class="sxs-lookup"><span data-stu-id="ccfcd-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="ccfcd-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="ccfcd-127">Property</span></span>|<span data-ttu-id="ccfcd-128">None</span><span class="sxs-lookup"><span data-stu-id="ccfcd-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="ccfcd-129">Свойство</span><span class="sxs-lookup"><span data-stu-id="ccfcd-129">Property</span></span>|<span data-ttu-id="ccfcd-130">None</span><span class="sxs-lookup"><span data-stu-id="ccfcd-130">None</span></span>|  
  
 <span data-ttu-id="ccfcd-131">Этот шаблон элемента управления не имеет связанных методов или событий.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="ccfcd-132">Исключения</span><span class="sxs-lookup"><span data-stu-id="ccfcd-132">Exceptions</span></span>  
 <span data-ttu-id="ccfcd-133">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfcd-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ccfcd-134">See also</span></span>

- [<span data-ttu-id="ccfcd-135">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="ccfcd-135">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ccfcd-136">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ccfcd-136">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ccfcd-137">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="ccfcd-137">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ccfcd-138">Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ccfcd-138">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="ccfcd-139">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="ccfcd-139">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ccfcd-140">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ccfcd-140">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
