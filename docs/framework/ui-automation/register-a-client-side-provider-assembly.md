---
title: "Регистрация сборки поставщика на стороне клиента"
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
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
caps.latest.revision: "8"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 638e7b07c159bf1daf91428a1b95a4e83f61dace
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="f4642-102">Регистрация сборки поставщика на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="f4642-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
>  <span data-ttu-id="f4642-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="f4642-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f4642-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f4642-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f4642-105">В этом разделе показано, как зарегистрировать библиотеку DLL, содержащую поставщики автоматизации пользовательского интерфейса на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="f4642-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4642-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f4642-106">Example</span></span>  
 <span data-ttu-id="f4642-107">В следующем примере показано, как зарегистрировать сборку, содержащую поставщик для окна консоли.</span><span class="sxs-lookup"><span data-stu-id="f4642-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="f4642-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f4642-108">See Also</span></span>  
 [<span data-ttu-id="f4642-109">Создание поставщика автоматизации пользовательского интерфейса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="f4642-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
