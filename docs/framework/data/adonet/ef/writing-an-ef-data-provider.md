---
title: Создание поставщика данных Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 50c0555d84c5b5f180c8c49a8419e8a414a4befe
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739455"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="6f1d4-102">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6f1d4-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="6f1d4-103">В этом разделе описывается порядок написания [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поставщика для поддержки источника данных, отличного от SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="6f1d4-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Включает поставщика, который поддерживает SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="6f1d4-105">Знакомство с моделью поставщика Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6f1d4-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="6f1d4-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] не зависит от баз данных, написать поставщика для подключения к различным источникам данных можно при помощи модели поставщика ADO.NE.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="6f1d4-107">Поставщик данных Entity Framework (созданный при помощи модели поставщика ADO.NET) выполняет следующие функции.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="6f1d4-108">Сопоставляет примитивные типы модели EDM с типами поставщика.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="6f1d4-109">Предоставляет функции данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="6f1d4-110">Создает команды определенного поставщика для поддержки запросов [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbQueryCommandTree.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="6f1d4-111">Формирует команды обновления для определенного поставщика для поддержки обновлений через [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="6f1d4-112">Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="6f1d4-113">Предоставляет метаданные (например, таблицы и представления) посредством концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="6f1d4-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="6f1d4-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="6f1d4-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6f1d4-115">Sample</span></span>  
 <span data-ttu-id="6f1d4-116">См. в разделе [образца поставщика Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) пример [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поставщика, поддерживающего источника данных, отличного от SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f1d4-116">See the [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f1d4-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f1d4-117">In This Section</span></span>  
 [<span data-ttu-id="6f1d4-118">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="6f1d4-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="6f1d4-119">Создание кода SQL для изменения данных</span><span class="sxs-lookup"><span data-stu-id="6f1d4-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="6f1d4-120">Спецификация манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="6f1d4-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f1d4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6f1d4-121">See Also</span></span>  
 [<span data-ttu-id="6f1d4-122">Работа с поставщиками данных</span><span class="sxs-lookup"><span data-stu-id="6f1d4-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
