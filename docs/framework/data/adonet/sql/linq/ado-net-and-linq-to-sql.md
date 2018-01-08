---
title: "ADO.NET и LINQ to SQL"
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
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ae0b5aeb658b67434cea187839833e24007ee77e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="1ea1d-102">ADO.NET и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1ea1d-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="1ea1d-103">является частью [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] семейства технологий.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-103"> is part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies.</span></span> <span data-ttu-id="1ea1d-104">Он основан на службах, предоставленных моделью поставщика [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ea1d-104">It is based on services provided by the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] provider model.</span></span> <span data-ttu-id="1ea1d-105">Таким образом можно смешивать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] кода с существующими [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] приложений и выполнять переход с текущих [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] решения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ea1d-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applications and migrate current [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="1ea1d-106">На следующем рисунке показано общее представление связи.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="1ea1d-107">![LINQ to SQL и ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="1ea1d-107">![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="1ea1d-108">Подключения</span><span class="sxs-lookup"><span data-stu-id="1ea1d-108">Connections</span></span>  
 <span data-ttu-id="1ea1d-109">Можно использовать существующее [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] при создании соединения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-109">You can supply an existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="1ea1d-110">Все операции с <xref:System.Data.Linq.DataContext> (включая запросы) использоваться.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="1ea1d-111">Если соединение уже открыто, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оставит его как при завершении работы с ним.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="1ea1d-112">Для постоянного доступа к подключению и его закрытия можно использовать свойство <xref:System.Data.Linq.DataContext.Connection%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="1ea1d-113">Транзакции</span><span class="sxs-lookup"><span data-stu-id="1ea1d-113">Transactions</span></span>  
 <span data-ttu-id="1ea1d-114">Когда приложение уже инициировало транзакцию и в нее требуется включить <xref:System.Data.Linq.DataContext>, его можно добавить в собственную транзакцию базы данных<xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="1ea1d-115">Рекомендуемым методом выполнения транзакций с [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] является использование объекта <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-115">The preferred method of doing transactions with the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="1ea1d-116">Благодаря этому способу можно выполнить распределенные транзакции, работающие в базах данных и других находящихся в памяти диспетчерах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="1ea1d-117">Для запуска транзакций требуется незначительное количество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="1ea1d-118">Они преобразуются в распределенные транзакции только при наличии в области действия транзакции нескольких подключений.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="1ea1d-119">Этот способ не подходит для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="1ea1d-120">Например, подключение SqlClient не может повысить уровень системных транзакций, если используется на сервере [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ea1d-120">For example, the SqlClient connection cannot promote system transactions when it works against a [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] server.</span></span> <span data-ttu-id="1ea1d-121">Наоборот, оно автоматически включается в полную, распределенную транзакцию при каждом обнаружении используемой области действия транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="1ea1d-122">Прямые команды SQL</span><span class="sxs-lookup"><span data-stu-id="1ea1d-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="1ea1d-123">Иногда могут возникать ситуации, когда возможность <xref:System.Data.Linq.DataContext> осуществлять запросы или отправлять изменения будет недостаточной для выполнения специализированной задачи.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="1ea1d-124">В подобных случаях, чтобы запустить команды SQL в базе данных и преобразовать результаты запроса в объекты, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="1ea1d-125">Например, предположим, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2).</span><span class="sxs-lookup"><span data-stu-id="1ea1d-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="1ea1d-126">Следующий запрос возвращает последовательность двух объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="1ea1d-127">При условии, что имена столбцов в табличных результатах соответствуют свойствам столбцов класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты вне запроса SQL.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="1ea1d-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ea1d-128">Parameters</span></span>  
 <span data-ttu-id="1ea1d-129">Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> допускает использование параметров.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="1ea1d-130">В следующем коде выполняется параметризованный запрос.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="1ea1d-131">Параметры записываются в тексте запроса с использованием той же нотации с фигурными скобками, что и в методах `Console.WriteLine()` и `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="1ea1d-132">Метод `String.Format()` принимает указанную строку запроса и заменяет параметры в фигурных скобках на автоматически созданные имена, такие как `@p0`, `@p1`…, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="1ea1d-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea1d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1ea1d-133">See Also</span></span>  
 [<span data-ttu-id="1ea1d-134">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="1ea1d-134">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="1ea1d-135">Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext</span><span class="sxs-lookup"><span data-stu-id="1ea1d-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
