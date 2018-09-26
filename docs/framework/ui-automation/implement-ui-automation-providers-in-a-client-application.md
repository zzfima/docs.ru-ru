---
title: Реализация поставщиков UI Automation в в приложении клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: becd247e07a2ece2865251e7a8bbd10f0750ddb3
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086386"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="8c33a-102">Реализация поставщиков UI Automation в в приложении клиента</span><span class="sxs-lookup"><span data-stu-id="8c33a-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="8c33a-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="8c33a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8c33a-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8c33a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8c33a-105">В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса в приложении.</span><span class="sxs-lookup"><span data-stu-id="8c33a-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="8c33a-106">Это происходит редко.</span><span class="sxs-lookup"><span data-stu-id="8c33a-106">This is an uncommon scenario.</span></span> <span data-ttu-id="8c33a-107">Чаще всего клиентское приложение автоматизации пользовательского интерфейса использует поставщики на стороне сервера или поставщики на стороне клиента, которые находятся в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="8c33a-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c33a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8c33a-108">Example</span></span>  
 <span data-ttu-id="8c33a-109">В следующем примере кода реализуется простой поставщик для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="8c33a-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="8c33a-110">Этот код не имеет никаких полезных функциональных возможностей, но он предназначен для демонстрации основных действий по настройке поставщика в коде клиента и его регистрации с помощью метода <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c33a-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="8c33a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8c33a-111">See Also</span></span>  
 [<span data-ttu-id="8c33a-112">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8c33a-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="8c33a-113">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="8c33a-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)  
 [<span data-ttu-id="8c33a-114">Создание поставщика автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="8c33a-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [<span data-ttu-id="8c33a-115">Реализация клиентского поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8c33a-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
