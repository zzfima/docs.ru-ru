---
title: Защита приложений ADO.NET
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 32d3de15242aaf9cfacd9371289a5a0a675f884b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149387"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="1b4df-102">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b4df-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="1b4df-103">При написании безопасного приложения ADO.NET следует не просто избегать обычных проблем кодирования, таких как отсутствие проверки входных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b4df-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="1b4df-104">В приложении, в котором выполняется обращение к данным, много потенциально уязвимых мест, которые атакующий может использовать для получения конфиденциальных данных, манипулирования ими или их уничтожения.</span><span class="sxs-lookup"><span data-stu-id="1b4df-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="1b4df-105">Поэтому важно понимать все аспекты безопасности, от моделирования угроз на этапе проектирования приложения до развертывания и текущего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="1b4df-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="1b4df-106">.NET Framework предоставляет много полезных классов, служб и средств для обеспечения безопасности и администрирования приложений баз данных.</span><span class="sxs-lookup"><span data-stu-id="1b4df-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="1b4df-107">Среда CLR предоставляет средой типобезопасности для выполняющегося в ней кода. Управление доступом для кода (CAS) позволяет дополнительно ограничить разрешения для управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="1b4df-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="1b4df-108">Следующие приемы безопасного программирования доступа к данным ограничивают ущерб, который может быть нанесен возможным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="1b4df-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="1b4df-109">Написание безопасного кода не защищает от брешей в безопасности при работе с неуправляемыми ресурсами, такими как базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b4df-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="1b4df-110">Большинство баз данных, таких как SQL Server, имеют свои собственные системы безопасности, повышающие защиту при правильной их реализации.</span><span class="sxs-lookup"><span data-stu-id="1b4df-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="1b4df-111">Но даже источник данных с надежной системой безопасности может быть подвержен атакам, если он не будет настроен должным образом.</span><span class="sxs-lookup"><span data-stu-id="1b4df-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b4df-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1b4df-112">In This Section</span></span>  
 [<span data-ttu-id="1b4df-113">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="1b4df-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="1b4df-114">Предоставляет рекомендации по проектированию безопасных приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1b4df-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="1b4df-115">Безопасный доступ к данным</span><span class="sxs-lookup"><span data-stu-id="1b4df-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="1b4df-116">Описывает, как работать с данными из защищенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="1b4df-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="1b4df-117">Безопасные клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="1b4df-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="1b4df-118">Описывает вопросы безопасности для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="1b4df-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="1b4df-119">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b4df-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="1b4df-120">Описывает, как CAS может способствовать защите кода ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1b4df-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="1b4df-121">Также рассматриваются способы работы с частичным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="1b4df-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="1b4df-122">Конфиденциальность и безопасность данных</span><span class="sxs-lookup"><span data-stu-id="1b4df-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="1b4df-123">Описывает параметры шифрования для приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1b4df-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1b4df-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1b4df-124">Related Sections</span></span>  
 [<span data-ttu-id="1b4df-125">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b4df-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="1b4df-126">Описывает средства безопасности SQL Server с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="1b4df-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="1b4df-127">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="1b4df-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="1b4df-128">Описывает средства безопасности для приложений Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1b4df-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="1b4df-129">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1b4df-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="1b4df-130">Содержит ссылки на статьи, в которых описываются все аспекты безопасности в .NET.</span><span class="sxs-lookup"><span data-stu-id="1b4df-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="1b4df-131">[Средства обеспечения безопасности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1b4df-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="1b4df-132">Средства .NET Framework для безопасности и администрирования политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="1b4df-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="1b4df-133">[Ресурсы для создания защищенных приложений](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b4df-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="1b4df-134">Предоставляет ссылки на разделы, посвященные созданию безопасных приложений.</span><span class="sxs-lookup"><span data-stu-id="1b4df-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="1b4df-135">Библиография по вопросам безопасности</span><span class="sxs-lookup"><span data-stu-id="1b4df-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="1b4df-136">Предоставляет ссылки на внешние ресурсы, доступные в Интернете и в печатной форме.</span><span class="sxs-lookup"><span data-stu-id="1b4df-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4df-137">См. также</span><span class="sxs-lookup"><span data-stu-id="1b4df-137">See also</span></span>

- [<span data-ttu-id="1b4df-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b4df-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="1b4df-139">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b4df-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
