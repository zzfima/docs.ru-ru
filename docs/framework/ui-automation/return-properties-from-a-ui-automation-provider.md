---
title: Возврат свойств от поставщика автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: ac5d539f99fe4f7a20d9030986120318840801bb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107952"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="57e1a-102">Возврат свойств от поставщика автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="57e1a-102">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="57e1a-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="57e1a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="57e1a-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="57e1a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="57e1a-105">В этом разделе содержится пример кода, показывающий, как поставщик автоматизации пользовательского интерфейса может возвращать свойства элемента клиентским приложениям.</span><span class="sxs-lookup"><span data-stu-id="57e1a-105">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="57e1a-106">Для любого свойства, которое этот поставщик не поддерживает явным образом, он должен возвращать `null` (`Nothing` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="57e1a-106">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="57e1a-107">Это гарантирует, что [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] будет пытаться получить свойство из другого источника, такого как поставщик основного окна.</span><span class="sxs-lookup"><span data-stu-id="57e1a-107">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57e1a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="57e1a-108">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="57e1a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="57e1a-109">See Also</span></span>  
 [<span data-ttu-id="57e1a-110">Общие сведения о поставщиках автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="57e1a-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="57e1a-111">Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="57e1a-111">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
