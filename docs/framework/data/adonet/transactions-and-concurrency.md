---
title: Транзакции и параллельность
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 837fe6c42d64f7416dbd895e56a38d1a409e567a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791316"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="dc79f-102">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="dc79f-102">Transactions and Concurrency</span></span>
<span data-ttu-id="dc79f-103">Транзакция состоит из одной команды или группы команд, которые выполняются как пакет.</span><span class="sxs-lookup"><span data-stu-id="dc79f-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="dc79f-104">Транзакции позволяют объединить несколько операций в одну единицу работы.</span><span class="sxs-lookup"><span data-stu-id="dc79f-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="dc79f-105">Если в какой-либо точке транзакции возникает ошибка, может быть выполнен откат всех обновлений к их состоянию до начала транзакции.</span><span class="sxs-lookup"><span data-stu-id="dc79f-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="dc79f-106">Для обеспечения согласованности данных транзакция должна соответствовать свойствам ACID (атомарность, согласованность, изоляция и устойчивость).</span><span class="sxs-lookup"><span data-stu-id="dc79f-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="dc79f-107">Большая часть систем реляционных баз данных, таких как Microsoft SQL Server, поддерживает транзакции, предоставляя блокировку, ведение журнала и средства управления транзакцией при выполнении клиентским приложением операций обновления, вставки или удаления.</span><span class="sxs-lookup"><span data-stu-id="dc79f-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc79f-108">Транзакции, которые задействуют множество ресурсов, могут снизить параллелизм, если слишком долго удерживают блокировки.</span><span class="sxs-lookup"><span data-stu-id="dc79f-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="dc79f-109">Поэтому транзакции следует делать как можно короче.</span><span class="sxs-lookup"><span data-stu-id="dc79f-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="dc79f-110">В том случае, если в транзакции участвует несколько таблиц одной базы данных или одного сервера, явные транзакции в хранимых процедурах часто выполняются лучше.</span><span class="sxs-lookup"><span data-stu-id="dc79f-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="dc79f-111">Транзакции можно создавать в хранимых процедурах SQL Server с использованием инструкций Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` и `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="dc79f-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="dc79f-112">Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc79f-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="dc79f-113">Для транзакций, включающих различные диспетчеры ресурсов, например транзакцию между SQL Server и Oracle, требуется распределенная транзакция.</span><span class="sxs-lookup"><span data-stu-id="dc79f-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc79f-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="dc79f-114">In This Section</span></span>  
 [<span data-ttu-id="dc79f-115">Локальные транзакции</span><span class="sxs-lookup"><span data-stu-id="dc79f-115">Local Transactions</span></span>](local-transactions.md)  
 <span data-ttu-id="dc79f-116">Демонстрирует выполнение транзакций на базе данных.</span><span class="sxs-lookup"><span data-stu-id="dc79f-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="dc79f-117">Распределенные транзакции</span><span class="sxs-lookup"><span data-stu-id="dc79f-117">Distributed Transactions</span></span>](distributed-transactions.md)  
 <span data-ttu-id="dc79f-118">Описывает выполнение распределенных транзакций в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="dc79f-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="dc79f-119">Интеграция System.Transactions с SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc79f-119">System.Transactions Integration with SQL Server</span></span>](system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="dc79f-120">Описывает <xref:System.Transactions> интеграцию с SQL Server для работы с распределенными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="dc79f-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="dc79f-121">Оптимистическая блокировка</span><span class="sxs-lookup"><span data-stu-id="dc79f-121">Optimistic Concurrency</span></span>](optimistic-concurrency.md)  
 <span data-ttu-id="dc79f-122">Описывается оптимистичный и пессимистичный параллелизм и проверка на выявление нарушений параллелизма.</span><span class="sxs-lookup"><span data-stu-id="dc79f-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc79f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="dc79f-123">See also</span></span>

- [<span data-ttu-id="dc79f-124">Основные сведения о транзакциях</span><span class="sxs-lookup"><span data-stu-id="dc79f-124">Transaction Fundamentals</span></span>](../transactions/transaction-fundamentals.md)
- [<span data-ttu-id="dc79f-125">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="dc79f-125">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="dc79f-126">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="dc79f-126">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="dc79f-127">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="dc79f-127">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="dc79f-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="dc79f-128">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="dc79f-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dc79f-129">ADO.NET Overview</span></span>](ado-net-overview.md)
