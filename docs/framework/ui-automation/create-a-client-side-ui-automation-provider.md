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
ms.openlocfilehash: 03f64386271565b3494b9dac42cf969fc777e40b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211313"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="cb4f9-102">Создание поставщика модели автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="cb4f9-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="cb4f9-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="cb4f9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cb4f9-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="cb4f9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="cb4f9-105">В этом разделе содержится пример кода, демонстрирующий реализацию клиентского поставщика автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4f9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="cb4f9-106">Example</span></span>  
 <span data-ttu-id="cb4f9-107">Следующий пример кода может быть встроен в [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] , реализующую очень простого клиентского поставщика для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="cb4f9-108">Код не имеет никаких полезных функциональных возможностей, он предназначен для демонстрации основных действий по настройке сборки поставщика, которая может быть зарегистрирована клиентским приложением модели автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="cb4f9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cb4f9-109">See also</span></span>

- [<span data-ttu-id="cb4f9-110">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="cb4f9-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="cb4f9-111">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="cb4f9-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
