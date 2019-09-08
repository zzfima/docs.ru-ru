---
title: Защита приложений ADO.NET
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 725ba568f3cd482991359237f4fc42b7da99bc0a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795057"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="ad5d1-102">Защита приложений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad5d1-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="ad5d1-103">При написании безопасного приложения ADO.NET следует не просто избегать обычных проблем кодирования, таких как отсутствие проверки входных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="ad5d1-104">В приложении, в котором выполняется обращение к данным, много потенциально уязвимых мест, которые атакующий может использовать для получения конфиденциальных данных, манипулирования ими или их уничтожения.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="ad5d1-105">Поэтому важно понимать все аспекты безопасности, от моделирования угроз на этапе проектирования приложения до развертывания и текущего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="ad5d1-106">.NET Framework предоставляет много полезных классов, служб и средств для обеспечения безопасности и администрирования приложений баз данных.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="ad5d1-107">Среда CLR предоставляет средой типобезопасности для выполняющегося в ней кода. Управление доступом для кода (CAS) позволяет дополнительно ограничить разрешения для управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="ad5d1-108">Следующие приемы безопасного программирования доступа к данным ограничивают ущерб, который может быть нанесен возможным злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="ad5d1-109">Написание безопасного кода не защищает от брешей в безопасности при работе с неуправляемыми ресурсами, такими как базы данных.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="ad5d1-110">Большинство баз данных, таких как SQL Server, имеют свои собственные системы безопасности, повышающие защиту при правильной их реализации.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="ad5d1-111">Но даже источник данных с надежной системой безопасности может быть подвержен атакам, если он не будет настроен должным образом.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad5d1-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ad5d1-112">In This Section</span></span>  
 [<span data-ttu-id="ad5d1-113">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="ad5d1-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="ad5d1-114">Предоставляет рекомендации по проектированию безопасных приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="ad5d1-115">Безопасный доступ к данным</span><span class="sxs-lookup"><span data-stu-id="ad5d1-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="ad5d1-116">Описывает, как работать с данными из защищенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="ad5d1-117">Безопасные клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="ad5d1-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="ad5d1-118">Описывает вопросы безопасности для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="ad5d1-119">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad5d1-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="ad5d1-120">Описывает, как CAS может способствовать защите кода ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="ad5d1-121">Также рассматриваются способы работы с частичным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="ad5d1-122">Конфиденциальность и безопасность данных</span><span class="sxs-lookup"><span data-stu-id="ad5d1-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="ad5d1-123">Описывает параметры шифрования для приложений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad5d1-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ad5d1-124">Related Sections</span></span>  
 [<span data-ttu-id="ad5d1-125">Безопасность SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad5d1-125">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="ad5d1-126">Описывает средства безопасности SQL Server с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="ad5d1-127">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="ad5d1-127">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="ad5d1-128">Описывает средства безопасности для приложений Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="ad5d1-129">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ad5d1-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="ad5d1-130">Содержит ссылки на статьи, в которых описываются все аспекты безопасности в .NET.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="ad5d1-131">[Средства обеспечения безопасности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ad5d1-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="ad5d1-132">Средства .NET Framework для безопасности и администрирования политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="ad5d1-133">[Ресурсы для создания защищенных приложений](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad5d1-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="ad5d1-134">Предоставляет ссылки на разделы, посвященные созданию безопасных приложений.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="ad5d1-135">Библиография по вопросам безопасности</span><span class="sxs-lookup"><span data-stu-id="ad5d1-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="ad5d1-136">Предоставляет ссылки на внешние ресурсы, доступные в Интернете и в печатной форме.</span><span class="sxs-lookup"><span data-stu-id="ad5d1-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5d1-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ad5d1-137">See also</span></span>

- [<span data-ttu-id="ad5d1-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad5d1-138">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ad5d1-139">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad5d1-139">ADO.NET Overview</span></span>](ado-net-overview.md)
