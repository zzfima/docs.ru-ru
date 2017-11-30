---
title: "Практическое руководство. Управление конфликтами изменений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 87d895c8d5531d091d773e9f2d51b89408169022
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="fac3a-102">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="fac3a-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="fac3a-103">Предоставляет коллекцию API-интерфейсов, которые помогают обнаруживать, оценивать и разрешать конфликты параллелизма.</span><span class="sxs-lookup"><span data-stu-id="fac3a-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fac3a-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="fac3a-104">In This Section</span></span>  
 [<span data-ttu-id="fac3a-105">Как: обнаруживать и разрешать конфликты отправки</span><span class="sxs-lookup"><span data-stu-id="fac3a-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="fac3a-106">Описывается, как обнаруживать и разрешать конфликты параллелизма.</span><span class="sxs-lookup"><span data-stu-id="fac3a-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="fac3a-107">Как: Укажите, при которых создаются исключения параллельности</span><span class="sxs-lookup"><span data-stu-id="fac3a-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="fac3a-108">Описывается, как указывать моменты, в которые следует извещать о конфликтах параллелизма.</span><span class="sxs-lookup"><span data-stu-id="fac3a-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="fac3a-109">Как: Укажите, какие элементы проверяются на наличие конфликтов параллелизма</span><span class="sxs-lookup"><span data-stu-id="fac3a-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="fac3a-110">Описываются способы добавления атрибутов к членам, чтобы указать, следует ли их проверять на наличие конфликтов параллелизма.</span><span class="sxs-lookup"><span data-stu-id="fac3a-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="fac3a-111">Как: получение сведений о конфликте сущностей</span><span class="sxs-lookup"><span data-stu-id="fac3a-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="fac3a-112">Описывается, как собирать сведения о конфликтах сущностей.</span><span class="sxs-lookup"><span data-stu-id="fac3a-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="fac3a-113">Как: получение сведений о конфликте членов</span><span class="sxs-lookup"><span data-stu-id="fac3a-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="fac3a-114">Описывается, как собирать сведения о конфликтах членов.</span><span class="sxs-lookup"><span data-stu-id="fac3a-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="fac3a-115">Как: разрешение конфликтов за счет сохранения значений базы данных</span><span class="sxs-lookup"><span data-stu-id="fac3a-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="fac3a-116">Описывается, как перезаписывать текущие значения значениями из базы данных.</span><span class="sxs-lookup"><span data-stu-id="fac3a-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="fac3a-117">Как: разрешение конфликтов за счет перезаписи значений базы данных</span><span class="sxs-lookup"><span data-stu-id="fac3a-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="fac3a-118">Описывается, как сохранять текущие значения, перезаписывая значения из базы данных.</span><span class="sxs-lookup"><span data-stu-id="fac3a-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="fac3a-119">Как: разрешать конфликты путем объединения значений базы данных</span><span class="sxs-lookup"><span data-stu-id="fac3a-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="fac3a-120">Описывается, как разрешать конфликты путем объединения значений из базы данных с текущими значениями.</span><span class="sxs-lookup"><span data-stu-id="fac3a-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fac3a-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fac3a-121">Related Sections</span></span>  
 [<span data-ttu-id="fac3a-122">Оптимистический параллелизм: Обзор</span><span class="sxs-lookup"><span data-stu-id="fac3a-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="fac3a-123">Объясняются термины, применяемые к оптимистическому параллелизму в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fac3a-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
