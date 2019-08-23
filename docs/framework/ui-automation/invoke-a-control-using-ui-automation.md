---
title: Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: f17f3ad25f137bbf8d7cf88b43cc52dfdeeb3fd4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923727"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="075b0-102">Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="075b0-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="075b0-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="075b0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="075b0-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="075b0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="075b0-105">В этом примере показано выполнение следующих задач.</span><span class="sxs-lookup"><span data-stu-id="075b0-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="075b0-106">Поиск элемента управления, который соответствует конкретным условиям свойств путем прохода представления элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="075b0-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="075b0-107">Создание <xref:System.Windows.Automation.AutomationElement> для каждого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="075b0-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="075b0-108">Получение объекта <xref:System.Windows.Automation.InvokePattern> из любого найденного элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , который поддерживает шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="075b0-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="075b0-109">Использование <xref:System.Windows.Automation.InvokePattern.Invoke%2A> для вызова элемента управления из обработчика событий клиента.</span><span class="sxs-lookup"><span data-stu-id="075b0-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="075b0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="075b0-110">Example</span></span>  
 <span data-ttu-id="075b0-111">В этом примере используется метод <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> класса <xref:System.Windows.Automation.AutomationElement> для создания объекта <xref:System.Windows.Automation.InvokePattern> и вызова элемента управления с помощью метода <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="075b0-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="075b0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="075b0-112">See also</span></span>

- [<span data-ttu-id="075b0-113">Пример InvokePattern, ExpandCollapsePattern и Тогглепаттерн</span><span class="sxs-lookup"><span data-stu-id="075b0-113">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
