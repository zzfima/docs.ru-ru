---
title: Внесение и отправка изменений данных
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 18468c9a2018a28e85d87155d98b0853854013fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792963"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="c6ff0-102">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="c6ff0-102">Making and Submitting Data Changes</span></span>

<span data-ttu-id="c6ff0-103">В подразделах данного раздела описывается, как выполнять изменения и передавать их в базу данных, а также обрабатывать конфликты оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="c6ff0-104">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="c6ff0-105">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c6ff0-105">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="c6ff0-106">Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c6ff0-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c6ff0-107">In This Section</span></span>

<span data-ttu-id="c6ff0-108">[Практическое руководство. Вставка строк в базу данных](how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-108">[How to: Insert Rows Into the Database](how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="c6ff0-109">Описывает, как вставлять строки в базу данных путем добавления объектов в модель объектов.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="c6ff0-110">[Практическое руководство. Обновление строк в базе данных](how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-110">[How to: Update Rows in the Database](how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="c6ff0-111">Описывается, как обновлять строки в базе данных путем обновления объектов в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-111">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="c6ff0-112">[Практическое руководство. Удаление строк из базы данных](how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-112">[How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="c6ff0-113">Описывается, как удалять строки из базы данных путем удаления объектов из объектной модели.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="c6ff0-114">[Практическое руководство. Отправка изменений в базу данных](how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-114">[How to: Submit Changes to the Database](how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="c6ff0-115">Описывается, как отправлять изменения объектной модели в базу данных.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-115">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="c6ff0-116">[Практическое руководство. Скобки для отправки данных с помощью транзакций](how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-116">[How to: Bracket Data Submissions by Using Transactions](how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="c6ff0-117">Описывается, как включать операции в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-117">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="c6ff0-118">[Практическое руководство. Динамическое создание базы данных](how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-118">[How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="c6ff0-119">Описывается динамическое создание баз данных и типичные сценарии использования этого метода.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="c6ff0-120">[Практическое руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="c6ff0-120">[How to: Manage Change Conflicts](how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="c6ff0-121">Описываются методы устранения проблем оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="c6ff0-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
