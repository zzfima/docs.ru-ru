---
title: "Практическое руководство. Отправка изменений в базу данных"
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
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 69ada8afe783ce8cc425a5804eab6a00475871c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="52238-102">Практическое руководство. Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="52238-102">How to: Submit Changes to the Database</span></span>
<span data-ttu-id="52238-103">Независимо от количества изменений, произведенных над объектами, эти изменения выполняются только над репликам, содержащимся в памяти.</span><span class="sxs-lookup"><span data-stu-id="52238-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="52238-104">Фактические данные в базе данных при этом не изменяются.</span><span class="sxs-lookup"><span data-stu-id="52238-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="52238-105">Изменения не передаются на сервер до тех пор, пока не будет явно вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> класса <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="52238-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="52238-106">При вызове этого метода класс <xref:System.Data.Linq.DataContext> пытается преобразовать сделанные изменения в эквивалентные команды SQL.</span><span class="sxs-lookup"><span data-stu-id="52238-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="52238-107">Можно использовать собственную пользовательскую логику для переопределения этих действий, однако порядок отправки управляется службой для <xref:System.Data.Linq.DataContext> называется *обработчиком изменений*.</span><span class="sxs-lookup"><span data-stu-id="52238-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="52238-108">Ниже представлена последовательность событий.</span><span class="sxs-lookup"><span data-stu-id="52238-108">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="52238-109">При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает набор известных объектов, чтобы определить, присоединены ли к ним новые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="52238-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="52238-110">При положительном результате новые экземпляры добавляются в набор отслеживаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="52238-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2.  <span data-ttu-id="52238-111">Все объекты, содержащие ожидающие изменения, упорядочиваются в последовательности объектов на основе зависимостей между ними.</span><span class="sxs-lookup"><span data-stu-id="52238-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="52238-112">Объекты, изменения которых зависят от других объектов, располагаются после своих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="52238-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3.  <span data-ttu-id="52238-113">Непосредственно после передачи фактических изменений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] начинает транзакцию для инкапсуляции ряда отдельных команд.</span><span class="sxs-lookup"><span data-stu-id="52238-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4.  <span data-ttu-id="52238-114">Изменения объектов последовательно преобразуются в команды SQL и отправляются на сервер.</span><span class="sxs-lookup"><span data-stu-id="52238-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="52238-115">В данный момент любые ошибки, обнаруженные базой данных, приводят к остановке процесса отправки и вызову исключения.</span><span class="sxs-lookup"><span data-stu-id="52238-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="52238-116">Выполняется откат всех изменений базы данных к состоянию до начала отправки.</span><span class="sxs-lookup"><span data-stu-id="52238-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="52238-117">Класс <xref:System.Data.Linq.DataContext> по-прежнему содержит запись всех изменений.</span><span class="sxs-lookup"><span data-stu-id="52238-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="52238-118">Поэтому можно попытаться исправить проблему и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> еще раз, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="52238-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52238-119">Пример</span><span class="sxs-lookup"><span data-stu-id="52238-119">Example</span></span>  
 <span data-ttu-id="52238-120">После успешного завершения транзакции, содержащей отправку, класс <xref:System.Data.Linq.DataContext> принимает изменения объектов, пропуская сведения об отслеживании изменений.</span><span class="sxs-lookup"><span data-stu-id="52238-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="52238-121">См. также</span><span class="sxs-lookup"><span data-stu-id="52238-121">See Also</span></span>  
 [<span data-ttu-id="52238-122">Практическое руководство. Обнаружение и разрешение отправок, вызывающих конфликты</span><span class="sxs-lookup"><span data-stu-id="52238-122">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 [<span data-ttu-id="52238-123">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="52238-123">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="52238-124">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="52238-124">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="52238-125">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="52238-125">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
