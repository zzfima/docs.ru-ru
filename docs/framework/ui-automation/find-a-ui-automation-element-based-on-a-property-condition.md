---
title: Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 24c236e3d577fd4c9844546b04eefeee9eaf1de8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965146"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="d2db1-102">Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства</span><span class="sxs-lookup"><span data-stu-id="d2db1-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="d2db1-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="d2db1-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d2db1-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d2db1-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d2db1-105">В этом разделе содержится пример кода, в котором показано, как можно наыскать элемент в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дереве на основе конкретного свойства или свойств.</span><span class="sxs-lookup"><span data-stu-id="d2db1-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2db1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d2db1-106">Example</span></span>  
 <span data-ttu-id="d2db1-107">В следующем примере задается набор условий свойства, которые определяют определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дереве.</span><span class="sxs-lookup"><span data-stu-id="d2db1-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="d2db1-108">Затем выполняется поиск всех соответствующих элементов с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метода, включающего <xref:System.Windows.Automation.AndCondition> ряд логических операций для ограничения количества совпадающих элементов.</span><span class="sxs-lookup"><span data-stu-id="d2db1-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2db1-109">При поиске из <xref:System.Windows.Automation.AutomationElement.RootElement%2A>необходимо попытаться получить только прямые дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="d2db1-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="d2db1-110">Поиск потомков может осуществлять итерацию сотен или даже тысяч элементов, что может привести к переполнению стека.</span><span class="sxs-lookup"><span data-stu-id="d2db1-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="d2db1-111">Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.</span><span class="sxs-lookup"><span data-stu-id="d2db1-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="d2db1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d2db1-112">See also</span></span>

- <span data-ttu-id="d2db1-113">[Пример пункта меню InvokePattern и ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d2db1-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="d2db1-114">Получение элементов модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d2db1-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [<span data-ttu-id="d2db1-115">Использование свойства AutomationID</span><span class="sxs-lookup"><span data-stu-id="d2db1-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
