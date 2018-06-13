---
title: Основные принципы запросов
ms.date: 03/30/2017
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
ms.openlocfilehash: 62af37399cda5220c429fae2d9ab619989050b00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361631"
---
# <a name="query-concepts"></a><span data-ttu-id="a9dc5-102">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="a9dc5-102">Query Concepts</span></span>
<span data-ttu-id="a9dc5-103">В данном разделе описываются основные понятия, связанные с разработкой запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9dc5-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a9dc5-104">In This Section</span></span>  
 [<span data-ttu-id="a9dc5-105">Запросы LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a9dc5-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="a9dc5-106">Содержатся ссылки на общие разделы, посвященные [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], и объясняются вопросы, связанные с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="a9dc5-107">Выполнение запросов в связях</span><span class="sxs-lookup"><span data-stu-id="a9dc5-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="a9dc5-108">Объясняется, как использовать связи в объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="a9dc5-109">Сравнение удаленного и локального выполнений</span><span class="sxs-lookup"><span data-stu-id="a9dc5-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="a9dc5-110">Объясняется, как указать место выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="a9dc5-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="a9dc5-111">Отложенная и немедленная загрузка</span><span class="sxs-lookup"><span data-stu-id="a9dc5-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="a9dc5-112">Описывается, как указать время загрузки связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="a9dc5-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9dc5-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a9dc5-113">Related Sections</span></span>  
 [<span data-ttu-id="a9dc5-114">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="a9dc5-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="a9dc5-115">Содержатся ссылки на разделы, в которых описывается технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="a9dc5-116">Идентификация объектов</span><span class="sxs-lookup"><span data-stu-id="a9dc5-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="a9dc5-117">Объясняется понятие идентификации объекта в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="a9dc5-118">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a9dc5-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="a9dc5-119">Содержатся вводные сведения о об операциях запросов в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9dc5-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
