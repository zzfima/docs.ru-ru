---
title: Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68de80e4a01de27c16c0ed85c4177c562d5e328b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204720"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="6bacf-102">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="6bacf-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="6bacf-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6bacf-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6bacf-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6bacf-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах.</span><span class="sxs-lookup"><span data-stu-id="6bacf-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="6bacf-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="6bacf-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="6bacf-107"><xref:System.Windows.Automation.GridItemPattern> Шаблон элемента управления используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="6bacf-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="6bacf-108">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6bacf-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="6bacf-109">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="6bacf-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="6bacf-110">При реализации <xref:System.Windows.Automation.Provider.IGridProvider>, обратите внимание на следующие правила и соглашения:</span><span class="sxs-lookup"><span data-stu-id="6bacf-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="6bacf-111">Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).</span><span class="sxs-lookup"><span data-stu-id="6bacf-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="6bacf-112">Объединенные ячейки будут передавать свои <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> основании свойств их базовой ячейки, как определено поставщиком модели автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6bacf-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="6bacf-113">Как правило, это будет самая верхняя строка и крайний левый столбец.</span><span class="sxs-lookup"><span data-stu-id="6bacf-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="6bacf-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> не поддерживает активные манипуляции с сеткой, такие как объединение или разбиение ячеек.</span><span class="sxs-lookup"><span data-stu-id="6bacf-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="6bacf-115">Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider> обычно могут быть пройдены (то есть клиент автоматизации пользовательского интерфейса может переходить между соседними элементами управления) с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="6bacf-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="6bacf-116">Обязательные члены для IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="6bacf-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="6bacf-117">Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="6bacf-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="6bacf-118">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="6bacf-118">Required members</span></span>|<span data-ttu-id="6bacf-119">Тип члена</span><span class="sxs-lookup"><span data-stu-id="6bacf-119">Member type</span></span>|<span data-ttu-id="6bacf-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="6bacf-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="6bacf-121">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6bacf-121">Property</span></span>|<span data-ttu-id="6bacf-122">Нет</span><span class="sxs-lookup"><span data-stu-id="6bacf-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="6bacf-123">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6bacf-123">Property</span></span>|<span data-ttu-id="6bacf-124">Нет</span><span class="sxs-lookup"><span data-stu-id="6bacf-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="6bacf-125">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6bacf-125">Property</span></span>|<span data-ttu-id="6bacf-126">Нет</span><span class="sxs-lookup"><span data-stu-id="6bacf-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="6bacf-127">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6bacf-127">Property</span></span>|<span data-ttu-id="6bacf-128">Нет</span><span class="sxs-lookup"><span data-stu-id="6bacf-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="6bacf-129">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6bacf-129">Property</span></span>|<span data-ttu-id="6bacf-130">Нет</span><span class="sxs-lookup"><span data-stu-id="6bacf-130">None</span></span>|  
  
 <span data-ttu-id="6bacf-131">Этот шаблон элемента управления не имеет связанных методов или событий.</span><span class="sxs-lookup"><span data-stu-id="6bacf-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="6bacf-132">Исключения</span><span class="sxs-lookup"><span data-stu-id="6bacf-132">Exceptions</span></span>  
 <span data-ttu-id="6bacf-133">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="6bacf-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bacf-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6bacf-134">See Also</span></span>  
 [<span data-ttu-id="6bacf-135">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="6bacf-136">Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="6bacf-137">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="6bacf-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="6bacf-138">Реализация шаблона элемента управления Grid модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="6bacf-139">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="6bacf-140">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6bacf-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
