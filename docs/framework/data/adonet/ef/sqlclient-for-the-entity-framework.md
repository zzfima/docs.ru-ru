---
title: SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: ec67637c416f2560c1f5d0a9fd0e856703820a84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69954973"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="d527d-102">SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d527d-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="d527d-103">В этом разделе описан поставщик данных .NET Framework для SQL Server (SqlClient), который позволяет платформе Entity Framework работать с сервером Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d527d-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="d527d-104">Атрибут Provider элемента Schema</span><span class="sxs-lookup"><span data-stu-id="d527d-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="d527d-105">`Provider` является атрибутом элемента `Schema` в языке SSDL.</span><span class="sxs-lookup"><span data-stu-id="d527d-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="d527d-106">Для использования SqlClient нужно присвоить атрибуту `Provider` элемента `Schema` значение в виде строки «System.Data.SqlClient».</span><span class="sxs-lookup"><span data-stu-id="d527d-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="d527d-107">Атрибут ProviderManifestToken элемента Schema</span><span class="sxs-lookup"><span data-stu-id="d527d-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="d527d-108">`ProviderManifestToken` - обязательный атрибут элемента `Schema` в SSDL.</span><span class="sxs-lookup"><span data-stu-id="d527d-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="d527d-109">Этот маркер используется для загрузки манифеста поставщика при автономном использовании.</span><span class="sxs-lookup"><span data-stu-id="d527d-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="d527d-110">Дополнительные сведения об `ProviderManifestToken` атрибуте см. в разделе [элемент Schema (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="d527d-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="d527d-111">SqlClient можно использовать в качестве поставщика данных для разных версий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d527d-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="d527d-112">Эти версии имеют разные возможности.</span><span class="sxs-lookup"><span data-stu-id="d527d-112">These versions have different capabilities.</span></span> <span data-ttu-id="d527d-113">Например, SQL Server 2000 не поддерживает `varchar(max)` типы и `nvarchar(max)` , которые появились в SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="d527d-113">For example, SQL Server 2000 does not support `varchar(max)` and `nvarchar(max)` types that were introduced with SQL Server 2005.</span></span>  
  
 <span data-ttu-id="d527d-114">SqlClient формирует и принимает следующие маркеры манифеста поставщика для различных версий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d527d-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="d527d-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="d527d-115">SQL Server 2000</span></span>|<span data-ttu-id="d527d-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="d527d-116">SQL Server 2005</span></span>|<span data-ttu-id="d527d-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d527d-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="d527d-118">2000</span><span class="sxs-lookup"><span data-stu-id="d527d-118">2000</span></span>|<span data-ttu-id="d527d-119">2005</span><span class="sxs-lookup"><span data-stu-id="d527d-119">2005</span></span>|<span data-ttu-id="d527d-120">2008</span><span class="sxs-lookup"><span data-stu-id="d527d-120">2008</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d527d-121">Начиная с Visual Studio 2010 [средства ADO.NET EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) не поддерживают SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="d527d-121">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="d527d-122">Имя пространства имен поставщика</span><span class="sxs-lookup"><span data-stu-id="d527d-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="d527d-123">Все поставщики должны указывать пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d527d-123">All providers must specify a namespace.</span></span> <span data-ttu-id="d527d-124">Это свойство сообщает платформе Entity Framework о том, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции.</span><span class="sxs-lookup"><span data-stu-id="d527d-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="d527d-125">Пространством имен для манифестов поставщика SqlClient является `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="d527d-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="d527d-126">Дополнительные сведения о пространствах имен см. в разделе [пространства имен](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d527d-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="d527d-127">Типы</span><span class="sxs-lookup"><span data-stu-id="d527d-127">Types</span></span>  
 <span data-ttu-id="d527d-128">Поставщик SqlClient для платформы Entity Framework предоставляет сведения о сопоставлении между типами концептуальной модели и типами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d527d-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="d527d-129">Дополнительные сведения см. в разделе [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="d527d-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="d527d-130">Функции</span><span class="sxs-lookup"><span data-stu-id="d527d-130">Functions</span></span>  
 <span data-ttu-id="d527d-131">Поставщик SqlClient для платформы Entity Framework определяет список функций, поддерживаемых поставщиком.</span><span class="sxs-lookup"><span data-stu-id="d527d-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="d527d-132">Список поддерживаемых функций см. в разделе [SqlClient for Entity Framework functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d527d-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d527d-133">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d527d-133">In This Section</span></span>  
 [<span data-ttu-id="d527d-134">Функции SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d527d-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="d527d-135">Типы SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d527d-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="d527d-136">Известные проблемы SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d527d-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="d527d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d527d-137">See also</span></span>

- [<span data-ttu-id="d527d-138">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d527d-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="d527d-139">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="d527d-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [<span data-ttu-id="d527d-140">Известные проблемы в поставщике SqlClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d527d-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
