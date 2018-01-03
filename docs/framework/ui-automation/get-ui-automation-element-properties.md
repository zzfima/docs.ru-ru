---
title: "Получение свойств элементов управления модели автоматизации пользовательского интерфейса"
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
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f3fcbb25fab616b60a1f60d9443af13b60f2d27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="5ebe9-102">Получение свойств элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5ebe9-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="5ebe9-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="5ebe9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5ebe9-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5ebe9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5ebe9-105">В этом разделе показано, как извлекать свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="5ebe9-106">Получение текущего значения свойства</span><span class="sxs-lookup"><span data-stu-id="5ebe9-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="5ebe9-107">Получить <xref:System.Windows.Automation.AutomationElement> , свойство которого нужно получить.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="5ebe9-108">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, или получить <xref:System.Windows.Automation.AutomationElement.Current%2A> структуры свойства и значение из одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="5ebe9-109">Получение кэшированного значения свойства</span><span class="sxs-lookup"><span data-stu-id="5ebe9-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="5ebe9-110">Получить <xref:System.Windows.Automation.AutomationElement> , свойство которого нужно получить.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="5ebe9-111">Свойство должно быть указано в <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="5ebe9-112">Вызовите <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, или получить <xref:System.Windows.Automation.AutomationElement.Cached%2A> структуры свойства и значение из одного из его членов.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ebe9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5ebe9-113">Example</span></span>  
 <span data-ttu-id="5ebe9-114">В следующем примере показаны различные способы извлечения текущих свойств объекта <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="5ebe9-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="5ebe9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5ebe9-115">See Also</span></span>  
 [<span data-ttu-id="5ebe9-116">Свойства автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="5ebe9-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="5ebe9-117">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5ebe9-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="5ebe9-118">Кэширование в клиентах автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5ebe9-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
