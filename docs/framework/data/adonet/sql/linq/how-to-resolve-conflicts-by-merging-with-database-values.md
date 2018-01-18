---
title: "Практическое руководство. Разрешение конфликтов за счет слияния со значениями баз данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 942313f87f19345b3656ec241e4c673d3f12601d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="1a6f2-102">Практическое руководство. Разрешение конфликтов за счет слияния со значениями баз данных</span><span class="sxs-lookup"><span data-stu-id="1a6f2-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="1a6f2-103">Чтобы согласовать различия между ожидаемыми и фактическими значениями базы данных до повторной отправки изменений, можно воспользоваться <xref:System.Data.Linq.RefreshMode.KeepChanges> для объединения значений базы данных с текущими значениями члена клиента.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="1a6f2-104">Дополнительные сведения см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a6f2-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a6f2-105">Во всех случаях запись на клиенте сначала обновляется путем извлечения обновленных данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="1a6f2-106">Это действие гарантирует успешное выполнение следующей попытки обновления при тех же проверках параллелизма.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a6f2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="1a6f2-107">Example</span></span>  
 <span data-ttu-id="1a6f2-108">В данном сценарии, когда Пользователь1 пытается отправить изменения, возникает исключение <xref:System.Data.Linq.ChangeConflictException>, поскольку Пользователь2 в это время изменил столбцы "Помощник" и "Отдел".</span><span class="sxs-lookup"><span data-stu-id="1a6f2-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="1a6f2-109">Эта ситуация представлена в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="1a6f2-110">Диспетчер</span><span class="sxs-lookup"><span data-stu-id="1a6f2-110">Manager</span></span>|<span data-ttu-id="1a6f2-111">Помощник</span><span class="sxs-lookup"><span data-stu-id="1a6f2-111">Assistant</span></span>|<span data-ttu-id="1a6f2-112">Отдел</span><span class="sxs-lookup"><span data-stu-id="1a6f2-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="1a6f2-113">Исходное состояние базы данных при отправке запросов Пользователем1 и Пользователем2.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="1a6f2-114">Алексеи</span><span class="sxs-lookup"><span data-stu-id="1a6f2-114">Alfreds</span></span>|<span data-ttu-id="1a6f2-115">Мария</span><span class="sxs-lookup"><span data-stu-id="1a6f2-115">Maria</span></span>|<span data-ttu-id="1a6f2-116">Продажи</span><span class="sxs-lookup"><span data-stu-id="1a6f2-116">Sales</span></span>|  
|<span data-ttu-id="1a6f2-117">Пользователь1 готовится отправить изменения.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="1a6f2-118">Алексей</span><span class="sxs-lookup"><span data-stu-id="1a6f2-118">Alfred</span></span>||<span data-ttu-id="1a6f2-119">Маркетинг</span><span class="sxs-lookup"><span data-stu-id="1a6f2-119">Marketing</span></span>|  
|<span data-ttu-id="1a6f2-120">Пользователь2 уже отправил изменения.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="1a6f2-121">Инна</span><span class="sxs-lookup"><span data-stu-id="1a6f2-121">Mary</span></span>|<span data-ttu-id="1a6f2-122">Служба</span><span class="sxs-lookup"><span data-stu-id="1a6f2-122">Service</span></span>|  
  
 <span data-ttu-id="1a6f2-123">Пользователь1 решает устранить этот конфликт путем объединения значений базы данных с текущими значениями члена клиента.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="1a6f2-124">Ожидаемый результат: значения базы данных будут переопределены только при изменении значения текущим набором изменений.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="1a6f2-125">При устранении Пользователем1 конфликта с помощью <xref:System.Data.Linq.RefreshMode.KeepChanges> результат в базе данных будет соответствовать данным в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="1a6f2-126">Диспетчер</span><span class="sxs-lookup"><span data-stu-id="1a6f2-126">Manager</span></span>|<span data-ttu-id="1a6f2-127">Помощник</span><span class="sxs-lookup"><span data-stu-id="1a6f2-127">Assistant</span></span>|<span data-ttu-id="1a6f2-128">Отдел</span><span class="sxs-lookup"><span data-stu-id="1a6f2-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="1a6f2-129">Новое состояние после устранения конфликта.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-129">New state after conflict resolution.</span></span>|<span data-ttu-id="1a6f2-130">Алексей</span><span class="sxs-lookup"><span data-stu-id="1a6f2-130">Alfred</span></span><br /><br /> <span data-ttu-id="1a6f2-131">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="1a6f2-131">(from User1)</span></span>|<span data-ttu-id="1a6f2-132">Инна</span><span class="sxs-lookup"><span data-stu-id="1a6f2-132">Mary</span></span><br /><br /> <span data-ttu-id="1a6f2-133">(от Пользователя2)</span><span class="sxs-lookup"><span data-stu-id="1a6f2-133">(from User2)</span></span>|<span data-ttu-id="1a6f2-134">Маркетинг</span><span class="sxs-lookup"><span data-stu-id="1a6f2-134">Marketing</span></span><br /><br /> <span data-ttu-id="1a6f2-135">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="1a6f2-135">(from User1)</span></span>|  
  
 <span data-ttu-id="1a6f2-136">В следующем примере показано объединение значений базы данных с текущими значениями члена клиента (если клиент также не изменил это значение).</span><span class="sxs-lookup"><span data-stu-id="1a6f2-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="1a6f2-137">Конфликты проверки или пользовательской обработки отдельных членов не возникают.</span><span class="sxs-lookup"><span data-stu-id="1a6f2-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1a6f2-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1a6f2-138">See Also</span></span>  
 [<span data-ttu-id="1a6f2-139">Практическое руководство. Разрешение конфликтов за счет перезаписи значений баз данных</span><span class="sxs-lookup"><span data-stu-id="1a6f2-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="1a6f2-140">Практическое руководство. Разрешение конфликтов за счет сохранения значений баз данных</span><span class="sxs-lookup"><span data-stu-id="1a6f2-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="1a6f2-141">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="1a6f2-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
