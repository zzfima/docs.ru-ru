---
title: "Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: "10"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 26cdf2dea8ec924d4345c1591be8fee1ed489c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="64c1c-102">Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="64c1c-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="64c1c-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="64c1c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="64c1c-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="64c1c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="64c1c-105">В этом разделе показано, как получать объекты шаблона элемента управления из [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элементов.</span><span class="sxs-lookup"><span data-stu-id="64c1c-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="64c1c-106">Получение всех шаблонов элементов управления</span><span class="sxs-lookup"><span data-stu-id="64c1c-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="64c1c-107">Получить <xref:System.Windows.Automation.AutomationElement> шаблоны элементов управления которого вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="64c1c-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="64c1c-108">Вызовите <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> , чтобы получить все шаблоны элементов управления из этого элемента.</span><span class="sxs-lookup"><span data-stu-id="64c1c-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="64c1c-109">Настоятельно рекомендуется не использовать клиент <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="64c1c-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="64c1c-110">Производительность может значительно снизиться, так как этот метод вызывает <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> внутренне для каждого существующего шаблона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64c1c-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="64c1c-111">Если это возможно, клиент должен вызывать метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> для основных интересующих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="64c1c-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="64c1c-112">Получение конкретного шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="64c1c-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="64c1c-113">Получить <xref:System.Windows.Automation.AutomationElement> шаблоны элементов управления которого вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="64c1c-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="64c1c-114">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> для запроса определенного шаблона.</span><span class="sxs-lookup"><span data-stu-id="64c1c-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="64c1c-115">Эти методы похожи, но если шаблон не найден, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> вызывает исключение, и <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="64c1c-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64c1c-116">Пример</span><span class="sxs-lookup"><span data-stu-id="64c1c-116">Example</span></span>  
 <span data-ttu-id="64c1c-117">В следующем примере извлекается <xref:System.Windows.Automation.AutomationElement> для элемента списка и получает <xref:System.Windows.Automation.SelectionItemPattern> из этого элемента.</span><span class="sxs-lookup"><span data-stu-id="64c1c-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="64c1c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="64c1c-118">See Also</span></span>  
 [<span data-ttu-id="64c1c-119">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="64c1c-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
