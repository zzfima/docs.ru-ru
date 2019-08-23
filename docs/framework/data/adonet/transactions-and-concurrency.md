---
title: Транзакции и параллельность
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: c78031150d9b1209372dece49813dfcf0a03b9d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965216"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="920f6-102">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="920f6-102">Transactions and Concurrency</span></span>
<span data-ttu-id="920f6-103">Транзакция состоит из одной команды или группы команд, которые выполняются как пакет.</span><span class="sxs-lookup"><span data-stu-id="920f6-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="920f6-104">Транзакции позволяют объединить несколько операций в одну единицу работы.</span><span class="sxs-lookup"><span data-stu-id="920f6-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="920f6-105">Если в какой-либо точке транзакции возникает ошибка, может быть выполнен откат всех обновлений к их состоянию до начала транзакции.</span><span class="sxs-lookup"><span data-stu-id="920f6-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="920f6-106">Для обеспечения согласованности данных транзакция должна соответствовать свойствам ACID (атомарность, согласованность, изоляция и устойчивость).</span><span class="sxs-lookup"><span data-stu-id="920f6-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="920f6-107">Большая часть систем реляционных баз данных, таких как Microsoft SQL Server, поддерживает транзакции, предоставляя блокировку, ведение журнала и средства управления транзакцией при выполнении клиентским приложением операций обновления, вставки или удаления.</span><span class="sxs-lookup"><span data-stu-id="920f6-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="920f6-108">Транзакции, которые задействуют множество ресурсов, могут снизить параллелизм, если слишком долго удерживают блокировки.</span><span class="sxs-lookup"><span data-stu-id="920f6-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="920f6-109">Поэтому транзакции следует делать как можно короче.</span><span class="sxs-lookup"><span data-stu-id="920f6-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="920f6-110">В том случае, если в транзакции участвует несколько таблиц одной базы данных или одного сервера, явные транзакции в хранимых процедурах часто выполняются лучше.</span><span class="sxs-lookup"><span data-stu-id="920f6-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="920f6-111">Транзакции можно создавать в хранимых процедурах SQL Server с использованием инструкций Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` и `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="920f6-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="920f6-112">Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="920f6-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="920f6-113">Для транзакций, включающих различные диспетчеры ресурсов, например транзакцию между SQL Server и Oracle, требуется распределенная транзакция.</span><span class="sxs-lookup"><span data-stu-id="920f6-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="920f6-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="920f6-114">In This Section</span></span>  
 [<span data-ttu-id="920f6-115">Локальные транзакции</span><span class="sxs-lookup"><span data-stu-id="920f6-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="920f6-116">Демонстрирует выполнение транзакций на базе данных.</span><span class="sxs-lookup"><span data-stu-id="920f6-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="920f6-117">Распределенные транзакции</span><span class="sxs-lookup"><span data-stu-id="920f6-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="920f6-118">Описывает выполнение распределенных транзакций в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="920f6-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="920f6-119">Интеграция System.Transactions с SQL Server</span><span class="sxs-lookup"><span data-stu-id="920f6-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="920f6-120">Описывает <xref:System.Transactions> интеграцию с SQL Server для работы с распределенными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="920f6-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="920f6-121">Оптимистическая блокировка</span><span class="sxs-lookup"><span data-stu-id="920f6-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="920f6-122">Описывается оптимистичный и пессимистичный параллелизм и проверка на выявление нарушений параллелизма.</span><span class="sxs-lookup"><span data-stu-id="920f6-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920f6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="920f6-123">See also</span></span>

- [<span data-ttu-id="920f6-124">Основные сведения о транзакциях</span><span class="sxs-lookup"><span data-stu-id="920f6-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)
- [<span data-ttu-id="920f6-125">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="920f6-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="920f6-126">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="920f6-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="920f6-127">Объекты DataAdapter и DataReader</span><span class="sxs-lookup"><span data-stu-id="920f6-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="920f6-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="920f6-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [<span data-ttu-id="920f6-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="920f6-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
