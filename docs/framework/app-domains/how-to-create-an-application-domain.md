---
title: Практическое руководство. Создание домена приложения
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 366dbea0f9559cdeccd2e126e4a3e913fb5ba23d
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="56acb-102">Практическое руководство. Создание домена приложения</span><span class="sxs-lookup"><span data-stu-id="56acb-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="56acb-103">Хост-приложение CLR автоматически создает домены приложений в нужный момент.</span><span class="sxs-lookup"><span data-stu-id="56acb-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="56acb-104">Но можно создать собственные домены приложений и загрузить их в те сборки, которыми требуется управлять отдельно.</span><span class="sxs-lookup"><span data-stu-id="56acb-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="56acb-105">Кроме того, домены приложений можно создать из доменов, выполняющих код.</span><span class="sxs-lookup"><span data-stu-id="56acb-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="56acb-106">Создать домен приложения можно с помощью одного из перегруженных методов **CreateDomain** в классе <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56acb-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="56acb-107">Для домена приложения можно назначить имя и использовать его в ссылках на домен.</span><span class="sxs-lookup"><span data-stu-id="56acb-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="56acb-108">В следующем примере создается новый домен приложения, которому назначается имя `MyDomain`, после чего на консоль выводятся имя основного домена и нового созданного дочернего домена приложения.</span><span class="sxs-lookup"><span data-stu-id="56acb-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56acb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="56acb-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="56acb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="56acb-110">See Also</span></span>  
 [<span data-ttu-id="56acb-111">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="56acb-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
 [<span data-ttu-id="56acb-112">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="56acb-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
