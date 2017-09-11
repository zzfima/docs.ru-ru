---
title: "Извлечение сведений о настройке из домена приложения"
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
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 865ae7b5cb005a5fc4fef283d63527b028253ad6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="retrieving-setup-information-from-an-application-domain"></a><span data-ttu-id="94902-102">Извлечение сведений о настройке из домена приложения</span><span class="sxs-lookup"><span data-stu-id="94902-102">Retrieving Setup Information from an Application Domain</span></span>
<span data-ttu-id="94902-103">Каждый экземпляр домена приложения содержит свойства и сведения <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="94902-103">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="94902-104">Сведения о настройке можно получить из домена приложения с помощью класса <xref:System.AppDomain?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="94902-104">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=fullName> class.</span></span> <span data-ttu-id="94902-105">Этот класс предоставляет несколько членов, извлекающих сведения конфигурации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="94902-105">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="94902-106">Кроме того, для получения сведений о настройке домена приложения можно выполнить запрос объекта **AppDomainSetup**, который был передан в домен при его создании.</span><span class="sxs-lookup"><span data-stu-id="94902-106">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="94902-107">В следующем примере создается домен приложения и выполняется вывод значений нескольких его членов на консоль.</span><span class="sxs-lookup"><span data-stu-id="94902-107">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 <span data-ttu-id="94902-108">[!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)] [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)] [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="94902-108">[!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)] [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)] [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]</span></span>  
  
 <span data-ttu-id="94902-109">В следующем примере для домена приложения задаются и извлекаются сведения о настройке.</span><span class="sxs-lookup"><span data-stu-id="94902-109">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="94902-110">Обратите внимание, что `AppDomain.SetupInformation.ApplicationBase` получает сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="94902-110">Note that `AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 <span data-ttu-id="94902-111">[!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)] [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)] [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="94902-111">[!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)] [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)] [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94902-112">См. также</span><span class="sxs-lookup"><span data-stu-id="94902-112">See Also</span></span>  
 <span data-ttu-id="94902-113">[Программирование с использованием доменов приложений](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="94902-113">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 [<span data-ttu-id="94902-114">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="94902-114">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

