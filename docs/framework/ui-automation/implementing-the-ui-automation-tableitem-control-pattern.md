---
title: Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: e28ac8762c2c3a58a282b92da2b0a2dfadf32dbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398974"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="6129c-102">Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="6129c-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="6129c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6129c-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6129c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6129c-105">В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableItemProvider>, включая сведения о событиях и свойствах.</span><span class="sxs-lookup"><span data-stu-id="6129c-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="6129c-106">Ссылки на дополнительные материалы перечислены в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="6129c-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="6129c-107"><xref:System.Windows.Automation.TableItemPattern> Используется для поддержки дочерних элементов управления контейнеров, реализующих шаблон элемента управления <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="6129c-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="6129c-108">Доступ к функциям отдельной ячейки обеспечивается обязательной параллельной реализацией <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="6129c-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="6129c-109">Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridItemProvider> с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableItemProvider> должен программными средствами предоставлять отношение между отдельной ячейкой и сведениями ее строки и столбца.</span><span class="sxs-lookup"><span data-stu-id="6129c-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="6129c-110">Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6129c-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="6129c-111">Правила и соглашения реализации</span><span class="sxs-lookup"><span data-stu-id="6129c-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="6129c-112">Связанной функциональности элементов сетки, в разделе [реализации шаблон элемента управления GridItem модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="6129c-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="6129c-113">Обязательные члены для ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="6129c-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="6129c-114">Обязательный член</span><span class="sxs-lookup"><span data-stu-id="6129c-114">Required member</span></span>|<span data-ttu-id="6129c-115">Тип члена</span><span class="sxs-lookup"><span data-stu-id="6129c-115">Member type</span></span>|<span data-ttu-id="6129c-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="6129c-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="6129c-117">Метод</span><span class="sxs-lookup"><span data-stu-id="6129c-117">Method</span></span>|<span data-ttu-id="6129c-118">Нет</span><span class="sxs-lookup"><span data-stu-id="6129c-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="6129c-119">Метод</span><span class="sxs-lookup"><span data-stu-id="6129c-119">Method</span></span>|<span data-ttu-id="6129c-120">Нет</span><span class="sxs-lookup"><span data-stu-id="6129c-120">None</span></span>|  
  
 <span data-ttu-id="6129c-121">Этот шаблон элемента управления не имеет связанных свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="6129c-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="6129c-122">Исключения</span><span class="sxs-lookup"><span data-stu-id="6129c-122">Exceptions</span></span>  
 <span data-ttu-id="6129c-123">Этот шаблон элемента управления не имеет связанных исключений.</span><span class="sxs-lookup"><span data-stu-id="6129c-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6129c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6129c-124">See Also</span></span>  
 [<span data-ttu-id="6129c-125">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="6129c-126">Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="6129c-127">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="6129c-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="6129c-128">Реализация шаблона элемента управления Table модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="6129c-129">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="6129c-130">Общие сведения о дереве модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="6129c-131">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6129c-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
