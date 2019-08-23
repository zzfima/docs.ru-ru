---
title: Получение свойств элементов управления модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968965"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="ece2d-102">Получение свойств элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ece2d-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="ece2d-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="ece2d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ece2d-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ece2d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ece2d-105">В этом разделе показано, как получить свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента.</span><span class="sxs-lookup"><span data-stu-id="ece2d-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="ece2d-106">Получение значения текущего свойства</span><span class="sxs-lookup"><span data-stu-id="ece2d-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="ece2d-107">Получите объект <xref:System.Windows.Automation.AutomationElement> , свойство которого вы хотите получить.</span><span class="sxs-lookup"><span data-stu-id="ece2d-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="ece2d-108">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>или <xref:System.Windows.Automation.AutomationElement.Current%2A> извлеките структуру свойства и получите значение от одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="ece2d-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="ece2d-109">Получение значения кэшированного свойства</span><span class="sxs-lookup"><span data-stu-id="ece2d-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="ece2d-110">Получите объект <xref:System.Windows.Automation.AutomationElement> , свойство которого вы хотите получить.</span><span class="sxs-lookup"><span data-stu-id="ece2d-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="ece2d-111">Свойство должно быть указано в <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="ece2d-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="ece2d-112">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>или <xref:System.Windows.Automation.AutomationElement.Cached%2A> извлеките структуру свойства и получите значение от одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="ece2d-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ece2d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ece2d-113">Example</span></span>  
 <span data-ttu-id="ece2d-114">В следующем примере показаны различные способы получения текущих свойств <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="ece2d-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="ece2d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ece2d-115">See also</span></span>

- [<span data-ttu-id="ece2d-116">Свойства автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="ece2d-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="ece2d-117">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ece2d-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="ece2d-118">Кэширование в клиентах автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ece2d-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
