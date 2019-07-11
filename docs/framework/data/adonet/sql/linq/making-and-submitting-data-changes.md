---
title: Внесение и отправка изменений данных
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 23dc45c990763e69b41608f6c3ec15a8db17bf23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743012"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="cbd02-102">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="cbd02-103">В подразделах данного раздела описывается, как выполнять изменения и передавать их в базу данных, а также обрабатывать конфликты оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="cbd02-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbd02-104">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="cbd02-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="cbd02-105">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cbd02-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="cbd02-106">Реляционный конструктор объектов позволяют разработчикам, с помощью Visual Studio для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="cbd02-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbd02-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cbd02-107">In This Section</span></span>  
 [<span data-ttu-id="cbd02-108">Практическое руководство. Вставка строк в базе данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="cbd02-109">Описывает, как вставлять строки в базу данных путем добавления объектов в модель объектов.</span><span class="sxs-lookup"><span data-stu-id="cbd02-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="cbd02-110">Практическое руководство. Обновление строк в базе данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="cbd02-111">Описывается, как обновлять строки в базе данных путем обновления объектов в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="cbd02-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="cbd02-112">Практическое руководство. Удаление строк из базы данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="cbd02-113">Описывается, как удалять строки из базы данных путем удаления объектов из объектной модели.</span><span class="sxs-lookup"><span data-stu-id="cbd02-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="cbd02-114">Практическое руководство. Отправка изменений в базу данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="cbd02-115">Описывается, как отправлять изменения объектной модели в базу данных.</span><span class="sxs-lookup"><span data-stu-id="cbd02-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="cbd02-116">Практическое руководство. Объединить в пакеты отправку данных с помощью транзакций</span><span class="sxs-lookup"><span data-stu-id="cbd02-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="cbd02-117">Описывается, как включать операции в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cbd02-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="cbd02-118">Практическое руководство. Динамически создать базу данных</span><span class="sxs-lookup"><span data-stu-id="cbd02-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="cbd02-119">Описывается динамическое создание баз данных и типичные сценарии использования этого метода.</span><span class="sxs-lookup"><span data-stu-id="cbd02-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="cbd02-120">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="cbd02-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="cbd02-121">Описываются методы устранения проблем оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="cbd02-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
