---
title: "Запрос к базе данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4e7f2c2a3936fc27e963867a4a4bf4bc210c6b7e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="querying-the-database"></a><span data-ttu-id="41822-102">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="41822-102">Querying the Database</span></span>
<span data-ttu-id="41822-103">В этой группе разделов описывается, как разрабатывать и выполнять запросы в проектах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41822-103">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41822-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="41822-104">In This Section</span></span>  
 [<span data-ttu-id="41822-105">Практическое руководство. Запрос информации</span><span class="sxs-lookup"><span data-stu-id="41822-105">How to: Query for Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-query-for-information.md)  
 <span data-ttu-id="41822-106">Кратко показано общее сходство запросов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] с запросами [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41822-106">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries generally.</span></span>  
  
 [<span data-ttu-id="41822-107">Практическое руководство. Получение сведений как доступных только для чтения</span><span class="sxs-lookup"><span data-stu-id="41822-107">How to: Retrieve Information As Read-Only</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="41822-108">Описывается, как увеличить производительность запроса, если не планируется изменять данные.</span><span class="sxs-lookup"><span data-stu-id="41822-108">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="41822-109">Практическое руководство. Управление объемом получаемых взаимосвязанных данных</span><span class="sxs-lookup"><span data-stu-id="41822-109">How to: Control How Much Related Data Is Retrieved</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="41822-110">Описывается, как определять, какие связанные данные извлекаются вместе с основными целевыми данными.</span><span class="sxs-lookup"><span data-stu-id="41822-110">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="41822-111">Практическое руководство. Фильтрация связанных данных</span><span class="sxs-lookup"><span data-stu-id="41822-111">How to: Filter Related Data</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-related-data.md)  
 <span data-ttu-id="41822-112">Описывается, как извлекать данные с помощью вложенных запросов.</span><span class="sxs-lookup"><span data-stu-id="41822-112">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="41822-113">Практическое руководство. Выключение отложенной загрузки</span><span class="sxs-lookup"><span data-stu-id="41822-113">How to: Turn Off Deferred Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="41822-114">Описывается, как отключить отложенную загрузку.</span><span class="sxs-lookup"><span data-stu-id="41822-114">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="41822-115">Практическое руководство. Непосредственное выполнение запросов SQL</span><span class="sxs-lookup"><span data-stu-id="41822-115">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="41822-116">Описывается, как отправлять запросы с помощью языка SQL.</span><span class="sxs-lookup"><span data-stu-id="41822-116">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="41822-117">Практическое руководство. Хранение и повторное использование запросов</span><span class="sxs-lookup"><span data-stu-id="41822-117">How to: Store and Reuse Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="41822-118">Описывается, как, скомпилировав запрос один раз, использовать его несколько раз с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="41822-118">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="41822-119">Практическое руководство. Обработка составных ключей в запросах</span><span class="sxs-lookup"><span data-stu-id="41822-119">How to: Handle Composite Keys in Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="41822-120">Описывается, как включить несколько столбцов в запрос, оператор которого принимает только один аргумент.</span><span class="sxs-lookup"><span data-stu-id="41822-120">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="41822-121">Практическое руководство. Извлечение нескольких объектов одновременно</span><span class="sxs-lookup"><span data-stu-id="41822-121">How to: Retrieve Many Objects At Once</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="41822-122">Описание использования <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="41822-122">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="41822-123">Практическое руководство. Фильтрация на уровне DataContext</span><span class="sxs-lookup"><span data-stu-id="41822-123">How to: Filter at the DataContext Level</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="41822-124">Описывается другое использование метода <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="41822-124">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="41822-125">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="41822-125">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="41822-126">Предлагается несколько примеров запросов.</span><span class="sxs-lookup"><span data-stu-id="41822-126">Provides many examples of queries.</span></span>
