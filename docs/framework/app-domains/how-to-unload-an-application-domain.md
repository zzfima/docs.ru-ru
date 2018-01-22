---
title: "Практическое руководство. Выгрузка домена приложения"
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
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 741ddf7c394e1c310e368fe338f71d02a0d4736d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="5c3ab-102">Практическое руководство. Выгрузка домена приложения</span><span class="sxs-lookup"><span data-stu-id="5c3ab-102">How to: Unload an Application Domain</span></span>
<span data-ttu-id="5c3ab-103">После завершения использования домена приложения выгрузите его с помощью метода <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-103">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5c3ab-104">Метод **Unload** безопасно завершает работу указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-104">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="5c3ab-105">В процессе выгрузки новые потоки не могут получить доступ к домену приложения, и освобождаются все структуры данных, определяемые доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-105">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="5c3ab-106">Сборки, загруженные в домен приложения, удаляются и становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-106">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="5c3ab-107">Если сборка в домене приложения не зависит от домена, данные для сборки остаются в памяти, пока не будет завершен весь процесс.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-107">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="5c3ab-108">Не существует механизма для выгрузки независящей от домена сборки, кроме закрытия всего процесса.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-108">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="5c3ab-109">Существуют ситуации, когда запрос на выгрузку домена приложения не работает и возникает исключение <xref:System.CannotUnloadAppDomainException>.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-109">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="5c3ab-110">В следующем примере создается новый домен приложения с именем `MyDomain`, выполняется вывод некоторых данных на консоль, а затем выгрузка домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-110">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="5c3ab-111">Обратите внимание, что код пытается вывести на консоль понятное имя выгруженного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-111">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="5c3ab-112">Это действие создает исключение, которое обрабатывается операторами try/catch в конце программы.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-112">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c3ab-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5c3ab-113">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5c3ab-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5c3ab-114">See Also</span></span>  
 [<span data-ttu-id="5c3ab-115">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="5c3ab-115">Programming with Application Domains</span></span>](http://msdn.microsoft.com/library/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="5c3ab-116">Практическое руководство. Создание домена приложения</span><span class="sxs-lookup"><span data-stu-id="5c3ab-116">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 [<span data-ttu-id="5c3ab-117">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="5c3ab-117">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
