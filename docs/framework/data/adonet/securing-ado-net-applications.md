---
title: Защита приложений ADO.NET
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: e5b99621989e9f14c6c734a497f210780f3c7e57
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526973"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="a90c2-102">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a90c2-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="a90c2-103">При написании безопасного приложения ADO.NET следует не просто избегать обычных проблем кодирования, таких как отсутствие проверки входных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="a90c2-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="a90c2-104">В приложении, в котором выполняется обращение к данным, много потенциально уязвимых мест, которые атакующий может использовать для получения конфиденциальных данных, манипулирования ими или их уничтожения.</span><span class="sxs-lookup"><span data-stu-id="a90c2-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="a90c2-105">Поэтому важно понимать все аспекты безопасности, от моделирования угроз на этапе проектирования приложения до развертывания и текущего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a90c2-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="a90c2-106">.NET Framework предоставляет много полезных классов, служб и средств для обеспечения безопасности и администрирования приложений баз данных.</span><span class="sxs-lookup"><span data-stu-id="a90c2-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="a90c2-107">Среда CLR предоставляет средой типобезопасности для выполняющегося в ней кода. Управление доступом для кода (CAS) позволяет дополнительно ограничить разрешения для управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="a90c2-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="a90c2-108">Следующие приемы безопасного программирования доступа к данным ограничивают ущерб, который может быть нанесен возможным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="a90c2-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="a90c2-109">Написание безопасного кода не защищает от брешей в безопасности при работе с неуправляемыми ресурсами, такими как базы данных.</span><span class="sxs-lookup"><span data-stu-id="a90c2-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="a90c2-110">Большинство баз данных, таких как SQL Server, имеют свои собственные системы безопасности, повышающие защиту при правильной их реализации.</span><span class="sxs-lookup"><span data-stu-id="a90c2-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="a90c2-111">Но даже источник данных с надежной системой безопасности может быть подвержен атакам, если он не будет настроен должным образом.</span><span class="sxs-lookup"><span data-stu-id="a90c2-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a90c2-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a90c2-112">In This Section</span></span>  
 [<span data-ttu-id="a90c2-113">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="a90c2-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="a90c2-114">Предоставляет рекомендации по проектированию безопасных приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a90c2-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="a90c2-115">Безопасный доступ к данным</span><span class="sxs-lookup"><span data-stu-id="a90c2-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="a90c2-116">Описывает, как работать с данными из защищенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="a90c2-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="a90c2-117">Безопасные клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="a90c2-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="a90c2-118">Описывает вопросы безопасности для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="a90c2-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="a90c2-119">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a90c2-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="a90c2-120">Описывает, как CAS может способствовать защите кода ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a90c2-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="a90c2-121">Также рассматриваются способы работы с частичным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="a90c2-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="a90c2-122">Конфиденциальность и безопасность данных</span><span class="sxs-lookup"><span data-stu-id="a90c2-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="a90c2-123">Описывает параметры шифрования для приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a90c2-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a90c2-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a90c2-124">Related Sections</span></span>  
 [<span data-ttu-id="a90c2-125">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="a90c2-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="a90c2-126">Описывает средства безопасности SQL Server с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="a90c2-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="a90c2-127">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="a90c2-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="a90c2-128">Описывает средства безопасности для приложений Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a90c2-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="a90c2-129">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a90c2-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="a90c2-130">Содержит ссылки на статьи, в которых описываются все аспекты безопасности в .NET.</span><span class="sxs-lookup"><span data-stu-id="a90c2-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 [<span data-ttu-id="a90c2-131">Средства обеспечения безопасности</span><span class="sxs-lookup"><span data-stu-id="a90c2-131">Security Tools</span></span>](https://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 <span data-ttu-id="a90c2-132">Средства .NET Framework для безопасности и администрирования политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="a90c2-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 [<span data-ttu-id="a90c2-133">Ресурсы для создания защищенных приложений</span><span class="sxs-lookup"><span data-stu-id="a90c2-133">Resources for Creating Secure Applications</span></span>](https://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 <span data-ttu-id="a90c2-134">Предоставляет ссылки на разделы, посвященные созданию безопасных приложений.</span><span class="sxs-lookup"><span data-stu-id="a90c2-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="a90c2-135">Библиография по вопросам безопасности</span><span class="sxs-lookup"><span data-stu-id="a90c2-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="a90c2-136">Предоставляет ссылки на внешние ресурсы, доступные в Интернете и в печатной форме.</span><span class="sxs-lookup"><span data-stu-id="a90c2-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90c2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a90c2-137">See Also</span></span>  
 [<span data-ttu-id="a90c2-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a90c2-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="a90c2-139">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a90c2-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
