---
title: Использование кэширования в модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 679192b611a423e095ee9acc956d247364940edf
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800806"
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="0318e-102">Использование кэширования в модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0318e-102">Use Caching in UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="0318e-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="0318e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0318e-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0318e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0318e-105">В этом разделе показано, как реализовать кэширование шаблонов элементов управления и свойств <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="0318e-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="0318e-106">Активация запроса кэша</span><span class="sxs-lookup"><span data-stu-id="0318e-106">Activate a Cache Request</span></span>  
  
1. <span data-ttu-id="0318e-107">Создайте <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="0318e-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="0318e-108">Укажите свойства и шаблоны для кэширования с помощью <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="0318e-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3. <span data-ttu-id="0318e-109">Укажите область кэширования, установив свойство <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> .</span><span class="sxs-lookup"><span data-stu-id="0318e-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4. <span data-ttu-id="0318e-110">Укажите представление поддерева, установив свойство <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> .</span><span class="sxs-lookup"><span data-stu-id="0318e-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5. <span data-ttu-id="0318e-111">Задайте для свойства <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> значение <xref:System.Windows.Automation.AutomationElementMode.None> , если хотите повысить эффективность, не получая полную ссылку на объекты.</span><span class="sxs-lookup"><span data-stu-id="0318e-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="0318e-112">(Это сделает невозможным получение текущих значений из этих объектов.)</span><span class="sxs-lookup"><span data-stu-id="0318e-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6. <span data-ttu-id="0318e-113">Активируйте запрос с помощью <xref:System.Windows.Automation.CacheRequest.Activate%2A> в блоке `using` (`Using` в Microsoft Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="0318e-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="0318e-114">После получения объекта <xref:System.Windows.Automation.AutomationElement> или подписки на события деактивируйте запрос с помощью <xref:System.Windows.Automation.CacheRequest.Pop%2A> (если использовался <xref:System.Windows.Automation.CacheRequest.Push%2A> ) или удалив объект, созданный <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span><span class="sxs-lookup"><span data-stu-id="0318e-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="0318e-115">(Используйте <xref:System.Windows.Automation.CacheRequest.Activate%2A> в блоке `using` (`Using` в Microsoft Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="0318e-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="0318e-116">Кэширование свойств AutomationElement</span><span class="sxs-lookup"><span data-stu-id="0318e-116">Cache AutomationElement Properties</span></span>  
  
1. <span data-ttu-id="0318e-117">Когда <xref:System.Windows.Automation.CacheRequest> активен, получите объекты <xref:System.Windows.Automation.AutomationElement> с помощью метода <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> или <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; или получите <xref:System.Windows.Automation.AutomationElement> как источник события, для которого вы зарегистрировались, когда был активен <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="0318e-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="0318e-118">(Можно также создать кэш, передав <xref:System.Windows.Automation.CacheRequest> в GetUpdatedCache или в один из методов <xref:System.Windows.Automation.TreeWalker> .)</span><span class="sxs-lookup"><span data-stu-id="0318e-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="0318e-119">Используйте <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> или получите свойство из свойства <xref:System.Windows.Automation.AutomationElement.Cached%2A> элемента <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="0318e-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="0318e-120">Получение кэшированных шаблонов и их свойств</span><span class="sxs-lookup"><span data-stu-id="0318e-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1. <span data-ttu-id="0318e-121">Когда <xref:System.Windows.Automation.CacheRequest> активен, получите объекты <xref:System.Windows.Automation.AutomationElement> с помощью метода <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> или <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; или получите <xref:System.Windows.Automation.AutomationElement> как источник события, для которого вы зарегистрировались, когда был активен <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="0318e-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="0318e-122">(Можно также создать кэш, передав <xref:System.Windows.Automation.CacheRequest> в GetUpdatedCache или в один из методов <xref:System.Windows.Automation.TreeWalker> .)</span><span class="sxs-lookup"><span data-stu-id="0318e-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="0318e-123">Используйте метод <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> для получения кэшированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="0318e-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3. <span data-ttu-id="0318e-124">Получите значения свойства из свойства `Cached` шаблона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0318e-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0318e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0318e-125">Example</span></span>  
 <span data-ttu-id="0318e-126">В следующем примере кода показаны различные аспекты кэширования при использовании метода <xref:System.Windows.Automation.CacheRequest.Activate%2A> для активации <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="0318e-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="0318e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="0318e-127">Example</span></span>  
 <span data-ttu-id="0318e-128">В следующем примере кода показаны различные аспекты кэширования при использовании метода <xref:System.Windows.Automation.CacheRequest.Push%2A> для активации <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="0318e-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="0318e-129">За исключением случая, когда вы хотите вкладывать запросы кэширования, предпочтительнее использовать метод <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span><span class="sxs-lookup"><span data-stu-id="0318e-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="0318e-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="0318e-130">See also</span></span>

- [<span data-ttu-id="0318e-131">Кэширование в клиентах автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0318e-131">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
