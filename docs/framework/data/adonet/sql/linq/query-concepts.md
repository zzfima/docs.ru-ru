---
title: "Основные принципы запросов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4bea41ad092de4afe1a2fff7927321d63c43278e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="query-concepts"></a><span data-ttu-id="0bbd2-102">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="0bbd2-102">Query Concepts</span></span>
<span data-ttu-id="0bbd2-103">В данном разделе описываются основные понятия, связанные с разработкой запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bbd2-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0bbd2-104">In This Section</span></span>  
 [<span data-ttu-id="0bbd2-105">Запросы LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0bbd2-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="0bbd2-106">Содержатся ссылки на общие разделы, посвященные [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], и объясняются вопросы, связанные с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="0bbd2-107">Выполнение запросов в связях</span><span class="sxs-lookup"><span data-stu-id="0bbd2-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="0bbd2-108">Объясняется, как использовать связи в объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="0bbd2-109">Сравнение удаленного и локального выполнений</span><span class="sxs-lookup"><span data-stu-id="0bbd2-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="0bbd2-110">Объясняется, как указать место выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="0bbd2-111">Отложенная и немедленная загрузка</span><span class="sxs-lookup"><span data-stu-id="0bbd2-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="0bbd2-112">Описывается, как указать время загрузки связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="0bbd2-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0bbd2-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0bbd2-113">Related Sections</span></span>  
 [<span data-ttu-id="0bbd2-114">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="0bbd2-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="0bbd2-115">Содержатся ссылки на разделы, в которых описывается технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="0bbd2-116">Идентификация объектов</span><span class="sxs-lookup"><span data-stu-id="0bbd2-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="0bbd2-117">Объясняется понятие идентификации объекта в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="0bbd2-118">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="0bbd2-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="0bbd2-119">Содержатся вводные сведения о об операциях запросов в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bbd2-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
