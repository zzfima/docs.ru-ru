---
title: Практическое руководство. Как указать, когда возникают исключения параллелизма
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 0be17e7ceb6a5e5230d2619be350266d0282078c
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910806"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="06bd8-102">Практическое руководство. Как указать, когда возникают исключения параллелизма</span><span class="sxs-lookup"><span data-stu-id="06bd8-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="06bd8-103">Если в связи с конфликтами оптимистической блокировки обновление объектов не выполняется, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывается исключение <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="06bd8-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="06bd8-104">Дополнительные сведения см. в разделе [оптимистичный параллелизм: Общие сведения о](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="06bd8-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="06bd8-105">Перед отправкой изменений в базу данных можно указать момент возникновения исключений блокировки.</span><span class="sxs-lookup"><span data-stu-id="06bd8-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="06bd8-106">Создавать исключение при первом сбое (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="06bd8-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="06bd8-107">Завершить все попытки обновления, собрать все ошибки и сообщить о них в исключении (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="06bd8-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="06bd8-108">Созданное исключение <xref:System.Data.Linq.ChangeConflictException> предоставляет доступ к коллекции <xref:System.Data.Linq.ChangeConflictCollection>.</span><span class="sxs-lookup"><span data-stu-id="06bd8-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="06bd8-109">Данная коллекция содержит сведения о каждом конфликте (сопоставленном с одной неудачной попыткой обновления), включая доступ к коллекции <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.</span><span class="sxs-lookup"><span data-stu-id="06bd8-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="06bd8-110">Каждый конфликт члена сопоставляется с одним членом в обновлении, которое привело к сбою проверки блокировки.</span><span class="sxs-lookup"><span data-stu-id="06bd8-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06bd8-111">Пример</span><span class="sxs-lookup"><span data-stu-id="06bd8-111">Example</span></span>  
 <span data-ttu-id="06bd8-112">В следующем коде приведены примеры обоих значений.</span><span class="sxs-lookup"><span data-stu-id="06bd8-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06bd8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="06bd8-113">See also</span></span>

- [<span data-ttu-id="06bd8-114">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="06bd8-114">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="06bd8-115">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="06bd8-115">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
