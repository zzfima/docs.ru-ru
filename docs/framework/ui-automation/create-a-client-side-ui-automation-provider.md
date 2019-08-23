---
title: Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: f9f7258c272ada867b406c5615c5d2d52e1d98a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937915"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="d22a8-102">Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="d22a8-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="d22a8-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="d22a8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d22a8-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d22a8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d22a8-105">В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d22a8-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d22a8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d22a8-106">Example</span></span>  
 <span data-ttu-id="d22a8-107">Приведенный ниже пример кода можно встроить в библиотеку динамической компоновки (DLL), которая реализует очень простой поставщик на стороне клиента для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="d22a8-107">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="d22a8-108">Код не имеет никаких полезных функциональных возможностей, он предназначен для демонстрации основных действий по настройке сборки поставщика, которая может быть зарегистрирована клиентским приложением модели автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d22a8-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="d22a8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d22a8-109">See also</span></span>

- [<span data-ttu-id="d22a8-110">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d22a8-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="d22a8-111">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="d22a8-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
