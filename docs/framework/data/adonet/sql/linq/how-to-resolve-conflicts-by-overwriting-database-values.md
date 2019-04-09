---
title: Практическое руководство. Как разрешать конфликты путем переписывания значений базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 7b8d7cf8ab2335c064062ed3ab4072d81e8042fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189122"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="cdb40-102">Практическое руководство. Как разрешать конфликты путем переписывания значений базы данных</span><span class="sxs-lookup"><span data-stu-id="cdb40-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="cdb40-103">Чтобы выверить различия между ожидаемыми и фактическими значениями базы данных до повторной отправки изменений, можно воспользоваться <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> для перезаписи значений базы данных.</span><span class="sxs-lookup"><span data-stu-id="cdb40-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="cdb40-104">Дополнительные сведения см. в разделе [оптимистичный параллелизм: Общие сведения о](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cdb40-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdb40-105">Во всех случаях запись на клиенте сначала обновляется путем извлечения обновленных данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="cdb40-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="cdb40-106">Это действие гарантирует успешное выполнение следующей попытки обновления при тех же проверках параллелизма.</span><span class="sxs-lookup"><span data-stu-id="cdb40-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb40-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cdb40-107">Example</span></span>  
 <span data-ttu-id="cdb40-108">В данном сценарии, когда Пользователь1 пытается отправить изменения, возникает исключение <xref:System.Data.Linq.ChangeConflictException>, поскольку Пользователь2 в это время изменил столбцы "Помощник" и "Отдел".</span><span class="sxs-lookup"><span data-stu-id="cdb40-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="cdb40-109">Эта ситуация представлена в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cdb40-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="cdb40-110">Руководитель</span><span class="sxs-lookup"><span data-stu-id="cdb40-110">Manager</span></span>|<span data-ttu-id="cdb40-111">Помощник</span><span class="sxs-lookup"><span data-stu-id="cdb40-111">Assistant</span></span>|<span data-ttu-id="cdb40-112">Отдел</span><span class="sxs-lookup"><span data-stu-id="cdb40-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="cdb40-113">Исходное состояние базы данных при отправке запросов Пользователем1 и Пользователем2.</span><span class="sxs-lookup"><span data-stu-id="cdb40-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="cdb40-114">Алексеи</span><span class="sxs-lookup"><span data-stu-id="cdb40-114">Alfreds</span></span>|<span data-ttu-id="cdb40-115">Мария</span><span class="sxs-lookup"><span data-stu-id="cdb40-115">Maria</span></span>|<span data-ttu-id="cdb40-116">Продажи</span><span class="sxs-lookup"><span data-stu-id="cdb40-116">Sales</span></span>|  
|<span data-ttu-id="cdb40-117">Пользователь1 готовится отправить изменения.</span><span class="sxs-lookup"><span data-stu-id="cdb40-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="cdb40-118">Алексей</span><span class="sxs-lookup"><span data-stu-id="cdb40-118">Alfred</span></span>||<span data-ttu-id="cdb40-119">Маркетинговый отдел</span><span class="sxs-lookup"><span data-stu-id="cdb40-119">Marketing</span></span>|  
|<span data-ttu-id="cdb40-120">Пользователь2 уже отправил изменения.</span><span class="sxs-lookup"><span data-stu-id="cdb40-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="cdb40-121">Инна</span><span class="sxs-lookup"><span data-stu-id="cdb40-121">Mary</span></span>|<span data-ttu-id="cdb40-122">Служба</span><span class="sxs-lookup"><span data-stu-id="cdb40-122">Service</span></span>|  
  
 <span data-ttu-id="cdb40-123">Пользователь1 решает устранить этот конфликт путем перезаписи значений базы данных текущими значениями членов клиента.</span><span class="sxs-lookup"><span data-stu-id="cdb40-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="cdb40-124">При устранении Пользователем1 конфликта с помощью <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> результат в базе данных будет соответствовать данным в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cdb40-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="cdb40-125">Руководитель</span><span class="sxs-lookup"><span data-stu-id="cdb40-125">Manager</span></span>|<span data-ttu-id="cdb40-126">Помощник</span><span class="sxs-lookup"><span data-stu-id="cdb40-126">Assistant</span></span>|<span data-ttu-id="cdb40-127">Отдел</span><span class="sxs-lookup"><span data-stu-id="cdb40-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="cdb40-128">Новое состояние после устранения конфликта.</span><span class="sxs-lookup"><span data-stu-id="cdb40-128">New state after conflict resolution.</span></span>|<span data-ttu-id="cdb40-129">Алексей</span><span class="sxs-lookup"><span data-stu-id="cdb40-129">Alfred</span></span><br /><br /> <span data-ttu-id="cdb40-130">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="cdb40-130">(from User1)</span></span>|<span data-ttu-id="cdb40-131">Мария</span><span class="sxs-lookup"><span data-stu-id="cdb40-131">Maria</span></span><br /><br /> <span data-ttu-id="cdb40-132">(исходное значение)</span><span class="sxs-lookup"><span data-stu-id="cdb40-132">(original)</span></span>|<span data-ttu-id="cdb40-133">Маркетинговый отдел</span><span class="sxs-lookup"><span data-stu-id="cdb40-133">Marketing</span></span><br /><br /> <span data-ttu-id="cdb40-134">(от Пользователя1)</span><span class="sxs-lookup"><span data-stu-id="cdb40-134">(from User1)</span></span>|  
  
 <span data-ttu-id="cdb40-135">В следующем примере кода показано, как перезаписать значения базы данных текущими значениями членов клиента</span><span class="sxs-lookup"><span data-stu-id="cdb40-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="cdb40-136">(проверка или пользовательская обработка конфликтов отдельных членов не выполняется).</span><span class="sxs-lookup"><span data-stu-id="cdb40-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cdb40-137">См. также</span><span class="sxs-lookup"><span data-stu-id="cdb40-137">See also</span></span>

- [<span data-ttu-id="cdb40-138">Практическое руководство. Как управлять конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="cdb40-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
