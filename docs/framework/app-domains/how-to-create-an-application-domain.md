---
title: "Практическое руководство. Создание домена приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 39d8db32f82827e76d9517d387e2fc001fc209aa
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="534c5-102">Практическое руководство. Создание домена приложения</span><span class="sxs-lookup"><span data-stu-id="534c5-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="534c5-103">Хост-приложение CLR автоматически создает домены приложений в нужный момент.</span><span class="sxs-lookup"><span data-stu-id="534c5-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="534c5-104">Но можно создать собственные домены приложений и загрузить их в те сборки, которыми требуется управлять отдельно.</span><span class="sxs-lookup"><span data-stu-id="534c5-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="534c5-105">Кроме того, домены приложений можно создать из доменов, выполняющих код.</span><span class="sxs-lookup"><span data-stu-id="534c5-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="534c5-106">Создать домен приложения можно с помощью одного из перегруженных методов **CreateDomain** в классе <xref:System.AppDomain?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="534c5-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=fullName> class.</span></span> <span data-ttu-id="534c5-107">Для домена приложения можно назначить имя и использовать его в ссылках на домен.</span><span class="sxs-lookup"><span data-stu-id="534c5-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="534c5-108">В следующем примере создается новый домен приложения, которому назначается имя `MyDomain`, после чего на консоль выводятся имя основного домена и нового созданного дочернего домена приложения.</span><span class="sxs-lookup"><span data-stu-id="534c5-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="534c5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="534c5-109">Example</span></span>  
 <span data-ttu-id="534c5-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="534c5-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534c5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="534c5-111">See Also</span></span>  
 <span data-ttu-id="534c5-112">[Программирование с использованием доменов приложений](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="534c5-112">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 [<span data-ttu-id="534c5-113">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="534c5-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

