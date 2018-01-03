---
title: "Внесение и отправка изменений данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d2b121bdadcc231d2ea3a2c1d2ebdab40306c5ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="15cbc-102">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="15cbc-103">В подразделах данного раздела описывается, как выполнять изменения и передавать их в базу данных, а также обрабатывать конфликты оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="15cbc-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15cbc-104">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="15cbc-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="15cbc-105">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="15cbc-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="15cbc-106">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.</span><span class="sxs-lookup"><span data-stu-id="15cbc-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15cbc-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="15cbc-107">In This Section</span></span>  
 [<span data-ttu-id="15cbc-108">Практическое руководство. Вставка строк в базу данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="15cbc-109">Описывает, как вставлять строки в базу данных путем добавления объектов в модель объектов.</span><span class="sxs-lookup"><span data-stu-id="15cbc-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="15cbc-110">Практическое руководство. Обновление строк в базе данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="15cbc-111">Описывается, как обновлять строки в базе данных путем обновления объектов в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="15cbc-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="15cbc-112">Практическое руководство. Удаление строк из базы данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="15cbc-113">Описывается, как удалять строки из базы данных путем удаления объектов из объектной модели.</span><span class="sxs-lookup"><span data-stu-id="15cbc-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="15cbc-114">Практическое руководство. Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="15cbc-115">Описывается, как отправлять изменения объектной модели в базу данных.</span><span class="sxs-lookup"><span data-stu-id="15cbc-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="15cbc-116">Практическое руководство. Группировка отправок данных с использованием транзакций</span><span class="sxs-lookup"><span data-stu-id="15cbc-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="15cbc-117">Описывается, как включать операции в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="15cbc-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="15cbc-118">Практическое руководство. Динамическое создание базы данных</span><span class="sxs-lookup"><span data-stu-id="15cbc-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="15cbc-119">Описывается динамическое создание баз данных и типичные сценарии использования этого метода.</span><span class="sxs-lookup"><span data-stu-id="15cbc-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="15cbc-120">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="15cbc-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="15cbc-121">Описываются методы устранения проблем оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="15cbc-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
