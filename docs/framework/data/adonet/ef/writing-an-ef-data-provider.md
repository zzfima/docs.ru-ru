---
title: "Создание поставщика данных Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a316ae288d677a0ad5bd602399e27389839ef092
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="6946a-102">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6946a-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="6946a-103">В этом разделе описывается порядок написания поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] для поддержки источников данных, за исключением [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6946a-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6946a-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] имеет поставщика, поддерживающего [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6946a-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="6946a-105">Знакомство с моделью поставщика Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6946a-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="6946a-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] не зависит от баз данных, написать поставщика для подключения к различным источникам данных можно при помощи модели поставщика ADO.NE.</span><span class="sxs-lookup"><span data-stu-id="6946a-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="6946a-107">Поставщик данных Entity Framework (созданный при помощи модели поставщика ADO.NET) выполняет следующие функции.</span><span class="sxs-lookup"><span data-stu-id="6946a-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="6946a-108">Сопоставляет примитивные типы модели EDM с типами поставщика.</span><span class="sxs-lookup"><span data-stu-id="6946a-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="6946a-109">Предоставляет функции данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="6946a-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="6946a-110">Создает команды определенного поставщика для поддержки запросов [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbQueryCommandTree.</span><span class="sxs-lookup"><span data-stu-id="6946a-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="6946a-111">Формирует команды обновления для определенного поставщика для поддержки обновлений через [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="6946a-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="6946a-112">Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.</span><span class="sxs-lookup"><span data-stu-id="6946a-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="6946a-113">Предоставляет метаданные (например, таблицы и представления) посредством концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="6946a-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="6946a-114">![b42a7a5c &#45; 0ac0 &#45; 4911 &#45; 86be &#45; 0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="6946a-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="6946a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6946a-115">Sample</span></span>  
 <span data-ttu-id="6946a-116">В разделе [образца поставщика Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) образец [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поставщика, который поддерживает источник данных, отличный от [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6946a-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6946a-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6946a-117">In This Section</span></span>  
 [<span data-ttu-id="6946a-118">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="6946a-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="6946a-119">Создание кода SQL для изменения данных</span><span class="sxs-lookup"><span data-stu-id="6946a-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="6946a-120">Спецификация манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="6946a-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="6946a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6946a-121">See Also</span></span>  
 [<span data-ttu-id="6946a-122">Работа с поставщиками данных</span><span class="sxs-lookup"><span data-stu-id="6946a-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
