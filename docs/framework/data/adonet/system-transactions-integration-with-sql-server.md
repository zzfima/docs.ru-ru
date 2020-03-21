---
title: Интеграция System.Transactions с SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 42007dafbdc9f61b9fc0776e0aaa2987551b704a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174242"
---
# <a name="systemtransactions-integration-with-sql-server"></a><span data-ttu-id="71a9d-102">Интеграция System.Transactions с SQL Server</span><span class="sxs-lookup"><span data-stu-id="71a9d-102">System.Transactions Integration with SQL Server</span></span>
<span data-ttu-id="71a9d-103">В версии .NET Framework 2.0 была введена <xref:System.Transactions> рамка транзакций, к которым можно получить доступ через пространство имен.</span><span class="sxs-lookup"><span data-stu-id="71a9d-103">The .NET Framework version 2.0 introduced a transaction framework that can be accessed through the <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="71a9d-104">Эта основа предоставляет транзакции таким образом, чтобы полностью интегрированы в рамочную систему .NET, включая ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="71a9d-104">This framework exposes transactions in a way that is fully integrated in the .NET Framework, including ADO.NET.</span></span>  
  
 <span data-ttu-id="71a9d-105">В дополнение к улучшениям программируемости <xref:System.Transactions> и ADO.NET могут работать вместе, чтобы координировать оптимизацию при работе с транзакциями.</span><span class="sxs-lookup"><span data-stu-id="71a9d-105">In addition to the programmability enhancements, <xref:System.Transactions> and ADO.NET can work together to coordinate optimizations when you work with transactions.</span></span> <span data-ttu-id="71a9d-106">Повышаемая транзакция — это упрощенная (локальная) транзакция, которая по необходимости может быть автоматически повышена до полностью распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-106">A promotable transaction is a lightweight (local) transaction that can be automatically promoted to a fully distributed transaction on an as-needed basis.</span></span>  
  
 <span data-ttu-id="71a9d-107">Начиная с ADO.NET 2.0, <xref:System.Data.SqlClient> поддерживает промо-транзакции при работе с сервером S'L.</span><span class="sxs-lookup"><span data-stu-id="71a9d-107">Starting with ADO.NET 2.0, <xref:System.Data.SqlClient> supports promotable transactions when you work with SQL Server.</span></span> <span data-ttu-id="71a9d-108">Повышаемая транзакция не вызывает дополнительную нагрузку распределенной транзакции, если таковая не требуется.</span><span class="sxs-lookup"><span data-stu-id="71a9d-108">A promotable transaction does not invoke the added overhead of a distributed transaction unless the added overhead is required.</span></span> <span data-ttu-id="71a9d-109">Промоданные транзакции являются автоматическими и не требуют вмешательства со стороны разработчика.</span><span class="sxs-lookup"><span data-stu-id="71a9d-109">Promotable transactions are automatic and require no intervention from the developer.</span></span>  
  
 <span data-ttu-id="71a9d-110">Промоируемые транзакции доступны только при использовании поставщика рамочных данных .NET для сервера S'L Server ()`SqlClient`с сервером S'L.</span><span class="sxs-lookup"><span data-stu-id="71a9d-110">Promotable transactions are only available when you use the .NET Framework Data Provider for SQL Server (`SqlClient`) with SQL Server.</span></span>  
  
## <a name="creating-promotable-transactions"></a><span data-ttu-id="71a9d-111">Создание повышаемых транзакций</span><span class="sxs-lookup"><span data-stu-id="71a9d-111">Creating Promotable Transactions</span></span>  
 <span data-ttu-id="71a9d-112">Рамочный провайдер .NET для сервера S'L обеспечивает поддержку промо-транзакций, <xref:System.Transactions> которые обрабатываются через классы в пространстве имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="71a9d-112">The .NET Framework Provider for SQL Server provides support for promotable transactions, which are handled through the classes in the .NET Framework <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="71a9d-113">Повышаемые транзакции оптимизируют работу с распределенными транзакциями за счет отсрочки создания распределенной транзакции до того момента, когда она будет необходима.</span><span class="sxs-lookup"><span data-stu-id="71a9d-113">Promotable transactions optimize distributed transactions by deferring creating a distributed transaction until it is needed.</span></span> <span data-ttu-id="71a9d-114">Если требуется только один диспетчер ресурсов, то распределенная транзакция не создается.</span><span class="sxs-lookup"><span data-stu-id="71a9d-114">If only one resource manager is required, no distributed transaction occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71a9d-115">В частично доверенном сценарии при повышении транзакции до распределенной требуется право доступа <xref:System.Transactions.DistributedTransactionPermission> .</span><span class="sxs-lookup"><span data-stu-id="71a9d-115">In a partially trusted scenario, the <xref:System.Transactions.DistributedTransactionPermission> is required when a transaction is promoted to a distributed transaction.</span></span>  
  
## <a name="promotable-transaction-scenarios"></a><span data-ttu-id="71a9d-116">Сценарии использования повышаемых транзакций</span><span class="sxs-lookup"><span data-stu-id="71a9d-116">Promotable Transaction Scenarios</span></span>  
 <span data-ttu-id="71a9d-117">Как правило, для распределенных транзакций требуются значительные системные ресурсы, поскольку они управляются координатором распределенных транзакций (Майкрософт), который интегрирует все диспетчеры ресурсов, используемые в транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-117">Distributed transactions typically consume significant system resources, being managed by Microsoft Distributed Transaction Coordinator (MS DTC), which integrates all the resource managers accessed in the transaction.</span></span> <span data-ttu-id="71a9d-118">Продуютная транзакция — <xref:System.Transactions> это особая форма транзакции, которая фактически делегирует работу на простую транзакцию s'L Server.</span><span class="sxs-lookup"><span data-stu-id="71a9d-118">A promotable transaction is a special form of a <xref:System.Transactions> transaction that effectively delegates the work to a simple SQL Server transaction.</span></span> <span data-ttu-id="71a9d-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, , и сервер S'L координировать работу, связанную с обработкой транзакции, продвигая его к полностью распределенной транзакции по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="71a9d-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, and SQL Server coordinate the work involved in handling the transaction, promoting it to a full distributed transaction as needed.</span></span>  
  
 <span data-ttu-id="71a9d-120">Преимущество использования повышаемых транзакций заключается в том, что при открытии соединения с помощью активной транзакции <xref:System.Transactions.TransactionScope> и отсутствии других открытых соединений такая транзакция фиксируется как упрощенная, что позволяет избежать излишних затрат ресурсов на полностью распределенную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="71a9d-120">The benefit of using promotable transactions is that when a connection is opened by using an active <xref:System.Transactions.TransactionScope> transaction, and no other connections are opened, the transaction commits as a lightweight transaction, instead of incurring the additional overhead of a full distributed transaction.</span></span>  
  
### <a name="connection-string-keywords"></a><span data-ttu-id="71a9d-121">Ключевые слова в строке подключения</span><span class="sxs-lookup"><span data-stu-id="71a9d-121">Connection String Keywords</span></span>  
 <span data-ttu-id="71a9d-122">В свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> поддерживается использование ключевого слова `Enlist`, которое указывает, будет ли клиент <xref:System.Data.SqlClient> обнаруживать контексты транзакций и автоматически прикреплять соединение к распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-122">The <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property supports a keyword, `Enlist`, which indicates whether <xref:System.Data.SqlClient> will detect transactional contexts and automatically enlist the connection in a distributed transaction.</span></span> <span data-ttu-id="71a9d-123">Если `Enlist=true`, то соединение автоматически прикрепляется к текущему контексту транзакции открывающего потока.</span><span class="sxs-lookup"><span data-stu-id="71a9d-123">If `Enlist=true`, the connection is automatically enlisted in the opening thread's current transaction context.</span></span> <span data-ttu-id="71a9d-124">Если `Enlist=false`, то соединение `SqlClient` не будет взаимодействовать с распределенной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="71a9d-124">If `Enlist=false`, the `SqlClient` connection does not interact with a distributed transaction.</span></span> <span data-ttu-id="71a9d-125">Значение `Enlist` по умолчанию - true.</span><span class="sxs-lookup"><span data-stu-id="71a9d-125">The default value for `Enlist` is true.</span></span> <span data-ttu-id="71a9d-126">Если ключевое слово `Enlist` в строке соединения не задано, то соединение автоматически прикрепляется к распределенной транзакции, если она будет обнаружена при открытии соединения.</span><span class="sxs-lookup"><span data-stu-id="71a9d-126">If `Enlist` is not specified in the connection string, the connection is automatically enlisted in a distributed transaction if one is detected when the connection is opened.</span></span>  
  
 <span data-ttu-id="71a9d-127">Ключевые слова `Transaction Binding` в строке соединения <xref:System.Data.SqlClient.SqlConnection> управляют связью соединения с прикрепленной транзакцией `System.Transactions` .</span><span class="sxs-lookup"><span data-stu-id="71a9d-127">The `Transaction Binding` keywords in a <xref:System.Data.SqlClient.SqlConnection> connection string control the connection's association with an enlisted `System.Transactions` transaction.</span></span> <span data-ttu-id="71a9d-128">Эта связь также доступна через свойство <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> построителя <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="71a9d-128">It is also available through the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> property of a <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="71a9d-129">В следующей таблице описаны возможные значения.</span><span class="sxs-lookup"><span data-stu-id="71a9d-129">The following table describes the possible values.</span></span>  
  
|<span data-ttu-id="71a9d-130">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="71a9d-130">Keyword</span></span>|<span data-ttu-id="71a9d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="71a9d-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71a9d-132">Implicit Unbind</span><span class="sxs-lookup"><span data-stu-id="71a9d-132">Implicit Unbind</span></span>|<span data-ttu-id="71a9d-133">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71a9d-133">The default.</span></span> <span data-ttu-id="71a9d-134">Соединение отсоединяется от транзакции по ее завершении, вновь переходя в режим автоматической фиксации.</span><span class="sxs-lookup"><span data-stu-id="71a9d-134">The connection detaches from the transaction when it ends, switching back to autocommit mode.</span></span>|  
|<span data-ttu-id="71a9d-135">Explicit Unbind</span><span class="sxs-lookup"><span data-stu-id="71a9d-135">Explicit Unbind</span></span>|<span data-ttu-id="71a9d-136">Соединение остается прикрепленным к транзакции до ее закрытия.</span><span class="sxs-lookup"><span data-stu-id="71a9d-136">The connection remains attached to the transaction until the transaction is closed.</span></span> <span data-ttu-id="71a9d-137">Соединение будет потеряно, если связанная с ним транзакция не активна или не соответствует <xref:System.Transactions.Transaction.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="71a9d-137">The connection will fail if the associated transaction is not active or does not match <xref:System.Transactions.Transaction.Current%2A>.</span></span>|  
  
## <a name="using-transactionscope"></a><span data-ttu-id="71a9d-138">Использование класса TransactionScope</span><span class="sxs-lookup"><span data-stu-id="71a9d-138">Using TransactionScope</span></span>  
 <span data-ttu-id="71a9d-139">Класс <xref:System.Transactions.TransactionScope> делает блок кода транзакционным, неявно прикрепляя соединения к распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-139">The <xref:System.Transactions.TransactionScope> class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="71a9d-140">В конце блока <xref:System.Transactions.TransactionScope.Complete%2A> перед тем, как выйти из него, необходимо вызвать метод <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="71a9d-140">You must call the <xref:System.Transactions.TransactionScope.Complete%2A> method at the end of the <xref:System.Transactions.TransactionScope> block before leaving it.</span></span> <span data-ttu-id="71a9d-141">При выходе из этого блока вызывается метод <xref:System.Transactions.TransactionScope.Dispose%2A> .</span><span class="sxs-lookup"><span data-stu-id="71a9d-141">Leaving the block invokes the <xref:System.Transactions.TransactionScope.Dispose%2A> method.</span></span> <span data-ttu-id="71a9d-142">При возникновении исключения, в результате которого исполнение кода выходит за пределы области, транзакция считается прерванной.</span><span class="sxs-lookup"><span data-stu-id="71a9d-142">If an exception has been thrown that causes the code to leave scope, the transaction is considered aborted.</span></span>  
  
 <span data-ttu-id="71a9d-143">Рекомендуется использовать блок `using` , чтобы гарантировать вызов метода <xref:System.Transactions.TransactionScope.Dispose%2A> для объекта <xref:System.Transactions.TransactionScope> при выходе из блока using.</span><span class="sxs-lookup"><span data-stu-id="71a9d-143">We recommend that you use a `using` block to make sure that <xref:System.Transactions.TransactionScope.Dispose%2A> is called on the <xref:System.Transactions.TransactionScope> object when the using block is exited.</span></span> <span data-ttu-id="71a9d-144">Неудачная попытка зафиксировать или откатить незавершенные транзакции может значительно снизить производительность, поскольку время ожидания по умолчанию для объекта <xref:System.Transactions.TransactionScope> составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="71a9d-144">Failure to commit or roll back pending transactions can significantly damage performance because the default time-out for the <xref:System.Transactions.TransactionScope> is one minute.</span></span> <span data-ttu-id="71a9d-145">Если инструкция `using` не используется, необходимо явно выполнить все действия в блоке `Try` и вызвать метод <xref:System.Transactions.TransactionScope.Dispose%2A> в блоке `Finally`.</span><span class="sxs-lookup"><span data-stu-id="71a9d-145">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the <xref:System.Transactions.TransactionScope.Dispose%2A> method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="71a9d-146">Если в объекте <xref:System.Transactions.TransactionScope>возникает исключение, транзакция помечается как несогласованная и прерывается.</span><span class="sxs-lookup"><span data-stu-id="71a9d-146">If an exception occurs in the <xref:System.Transactions.TransactionScope>, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="71a9d-147">При удалении объекта <xref:System.Transactions.TransactionScope> будет произведен ее откат.</span><span class="sxs-lookup"><span data-stu-id="71a9d-147">It will be rolled back when the <xref:System.Transactions.TransactionScope> is disposed.</span></span> <span data-ttu-id="71a9d-148">Если исключений не возникает, то участвующие транзакции будут зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="71a9d-148">If no exception occurs, participating transactions commit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71a9d-149">Класс `TransactionScope` создает транзакцию с уровнем изоляции <xref:System.Transactions.Transaction.IsolationLevel%2A>, равным `Serializable` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71a9d-149">The `TransactionScope` class creates a transaction with a <xref:System.Transactions.Transaction.IsolationLevel%2A> of `Serializable` by default.</span></span> <span data-ttu-id="71a9d-150">В зависимости от приложения уровень изоляции можно понижать во избежание большого количества состязаний данных в приложении.</span><span class="sxs-lookup"><span data-stu-id="71a9d-150">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71a9d-151">В рамках распределенных транзакций рекомендуется выполнять только операции обновления, вставки и удаления, поскольку они потребляют значительные ресурсы базы данных.</span><span class="sxs-lookup"><span data-stu-id="71a9d-151">We recommend that you perform only updates, inserts, and deletes within distributed transactions because they consume significant database resources.</span></span> <span data-ttu-id="71a9d-152">Инструкции выборки могут без необходимости блокировать ресурсы базы данных, и в некоторых случаях для выборки может потребоваться использование транзакций.</span><span class="sxs-lookup"><span data-stu-id="71a9d-152">Select statements may lock database resources unnecessarily, and in some scenarios, you may have to use transactions for selects.</span></span> <span data-ttu-id="71a9d-153">Любые не связанные с базой данных действия должны выполняться за пределами области транзакции, если только в ней не задействованы другие диспетчеры ресурсов транзакций.</span><span class="sxs-lookup"><span data-stu-id="71a9d-153">Any non-database work should be done outside the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="71a9d-154">Хотя исключение в области транзакции не позволяет зафиксировать транзакцию, класс <xref:System.Transactions.TransactionScope> не имеет возможности отката каких-либо изменений, внесенных кодом за пределами области самой транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-154">Although an exception in the scope of the transaction prevents the transaction from committing, the <xref:System.Transactions.TransactionScope> class has no provision for rolling back any changes your code has made outside the scope of the transaction itself.</span></span> <span data-ttu-id="71a9d-155">При необходимости предпринять какие-либо действия, когда производится откат транзакции, следует написать собственную реализацию интерфейса <xref:System.Transactions.IEnlistmentNotification> и явно прикрепить его к транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-155">If you have to take some action when the transaction is rolled back, you must write your own implementation of the <xref:System.Transactions.IEnlistmentNotification> interface and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a9d-156">Пример</span><span class="sxs-lookup"><span data-stu-id="71a9d-156">Example</span></span>  
 <span data-ttu-id="71a9d-157">Для работы с <xref:System.Transactions> необходима ссылка на файл System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="71a9d-157">Working with <xref:System.Transactions> requires that you have a reference to System.Transactions.dll.</span></span>  
  
 <span data-ttu-id="71a9d-158">Следующая функция показывает, как создать повышаемую транзакцию для двух разных экземпляров SQL Server, представленных двумя разными объектами <xref:System.Data.SqlClient.SqlConnection> , которые заключены в оболочку с помощью блок <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="71a9d-158">The following function demonstrates how to create a promotable transaction against two different SQL Server instances, represented by two different <xref:System.Data.SqlClient.SqlConnection> objects, which are wrapped in a <xref:System.Transactions.TransactionScope> block.</span></span> <span data-ttu-id="71a9d-159">В коде создается блок <xref:System.Transactions.TransactionScope> с инструкцией `using` и открывается первое соединение, которое автоматически прикрепляется к транзакции <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="71a9d-159">The code creates the <xref:System.Transactions.TransactionScope> block with a `using` statement and opens the first connection, which automatically enlists it in the <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="71a9d-160">Изначально транзакция прикрепляется как упрощенная, а не полностью распределенная транзакция.</span><span class="sxs-lookup"><span data-stu-id="71a9d-160">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="71a9d-161">Второе соединение прикрепляется к транзакции <xref:System.Transactions.TransactionScope> , только если при выполнении команды в первом соединении не возникает исключения.</span><span class="sxs-lookup"><span data-stu-id="71a9d-161">The second connection is enlisted in the <xref:System.Transactions.TransactionScope> only if the command in the first connection does not throw an exception.</span></span> <span data-ttu-id="71a9d-162">При открытии второго соединения транзакция автоматически повышается до полностью распределенной.</span><span class="sxs-lookup"><span data-stu-id="71a9d-162">When the second connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="71a9d-163">Вызывается метод <xref:System.Transactions.TransactionScope.Complete%2A> , который фиксирует транзакцию, только если не возникло ни одного исключения.</span><span class="sxs-lookup"><span data-stu-id="71a9d-163">The <xref:System.Transactions.TransactionScope.Complete%2A> method is invoked, which commits the transaction only if no exceptions have been thrown.</span></span> <span data-ttu-id="71a9d-164">Если в любой точке блока <xref:System.Transactions.TransactionScope> возникло исключение, метод `Complete` вызван не будет и при удалении транзакции <xref:System.Transactions.TransactionScope> в конце ее блока `using` будет произведен откат распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="71a9d-164">If an exception has been thrown at any point in the <xref:System.Transactions.TransactionScope> block, `Complete` will not be called, and the distributed transaction will roll back when the <xref:System.Transactions.TransactionScope> is disposed at the end of its `using` block.</span></span>  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="71a9d-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="71a9d-165">See also</span></span>

- [<span data-ttu-id="71a9d-166">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="71a9d-166">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="71a9d-167">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="71a9d-167">ADO.NET Overview</span></span>](ado-net-overview.md)
