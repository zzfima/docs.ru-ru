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
ms.openlocfilehash: 1e148869f619729c72eae67892d4767eed9f8fb3
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042642"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="25232-102">Подписка на события модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="25232-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
> <span data-ttu-id="25232-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="25232-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="25232-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="25232-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="25232-105">В этом разделе показано, как подписаться на события, вызванные поставщиками автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="25232-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25232-106">Пример</span><span class="sxs-lookup"><span data-stu-id="25232-106">Example</span></span>  
 <span data-ttu-id="25232-107">В следующем примере кода регистрируется обработчик событий для события, которое возникает, когда элемент управления, например кнопки, вызывается и удаляется при закрытии формы приложения.</span><span class="sxs-lookup"><span data-stu-id="25232-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="25232-108">Событие идентифицируется по <xref:System.Windows.Automation.AutomationEvent>, переданному в качестве параметра в метод <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="25232-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="25232-109">Пример</span><span class="sxs-lookup"><span data-stu-id="25232-109">Example</span></span>  
 <span data-ttu-id="25232-110">В следующем примере показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для подписки на событие, возникающее при изменении фокуса.</span><span class="sxs-lookup"><span data-stu-id="25232-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="25232-111">Выполняется отмена регистрации обработчика событий в методе, который может вызываться при завершении работы приложения, или когда уведомление о событиях пользовательского интерфейса больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="25232-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="25232-112">См. также</span><span class="sxs-lookup"><span data-stu-id="25232-112">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="25232-113">Общие сведения о событиях модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="25232-113">UI Automation Events Overview</span></span>](ui-automation-events-overview.md)
