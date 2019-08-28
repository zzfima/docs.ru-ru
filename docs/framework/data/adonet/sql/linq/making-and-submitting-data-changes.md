---
title: Внесение и отправка изменений данных
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 699a8730f21ff290ad15d1932f565ab7a2478fb5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043987"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="9705c-102">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="9705c-102">Making and Submitting Data Changes</span></span>

<span data-ttu-id="9705c-103">В подразделах данного раздела описывается, как выполнять изменения и передавать их в базу данных, а также обрабатывать конфликты оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="9705c-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="9705c-104">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="9705c-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="9705c-105">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9705c-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="9705c-106">Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="9705c-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9705c-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9705c-107">In This Section</span></span>

<span data-ttu-id="9705c-108">[Практическое руководство. Вставка строк в базу данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-108">[How to: Insert Rows Into the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="9705c-109">Описывает, как вставлять строки в базу данных путем добавления объектов в модель объектов.</span><span class="sxs-lookup"><span data-stu-id="9705c-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="9705c-110">[Практическое руководство. Обновление строк в базе данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-110">[How to: Update Rows in the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="9705c-111">Описывается, как обновлять строки в базе данных путем обновления объектов в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="9705c-111">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="9705c-112">[Практическое руководство. Удаление строк из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-112">[How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="9705c-113">Описывается, как удалять строки из базы данных путем удаления объектов из объектной модели.</span><span class="sxs-lookup"><span data-stu-id="9705c-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="9705c-114">[Практическое руководство. Отправка изменений в базу данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-114">[How to: Submit Changes to the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="9705c-115">Описывается, как отправлять изменения объектной модели в базу данных.</span><span class="sxs-lookup"><span data-stu-id="9705c-115">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="9705c-116">[Практическое руководство. Скобки для отправки данных с помощью транзакций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-116">[How to: Bracket Data Submissions by Using Transactions](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="9705c-117">Описывается, как включать операции в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9705c-117">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="9705c-118">[Практическое руководство. Динамическое создание базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-118">[How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="9705c-119">Описывается динамическое создание баз данных и типичные сценарии использования этого метода.</span><span class="sxs-lookup"><span data-stu-id="9705c-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="9705c-120">[Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="9705c-120">[How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="9705c-121">Описываются методы устранения проблем оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="9705c-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
