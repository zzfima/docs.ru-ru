---
title: Защита приложений
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: c1bdf4329665e4d29a47c26fb7dba8eb41c1cc3a
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980032"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="d126b-102">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d126b-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="d126b-103">При написании безопасного приложения ADO.NET следует не просто избегать обычных проблем кодирования, таких как отсутствие проверки входных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="d126b-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="d126b-104">В приложении, в котором выполняется обращение к данным, много потенциально уязвимых мест, которые атакующий может использовать для получения конфиденциальных данных, манипулирования ими или их уничтожения.</span><span class="sxs-lookup"><span data-stu-id="d126b-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="d126b-105">Поэтому важно понимать все аспекты безопасности, от моделирования угроз на этапе проектирования приложения до развертывания и текущего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d126b-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="d126b-106">.NET Framework предоставляет много полезных классов, служб и средств для обеспечения безопасности и администрирования приложений баз данных.</span><span class="sxs-lookup"><span data-stu-id="d126b-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="d126b-107">Среда CLR предоставляет средой типобезопасности для выполняющегося в ней кода. Управление доступом для кода (CAS) позволяет дополнительно ограничить разрешения для управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d126b-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="d126b-108">Следующие приемы безопасного программирования доступа к данным ограничивают ущерб, который может быть нанесен возможным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="d126b-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="d126b-109">Написание безопасного кода не защищает от брешей в безопасности при работе с неуправляемыми ресурсами, такими как базы данных.</span><span class="sxs-lookup"><span data-stu-id="d126b-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="d126b-110">Большинство баз данных, таких как SQL Server, имеют свои собственные системы безопасности, повышающие защиту при правильной их реализации.</span><span class="sxs-lookup"><span data-stu-id="d126b-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="d126b-111">Но даже источник данных с надежной системой безопасности может быть подвержен атакам, если он не будет настроен должным образом.</span><span class="sxs-lookup"><span data-stu-id="d126b-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d126b-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d126b-112">In This Section</span></span>  
 [<span data-ttu-id="d126b-113">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="d126b-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="d126b-114">Предоставляет рекомендации по проектированию безопасных приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d126b-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="d126b-115">Безопасный доступ к данным</span><span class="sxs-lookup"><span data-stu-id="d126b-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="d126b-116">Описывает, как работать с данными из защищенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="d126b-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="d126b-117">Безопасные клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="d126b-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="d126b-118">Описывает вопросы безопасности для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="d126b-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="d126b-119">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d126b-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="d126b-120">Описывает, как CAS может способствовать защите кода ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d126b-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="d126b-121">Также рассматриваются способы работы с частичным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="d126b-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="d126b-122">Конфиденциальность и безопасность данных</span><span class="sxs-lookup"><span data-stu-id="d126b-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="d126b-123">Описывает параметры шифрования для приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d126b-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d126b-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d126b-124">Related Sections</span></span>  
 [<span data-ttu-id="d126b-125">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="d126b-125">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="d126b-126">Описывает средства безопасности SQL Server с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="d126b-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="d126b-127">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="d126b-127">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="d126b-128">Описывает средства безопасности для приложений Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d126b-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="d126b-129">Security</span><span class="sxs-lookup"><span data-stu-id="d126b-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="d126b-130">Содержит ссылки на статьи, в которых описываются все аспекты безопасности в .NET.</span><span class="sxs-lookup"><span data-stu-id="d126b-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="d126b-131">[Средства обеспечения безопасности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d126b-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="d126b-132">Средства .NET Framework для безопасности и администрирования политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="d126b-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="d126b-133">[Ресурсы для создания защищенных приложений](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d126b-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="d126b-134">Предоставляет ссылки на разделы, посвященные созданию безопасных приложений.</span><span class="sxs-lookup"><span data-stu-id="d126b-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="d126b-135">Библиография по вопросам безопасности</span><span class="sxs-lookup"><span data-stu-id="d126b-135">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="d126b-136">Предоставляет ссылки на внешние ресурсы, доступные в Интернете и в печатной форме.</span><span class="sxs-lookup"><span data-stu-id="d126b-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d126b-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="d126b-137">See also</span></span>

- [<span data-ttu-id="d126b-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d126b-138">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="d126b-139">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d126b-139">ADO.NET Overview</span></span>](ado-net-overview.md)
