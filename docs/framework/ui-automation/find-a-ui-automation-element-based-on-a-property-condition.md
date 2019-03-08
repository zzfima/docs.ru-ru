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
ms.openlocfilehash: 83d3a36d08463cedf46c176208625e76907db2d8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675112"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="2c8e5-102">Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства</span><span class="sxs-lookup"><span data-stu-id="2c8e5-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
>  <span data-ttu-id="2c8e5-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="2c8e5-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2c8e5-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="2c8e5-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="2c8e5-105">В этом разделе содержится пример кода, показано, как найти элемент в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева на основе конкретного свойства или свойств.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c8e5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2c8e5-106">Example</span></span>  
 <span data-ttu-id="2c8e5-107">В следующем примере набор условий свойства указываются, которые задают определенный элемент (или элементов), интерес в <xref:System.Windows.Automation.AutomationElement> дерева.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="2c8e5-108">Затем выполняется поиск всех соответствующих элементов с <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метод, который включает ряд <xref:System.Windows.Automation.AndCondition> логических операций, чтобы ограничить число найденных элементов.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c8e5-109">При поиске по указанию <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, следует попытаться получить только прямые потомки.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="2c8e5-110">Поиск потомков может выполнить итерацию сотни или даже тысячи элементов, что может привести к переполнению стека.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="2c8e5-111">Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.</span><span class="sxs-lookup"><span data-stu-id="2c8e5-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="2c8e5-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2c8e5-112">See also</span></span>
- <span data-ttu-id="2c8e5-113">[InvokePattern и образец элемента меню ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2c8e5-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="2c8e5-114">Получение элементов модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="2c8e5-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [<span data-ttu-id="2c8e5-115">Использование свойства AutomationID</span><span class="sxs-lookup"><span data-stu-id="2c8e5-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
