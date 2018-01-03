---
title: "Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства"
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
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d1d504ca056f35fe8716b299ec73f45648bb3d77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="6d126-102">Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства</span><span class="sxs-lookup"><span data-stu-id="6d126-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
>  <span data-ttu-id="6d126-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="6d126-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6d126-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6d126-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6d126-105">В этом разделе содержится пример кода, демонстрирующий способы поиска элемента в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева на основе конкретного свойства или свойств.</span><span class="sxs-lookup"><span data-stu-id="6d126-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d126-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6d126-106">Example</span></span>  
 <span data-ttu-id="6d126-107">В следующем примере набор состояний свойства указаны, которые задают определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дерева.</span><span class="sxs-lookup"><span data-stu-id="6d126-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="6d126-108">Затем выполняется поиск всех соответствующих элементов с <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метод, который включает ряд <xref:System.Windows.Automation.AndCondition> логические операции, чтобы ограничить число соответствующих элементов.</span><span class="sxs-lookup"><span data-stu-id="6d126-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d126-109">При поиске с <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, вы должны пытаться получить только прямые потомки.</span><span class="sxs-lookup"><span data-stu-id="6d126-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="6d126-110">Поиск потомков может выполнить итерацию по сотням или даже тысячам элементов, что может привести к переполнению стека.</span><span class="sxs-lookup"><span data-stu-id="6d126-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="6d126-111">Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.</span><span class="sxs-lookup"><span data-stu-id="6d126-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="6d126-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6d126-112">See Also</span></span>  
 [<span data-ttu-id="6d126-113">InvokePattern и образец элемента меню ExpandCollapsePattern</span><span class="sxs-lookup"><span data-stu-id="6d126-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [<span data-ttu-id="6d126-114">Получение элементов модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6d126-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [<span data-ttu-id="6d126-115">Использование свойства AutomationID</span><span class="sxs-lookup"><span data-stu-id="6d126-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
