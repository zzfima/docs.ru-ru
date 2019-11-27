---
title: Подписка на события модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: a5effd1d7a3cfaba5e068087b3008903e58b6739
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432989"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="c47f9-102">Подписка на события модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c47f9-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
> <span data-ttu-id="c47f9-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="c47f9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c47f9-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="c47f9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c47f9-105">В этом разделе показано, как подписаться на события, вызванные поставщиками автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c47f9-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c47f9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="c47f9-106">Example</span></span>  
 <span data-ttu-id="c47f9-107">В следующем примере кода регистрируется обработчик событий для события, которое возникает, когда элемент управления, например кнопки, вызывается и удаляется при закрытии формы приложения.</span><span class="sxs-lookup"><span data-stu-id="c47f9-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="c47f9-108">Событие идентифицируется по <xref:System.Windows.Automation.AutomationEvent>, переданному в качестве параметра в метод <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="c47f9-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="c47f9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c47f9-109">Example</span></span>  
 <span data-ttu-id="c47f9-110">В следующем примере показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для подписки на событие, возникающее при изменении фокуса.</span><span class="sxs-lookup"><span data-stu-id="c47f9-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="c47f9-111">Выполняется отмена регистрации обработчика событий в методе, который может вызываться при завершении работы приложения, или когда уведомление о событиях пользовательского интерфейса больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="c47f9-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="c47f9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c47f9-112">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="c47f9-113">Общие сведения о событиях модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c47f9-113">UI Automation Events Overview</span></span>](ui-automation-events-overview.md)
