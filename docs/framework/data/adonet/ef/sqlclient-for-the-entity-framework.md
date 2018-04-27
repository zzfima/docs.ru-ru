---
title: SqlClient для Entity Framework
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 2801ad445be073f2cd4725d04a0c731e8bfcdd1b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="c6d1e-102">SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c6d1e-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="c6d1e-103">В этом разделе описан поставщик данных .NET Framework для SQL Server (SqlClient), который позволяет платформе Entity Framework работать с сервером Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="c6d1e-104">Атрибут Provider элемента Schema</span><span class="sxs-lookup"><span data-stu-id="c6d1e-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="c6d1e-105">`Provider` является атрибутом элемента `Schema` в языке SSDL.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="c6d1e-106">Для использования SqlClient нужно присвоить атрибуту `Provider` элемента `Schema` значение в виде строки «System.Data.SqlClient».</span><span class="sxs-lookup"><span data-stu-id="c6d1e-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="c6d1e-107">Атрибут ProviderManifestToken элемента Schema</span><span class="sxs-lookup"><span data-stu-id="c6d1e-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="c6d1e-108">`ProviderManifestToken` - обязательный атрибут элемента `Schema` в SSDL.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="c6d1e-109">Этот маркер используется для загрузки манифеста поставщика при автономном использовании.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="c6d1e-110">Дополнительные сведения о `ProviderManifestToken` см. в разделе [элемент схемы (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).</span><span class="sxs-lookup"><span data-stu-id="c6d1e-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).</span></span>  
  
 <span data-ttu-id="c6d1e-111">SqlClient можно использовать в качестве поставщика данных для разных версий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="c6d1e-112">Эти версии имеют разные возможности.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-112">These versions have different capabilities.</span></span> <span data-ttu-id="c6d1e-113">Например, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] не поддерживает типы `varchar(max)` и `nvarchar(max)`, представленные в [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d1e-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="c6d1e-114">SqlClient формирует и принимает следующие маркеры манифеста поставщика для различных версий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="c6d1e-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="c6d1e-115">SQL Server 2000</span></span>|<span data-ttu-id="c6d1e-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6d1e-116">SQL Server 2005</span></span>|<span data-ttu-id="c6d1e-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="c6d1e-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="c6d1e-118">2000</span><span class="sxs-lookup"><span data-stu-id="c6d1e-118">2000</span></span>|<span data-ttu-id="c6d1e-119">2005</span><span class="sxs-lookup"><span data-stu-id="c6d1e-119">2005</span></span>|<span data-ttu-id="c6d1e-120">2008</span><span class="sxs-lookup"><span data-stu-id="c6d1e-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c6d1e-121">Начиная с [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) не поддерживает SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-121">Starting with [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, the [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="c6d1e-122">Имя пространства имен поставщика</span><span class="sxs-lookup"><span data-stu-id="c6d1e-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="c6d1e-123">Все поставщики должны указывать пространство имен.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-123">All providers must specify a namespace.</span></span> <span data-ttu-id="c6d1e-124">Это свойство сообщает платформе Entity Framework о том, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="c6d1e-125">Пространством имен для манифестов поставщика SqlClient является `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="c6d1e-126">Дополнительные сведения о пространствах имен см. в разделе [пространства имен](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c6d1e-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="c6d1e-127">Типы</span><span class="sxs-lookup"><span data-stu-id="c6d1e-127">Types</span></span>  
 <span data-ttu-id="c6d1e-128">Поставщик SqlClient для платформы Entity Framework предоставляет сведения о сопоставлении между типами концептуальной модели и типами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="c6d1e-129">Дополнительные сведения см. в разделе [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="c6d1e-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="c6d1e-130">Функции</span><span class="sxs-lookup"><span data-stu-id="c6d1e-130">Functions</span></span>  
 <span data-ttu-id="c6d1e-131">Поставщик SqlClient для платформы Entity Framework определяет список функций, поддерживаемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="c6d1e-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="c6d1e-132">Список поддерживаемых функций см. в разделе [функции SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c6d1e-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6d1e-133">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c6d1e-133">In This Section</span></span>  
 [<span data-ttu-id="c6d1e-134">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c6d1e-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="c6d1e-135">Типы SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c6d1e-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="c6d1e-136">Известные проблемы SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c6d1e-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6d1e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c6d1e-137">See Also</span></span>  
 [<span data-ttu-id="c6d1e-138">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c6d1e-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="c6d1e-139">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="c6d1e-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [<span data-ttu-id="c6d1e-140">Известные проблемы в Поставщик SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c6d1e-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
