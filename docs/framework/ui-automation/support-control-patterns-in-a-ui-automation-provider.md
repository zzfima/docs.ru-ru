---
title: Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 65ec0f85bf0a63d0051ff9491623a65abee7a05c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336685"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="fe34f-102">Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fe34f-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="fe34f-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="fe34f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fe34f-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="fe34f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="fe34f-105">В этом разделе показано, как реализовать один или несколько шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса, чтобы клиентские приложения могли работать с элементами управления и получать данные из них.</span><span class="sxs-lookup"><span data-stu-id="fe34f-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="fe34f-106">Поддержка шаблонов элементов управления</span><span class="sxs-lookup"><span data-stu-id="fe34f-106">Support Control Patterns</span></span>  
  
1. <span data-ttu-id="fe34f-107">Реализуйте соответствующие интерфейсы для шаблонов элементов управления, которые должен поддерживать элемент, таких как <xref:System.Windows.Automation.Provider.IInvokeProvider> для <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="fe34f-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2. <span data-ttu-id="fe34f-108">Получите объект, содержащий вашу реализацию каждого интерфейса элемента управления в реализации <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fe34f-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="fe34f-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fe34f-109">Example</span></span>  
 <span data-ttu-id="fe34f-110">В следующем примере показана реализация <xref:System.Windows.Automation.Provider.ISelectionProvider> для пользовательского списка с поддержкой единственного выбора.</span><span class="sxs-lookup"><span data-stu-id="fe34f-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="fe34f-111">Он возвращает три свойства и получает текущий выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="fe34f-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="fe34f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fe34f-112">Example</span></span>  
 <span data-ttu-id="fe34f-113">В следующем примере показана реализация метода <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> , который возвращает класс, реализующий <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span><span class="sxs-lookup"><span data-stu-id="fe34f-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="fe34f-114">Большинство элементов управления полей списка будут поддерживать другие шаблоны, также, но в этом примере ссылкой на null (`Nothing` в Microsoft Visual Basic .NET) возвращается для всех остальных идентификаторов шаблонов.</span><span class="sxs-lookup"><span data-stu-id="fe34f-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="fe34f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fe34f-115">See also</span></span>

- [<span data-ttu-id="fe34f-116">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fe34f-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="fe34f-117">Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="fe34f-117">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
