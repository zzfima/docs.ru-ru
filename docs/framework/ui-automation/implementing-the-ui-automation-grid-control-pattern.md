---
title: "Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, grid
- grid control pattern
- UI Automation, grid control pattern
ms.assetid: 234d11a0-7ce7-4309-8989-2f4720e02f78
caps.latest.revision: "27"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4667cd149940310e2422686b9e9fdf6e7e99ca9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-grid-control-pattern"></a><span data-ttu-id="0ae10-102">Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-102">Implementing the UI Automation Grid Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="0ae10-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="0ae10-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0ae10-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="0ae10-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="0ae10-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridProvider>, включая сведения о свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="0ae10-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="0ae10-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="0ae10-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="0ae10-107">Шаблон элемента управления <xref:System.Windows.Automation.GridPattern> используется для поддержки элементов управления, которые действуют как контейнеры для коллекции дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="0ae10-107">The <xref:System.Windows.Automation.GridPattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="0ae10-108">Дочерние элементы данного элемента должны реализовывать <xref:System.Windows.Automation.Provider.IGridItemProvider> и быть организованы в двумерной логической системе координат, к которой можно обращаться по строкам и столбцам.</span><span class="sxs-lookup"><span data-stu-id="0ae10-108">The children of this element must implement <xref:System.Windows.Automation.Provider.IGridItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="0ae10-109">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0ae10-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="0ae10-110">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="0ae10-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="0ae10-111">При реализации шаблона элемента управления Grid обратите внимание на следующие правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="0ae10-111">When implementing the Grid control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="0ae10-112">Координаты сетки отсчитываются начиная с нуля и от левой верхней ячейки (или правой верхней ячейки в зависимости от языкового стандарта), имеющей координаты (0, 0).</span><span class="sxs-lookup"><span data-stu-id="0ae10-112">Grid coordinates are zero-based with the upper left (or upper right cell depending on locale) having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="0ae10-113">Если ячейка пуста, элемент модели автоматизации пользовательского интерфейса по-прежнему должен возвращаться для поддержки свойства <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> для этой ячейки.</span><span class="sxs-lookup"><span data-stu-id="0ae10-113">If a cell is empty, a UI Automation element must still be returned in order to support the <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> property for that cell.</span></span> <span data-ttu-id="0ae10-114">Это возможно, когда макет дочерних элементов сетки подобен массиву с переменной длиной (см. пример ниже).</span><span class="sxs-lookup"><span data-stu-id="0ae10-114">This is possible when the layout of child elements in the grid is similar to a ragged array (see example below).</span></span>  
  
 <span data-ttu-id="0ae10-115">![Представление проводника Windows: раскладка без выравнивания. ] (../../../docs/framework/ui-automation/media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")</span><span class="sxs-lookup"><span data-stu-id="0ae10-115">![Windows Explorer view showing ragged layout.](../../../docs/framework/ui-automation/media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")</span></span>  
<span data-ttu-id="0ae10-116">Пример элемента управления "Сетка" с пустыми координатами</span><span class="sxs-lookup"><span data-stu-id="0ae10-116">Example of a Grid Control with Empty Coordinates</span></span>  
  
-   <span data-ttu-id="0ae10-117">Сетка с единственным элементом по-прежнему должна реализовывать <xref:System.Windows.Automation.Provider.IGridProvider> , если она логически считается сеткой.</span><span class="sxs-lookup"><span data-stu-id="0ae10-117">A grid with a single item is still required to implement <xref:System.Windows.Automation.Provider.IGridProvider> if it is logically considered to be a grid.</span></span> <span data-ttu-id="0ae10-118">Количество дочерних элементов в сетке не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="0ae10-118">The number of child items in the grid is immaterial.</span></span>  
  
-   <span data-ttu-id="0ae10-119">Скрытые строки и столбцы, в зависимости от реализации поставщика, могут быть загружены в дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и поэтому будут отражаться в свойствах <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> и <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ae10-119">Hidden rows and columns, depending on the provider implementation, may be loaded in the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree and therefore will be reflected in the <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> and <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> properties.</span></span> <span data-ttu-id="0ae10-120">Если скрытые строки и столбцы еще не загружены, они не должны учитываться.</span><span class="sxs-lookup"><span data-stu-id="0ae10-120">If the hidden rows and columns have not yet been loaded, they should not be counted.</span></span>  
  
-   <span data-ttu-id="0ae10-121"><xref:System.Windows.Automation.Provider.IGridProvider> не позволяет активно манипулировать сеткой; для включения этой функциональности необходимо реализовать <xref:System.Windows.Automation.Provider.ITransformProvider> .</span><span class="sxs-lookup"><span data-stu-id="0ae10-121"><xref:System.Windows.Automation.Provider.IGridProvider> does not enable active manipulation of a grid; <xref:System.Windows.Automation.Provider.ITransformProvider> must be implemented to enable this functionality.</span></span>  
  
-   <span data-ttu-id="0ae10-122">Используйте <xref:System.Windows.Automation.StructureChangedEventHandler> для прослушивания изменений структуры или макета сетки, таких как добавление, удаление или слияние ячеек.</span><span class="sxs-lookup"><span data-stu-id="0ae10-122">Use a <xref:System.Windows.Automation.StructureChangedEventHandler> to listen for structural or layout changes to the grid such as cells that have been added, removed, or merged.</span></span>  
  
-   <span data-ttu-id="0ae10-123">Используйте <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> для отслеживания прохождения по элементам или ячейкам сетки.</span><span class="sxs-lookup"><span data-stu-id="0ae10-123">Use a <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> to track traversal through the items or cells of a grid.</span></span>  
  
<a name="Required_Members_for_IGridProvider"></a>   
## <a name="required-members-for-igridprovider"></a><span data-ttu-id="0ae10-124">Обязательные члены для IGridProvider</span><span class="sxs-lookup"><span data-stu-id="0ae10-124">Required Members for IGridProvider</span></span>  
 <span data-ttu-id="0ae10-125">Следующие свойства и методы обязательны для реализации интерфейса IGridProvider.</span><span class="sxs-lookup"><span data-stu-id="0ae10-125">The following properties and methods are required for implementing the IGridProvider interface.</span></span>  
  
|<span data-ttu-id="0ae10-126">Обязательные члены</span><span class="sxs-lookup"><span data-stu-id="0ae10-126">Required members</span></span>|<span data-ttu-id="0ae10-127">Тип</span><span class="sxs-lookup"><span data-stu-id="0ae10-127">Type</span></span>|<span data-ttu-id="0ae10-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ae10-128">Notes</span></span>|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A>|<span data-ttu-id="0ae10-129">Свойство</span><span class="sxs-lookup"><span data-stu-id="0ae10-129">Property</span></span>|<span data-ttu-id="0ae10-130">Нет</span><span class="sxs-lookup"><span data-stu-id="0ae10-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>|<span data-ttu-id="0ae10-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="0ae10-131">Property</span></span>|<span data-ttu-id="0ae10-132">Нет</span><span class="sxs-lookup"><span data-stu-id="0ae10-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A>|<span data-ttu-id="0ae10-133">Метод</span><span class="sxs-lookup"><span data-stu-id="0ae10-133">Method</span></span>|<span data-ttu-id="0ae10-134">Нет</span><span class="sxs-lookup"><span data-stu-id="0ae10-134">None</span></span>|  
  
 <span data-ttu-id="0ae10-135">Этот шаблон элемента управления не имеет связанных событий.</span><span class="sxs-lookup"><span data-stu-id="0ae10-135">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="0ae10-136">Исключения</span><span class="sxs-lookup"><span data-stu-id="0ae10-136">Exceptions</span></span>  
 <span data-ttu-id="0ae10-137">Поставщики должны вызывать следующие исключения.</span><span class="sxs-lookup"><span data-stu-id="0ae10-137">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="0ae10-138">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="0ae10-138">Exception type</span></span>|<span data-ttu-id="0ae10-139">Условие</span><span class="sxs-lookup"><span data-stu-id="0ae10-139">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> <span data-ttu-id="0ae10-140">-Если запрошенная координата строки больше, чем <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> или координата столбца больше, чем <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ae10-140">-   If the requested row coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> or the column coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> <span data-ttu-id="0ae10-141">-Если Запрошенная строка или столбца координаты меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="0ae10-141">-   If either of the requested row or column coordinates is less than zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ae10-142">См. также</span><span class="sxs-lookup"><span data-stu-id="0ae10-142">See Also</span></span>  
 [<span data-ttu-id="0ae10-143">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-143">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="0ae10-144">Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-144">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="0ae10-145">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="0ae10-145">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="0ae10-146">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-146">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="0ae10-147">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-147">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="0ae10-148">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0ae10-148">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
