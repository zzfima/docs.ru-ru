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
ms.workload: dotnet
ms.openlocfilehash: 3059adbc9cd2c67035d5f6579e292df80cd87ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="7e985-102">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="7e985-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="7e985-103">Предоставляет коллекцию API-интерфейсов, которые помогают обнаруживать, оценивать и разрешать конфликты параллелизма.</span><span class="sxs-lookup"><span data-stu-id="7e985-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e985-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7e985-104">In This Section</span></span>  
 [<span data-ttu-id="7e985-105">Практическое руководство. Обнаружение и разрешение отправок, вызывающих конфликты</span><span class="sxs-lookup"><span data-stu-id="7e985-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="7e985-106">Описывается, как обнаруживать и разрешать конфликты параллелизма.</span><span class="sxs-lookup"><span data-stu-id="7e985-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="7e985-107">Практическое руководство. Выбор ситуаций, в которых создаются исключения параллельности</span><span class="sxs-lookup"><span data-stu-id="7e985-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="7e985-108">Описывается, как указывать моменты, в которые следует извещать о конфликтах параллелизма.</span><span class="sxs-lookup"><span data-stu-id="7e985-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="7e985-109">Практическое руководство. Выбор членов для проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="7e985-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="7e985-110">Описываются способы добавления атрибутов к членам, чтобы указать, следует ли их проверять на наличие конфликтов параллелизма.</span><span class="sxs-lookup"><span data-stu-id="7e985-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="7e985-111">Практическое руководство. Получение сведений о конфликте сущностей</span><span class="sxs-lookup"><span data-stu-id="7e985-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="7e985-112">Описывается, как собирать сведения о конфликтах сущностей.</span><span class="sxs-lookup"><span data-stu-id="7e985-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="7e985-113">Практическое руководство. Получение сведений о конфликте членов</span><span class="sxs-lookup"><span data-stu-id="7e985-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="7e985-114">Описывается, как собирать сведения о конфликтах членов.</span><span class="sxs-lookup"><span data-stu-id="7e985-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="7e985-115">Практическое руководство. Разрешение конфликтов за счет сохранения значений баз данных</span><span class="sxs-lookup"><span data-stu-id="7e985-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="7e985-116">Описывается, как перезаписывать текущие значения значениями из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7e985-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="7e985-117">Практическое руководство. Разрешение конфликтов за счет перезаписи значений баз данных</span><span class="sxs-lookup"><span data-stu-id="7e985-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="7e985-118">Описывается, как сохранять текущие значения, перезаписывая значения из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7e985-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="7e985-119">Практическое руководство. Разрешение конфликтов за счет слияния со значениями баз данных</span><span class="sxs-lookup"><span data-stu-id="7e985-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="7e985-120">Описывается, как разрешать конфликты путем объединения значений из базы данных с текущими значениями.</span><span class="sxs-lookup"><span data-stu-id="7e985-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7e985-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7e985-121">Related Sections</span></span>  
 [<span data-ttu-id="7e985-122">Общие сведения об оптимистической блокировке</span><span class="sxs-lookup"><span data-stu-id="7e985-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="7e985-123">Объясняются термины, применяемые к оптимистическому параллелизму в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e985-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
