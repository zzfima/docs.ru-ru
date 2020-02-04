---
title: ADO.NET и LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 4d2376a2e32ff099497a5dbcd6cb68d8ed526884
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980006"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="5f269-102">ADO.NET и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5f269-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5f269-103">является частью семейства технологий ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="5f269-103">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="5f269-104">Он основан на службах, предоставляемых моделью поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="5f269-104">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="5f269-105">Таким образом, можно смешивать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] код с существующими приложениями ADO.NET и переносить текущие решения ADO.NET в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f269-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5f269-106">На следующем рисунке показано общее представление связи.</span><span class="sxs-lookup"><span data-stu-id="5f269-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="5f269-107">![LINQ to SQL и ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="5f269-107">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="5f269-108">Подключения</span><span class="sxs-lookup"><span data-stu-id="5f269-108">Connections</span></span>  
 <span data-ttu-id="5f269-109">При создании <xref:System.Data.Linq.DataContext>[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] можно указать существующее подключение к ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="5f269-109">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="5f269-110">Все операции с <xref:System.Data.Linq.DataContext> (включая запросы) используют это предоставленное соединение.</span><span class="sxs-lookup"><span data-stu-id="5f269-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="5f269-111">Если подключение уже открыто, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оставляет его как есть после завершения работы с ним.</span><span class="sxs-lookup"><span data-stu-id="5f269-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="5f269-112">Для постоянного доступа к подключению и его закрытия можно использовать свойство <xref:System.Data.Linq.DataContext.Connection%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="5f269-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="5f269-113">Транзакции</span><span class="sxs-lookup"><span data-stu-id="5f269-113">Transactions</span></span>  
 <span data-ttu-id="5f269-114">Когда приложение уже инициировало транзакцию и в нее требуется включить <xref:System.Data.Linq.DataContext>, его можно добавить в собственную транзакцию базы данных.</span><span class="sxs-lookup"><span data-stu-id="5f269-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="5f269-115">Предпочтительным методом выполнения транзакций с .NET Framework является использование объекта <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="5f269-115">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="5f269-116">Благодаря этому способу можно выполнить распределенные транзакции, работающие в базах данных и других находящихся в памяти диспетчерах ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5f269-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="5f269-117">Для запуска транзакций требуется незначительное количество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5f269-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="5f269-118">Они преобразуются в распределенные транзакции только при наличии в области действия транзакции нескольких подключений.</span><span class="sxs-lookup"><span data-stu-id="5f269-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="5f269-119">Этот способ не подходит для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="5f269-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="5f269-120">Например, соединение SqlClient не может повысить системные транзакции, если оно работает с сервером SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="5f269-120">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="5f269-121">Наоборот, оно автоматически включается в полную, распределенную транзакцию при каждом обнаружении используемой области действия транзакции.</span><span class="sxs-lookup"><span data-stu-id="5f269-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="5f269-122">Прямые команды SQL</span><span class="sxs-lookup"><span data-stu-id="5f269-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="5f269-123">Иногда могут возникать ситуации, когда возможность <xref:System.Data.Linq.DataContext> осуществлять запросы или отправлять изменения будет недостаточной для выполнения специализированной задачи.</span><span class="sxs-lookup"><span data-stu-id="5f269-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="5f269-124">В подобных случаях, чтобы запустить команды SQL в базе данных и преобразовать результаты запроса в объекты, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f269-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="5f269-125">Например, предположим, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2).</span><span class="sxs-lookup"><span data-stu-id="5f269-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="5f269-126">Следующий запрос возвращает последовательность двух объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="5f269-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="5f269-127">При условии, что имена столбцов в табличных результатах соответствуют свойствам столбца класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты из любого SQL запроса.</span><span class="sxs-lookup"><span data-stu-id="5f269-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="5f269-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f269-128">Parameters</span></span>  
 <span data-ttu-id="5f269-129">Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> допускает использование параметров.</span><span class="sxs-lookup"><span data-stu-id="5f269-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="5f269-130">В следующем коде выполняется параметризованный запрос.</span><span class="sxs-lookup"><span data-stu-id="5f269-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="5f269-131">Параметры записываются в тексте запроса с использованием той же нотации с фигурными скобками, что и в методах `Console.WriteLine()` и `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="5f269-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="5f269-132">Метод `String.Format()` принимает указанную строку запроса и заменяет параметры в фигурных скобках на автоматически созданные имена, такие как `@p0`, `@p1`…, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="5f269-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f269-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f269-133">See also</span></span>

- [<span data-ttu-id="5f269-134">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="5f269-134">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="5f269-135">Практическое руководство. Повторное использование соединения между командой ADO.NET и контекстом DataContext</span><span class="sxs-lookup"><span data-stu-id="5f269-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
