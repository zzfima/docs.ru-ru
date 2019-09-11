---
title: Создание поставщика данных Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854159"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="d92c6-102">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d92c6-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="d92c6-103">В этом разделе описывается написание поставщика Entity Framework для поддержки источника данных, отличного от SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d92c6-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="d92c6-104">Entity Framework содержит поставщик, поддерживающий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d92c6-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="d92c6-105">Знакомство с моделью поставщика Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d92c6-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="d92c6-106">Entity Framework не зависит от базы данных, и вы можете написать поставщик с помощью модели поставщика ADO.NET для подключения к широкому набору источников данных.</span><span class="sxs-lookup"><span data-stu-id="d92c6-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="d92c6-107">Поставщик данных Entity Framework (созданный при помощи модели поставщика ADO.NET) выполняет следующие функции.</span><span class="sxs-lookup"><span data-stu-id="d92c6-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="d92c6-108">Сопоставляет примитивные типы модели EDM с типами поставщика.</span><span class="sxs-lookup"><span data-stu-id="d92c6-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="d92c6-109">Предоставляет функции данного поставщика.</span><span class="sxs-lookup"><span data-stu-id="d92c6-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="d92c6-110">Создает специальные команды поставщика для данного Дбкуерикоммандтри для поддержки запросов Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d92c6-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="d92c6-111">Создает специфические для поставщика команды обновления для данного DbModificationCommandTree для поддержки обновлений с помощью Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d92c6-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="d92c6-112">Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.</span><span class="sxs-lookup"><span data-stu-id="d92c6-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="d92c6-113">Предоставляет метаданные (например, таблицы и представления) посредством концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="d92c6-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="d92c6-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="d92c6-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="d92c6-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d92c6-115">Sample</span></span>  
 <span data-ttu-id="d92c6-116">Пример поставщика Entity Framework, который поддерживает источник данных, отличный от SQL Server, см. в [Entity Framework примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) .</span><span class="sxs-lookup"><span data-stu-id="d92c6-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d92c6-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d92c6-117">In This Section</span></span>  
 [<span data-ttu-id="d92c6-118">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="d92c6-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="d92c6-119">Создание кода SQL для изменения данных</span><span class="sxs-lookup"><span data-stu-id="d92c6-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="d92c6-120">Спецификация манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="d92c6-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="d92c6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d92c6-121">See also</span></span>

- [<span data-ttu-id="d92c6-122">Работа с поставщиками данных</span><span class="sxs-lookup"><span data-stu-id="d92c6-122">Working with Data Providers</span></span>](working-with-data-providers.md)
