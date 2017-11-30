---
title: "Включение нескольких активных результирующих наборов"
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
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1d39d1666f63d7d6f7a6154a124280486c3fccce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-multiple-active-result-sets"></a><span data-ttu-id="d32af-102">Включение нескольких активных результирующих наборов</span><span class="sxs-lookup"><span data-stu-id="d32af-102">Enabling Multiple Active Result Sets</span></span>
<span data-ttu-id="d32af-103">Режим MARS - это новая возможность, которая в SQL Server используется для выполнения нескольких пакетов по одному соединению.</span><span class="sxs-lookup"><span data-stu-id="d32af-103">Multiple Active Result Sets (MARS) is a feature that works with SQL Server to allow the execution of multiple batches on a single connection.</span></span> <span data-ttu-id="d32af-104">Если для работы с SQL Server включен режим MARS, каждый используемый объект команды добавляет сеанс к соединению.</span><span class="sxs-lookup"><span data-stu-id="d32af-104">When MARS is enabled for use with SQL Server, each command object used adds a session to the connection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d32af-105">Один сеанс режима MARS открывает одно логическое соединение для использования самим режимом MARS, а затем - по одному логическому соединению для каждой активной команды.</span><span class="sxs-lookup"><span data-stu-id="d32af-105">A single MARS session opens one logical connection for MARS to use and then one logical connection for each active command.</span></span>  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a><span data-ttu-id="d32af-106">Включение и отключение режима MARS в строке соединения</span><span class="sxs-lookup"><span data-stu-id="d32af-106">Enabling and Disabling MARS in the Connection String</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d32af-107">В следующей строке подключения используется образец **AdventureWorks** базы данных в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d32af-107">The following connection strings use the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="d32af-108">Строки соединения, представленные в образце кода, предполагают, что база данных установлена на сервере MSSQL1.</span><span class="sxs-lookup"><span data-stu-id="d32af-108">The connection strings provided assume that the database is installed on a server named MSSQL1.</span></span> <span data-ttu-id="d32af-109">Измените строку соединения при необходимости в соответствии с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="d32af-109">Modify the connection string as necessary for your environment.</span></span>  
  
 <span data-ttu-id="d32af-110">По умолчанию режим MARS отключен.</span><span class="sxs-lookup"><span data-stu-id="d32af-110">The MARS feature is disabled by default.</span></span> <span data-ttu-id="d32af-111">Включить его можно, добавив в строку соединения ключевое слово «MultipleActiveResultSets=True».</span><span class="sxs-lookup"><span data-stu-id="d32af-111">It can be enabled by adding the "MultipleActiveResultSets=True" keyword pair to your connection string.</span></span> <span data-ttu-id="d32af-112">«True» — это единственное допустимое значение для включения режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-112">"True" is the only valid value for enabling MARS.</span></span> <span data-ttu-id="d32af-113">В следующем примере демонстрируется, как подключиться к экземпляру SQL Server, а также как указать, что режим MARS должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="d32af-113">The following example demonstrates how to connect to an instance of SQL Server and how to specify that MARS should be enabled.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 <span data-ttu-id="d32af-114">Отключить режим MARS можно, добавив в строку соединения ключевое слово «MultipleActiveResultSets=False».</span><span class="sxs-lookup"><span data-stu-id="d32af-114">You can disable MARS by adding the "MultipleActiveResultSets=False" keyword pair to your connection string.</span></span> <span data-ttu-id="d32af-115">«False» — это единственное допустимое значение для отключения режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-115">"False" is the only valid value for disabling MARS.</span></span> <span data-ttu-id="d32af-116">Следующая строка соединения показывает, как отключать режим MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-116">The following connection string demonstrates how to disable MARS.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a><span data-ttu-id="d32af-117">Особые рассуждения об использовании режима MARS</span><span class="sxs-lookup"><span data-stu-id="d32af-117">Special Considerations When Using MARS</span></span>  
 <span data-ttu-id="d32af-118">В общем случае необходимости изменять существующие приложения для использования соединений с режимом MARS быть не должно.</span><span class="sxs-lookup"><span data-stu-id="d32af-118">In general, existing applications should not need modification to use a MARS-enabled connection.</span></span> <span data-ttu-id="d32af-119">Однако если требуется использовать функцию режима MARS в приложениях, следует ознакомиться со следующими рассуждениями и понять их.</span><span class="sxs-lookup"><span data-stu-id="d32af-119">However, if you wish to use MARS features in your applications, you should understand the following special considerations.</span></span>  
  
### <a name="statement-interleaving"></a><span data-ttu-id="d32af-120">Чередование инструкций</span><span class="sxs-lookup"><span data-stu-id="d32af-120">Statement Interleaving</span></span>  
 <span data-ttu-id="d32af-121">На сервере операции режима MARS выполняются синхронно.</span><span class="sxs-lookup"><span data-stu-id="d32af-121">MARS operations execute synchronously on the server.</span></span> <span data-ttu-id="d32af-122">Разрешается чередование инструкций SELECT и BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="d32af-122">Statement interleaving of SELECT and BULK INSERT statements is allowed.</span></span> <span data-ttu-id="d32af-123">Однако инструкции на языке DML и языке DDL выполняются атомарным образом.</span><span class="sxs-lookup"><span data-stu-id="d32af-123">However, data manipulation language (DML) and data definition language (DDL) statements execute atomically.</span></span> <span data-ttu-id="d32af-124">Попытка выполнения любых инструкций во время выполнения атомарного пакета блокируется.</span><span class="sxs-lookup"><span data-stu-id="d32af-124">Any statements attempting to execute while an atomic batch is executing are blocked.</span></span> <span data-ttu-id="d32af-125">Параллельное выполнение на сервере не является функцией режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-125">Parallel execution at the server is not a MARS feature.</span></span>  
  
 <span data-ttu-id="d32af-126">Если в рамках соединения режима MARS подаются два пакета (один с инструкцией SELECT, другой с инструкцией DML), выполнение инструкции DML может начаться во время выполнения инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="d32af-126">If two batches are submitted under a MARS connection, one of them containing a SELECT statement, the other containing a DML statement, the DML can begin execution within execution of the SELECT statement.</span></span> <span data-ttu-id="d32af-127">Однако выполнение инструкции SELECT может быть продолжено только после полного выполнения инструкции DML.</span><span class="sxs-lookup"><span data-stu-id="d32af-127">However, the DML statement must run to completion before the SELECT statement can make progress.</span></span> <span data-ttu-id="d32af-128">Если обе инструкции выполняются в рамках одной транзакции, любые изменения, внесенные инструкцией DML после начала выполнения инструкции SELECT, являются невидимыми для операции чтения.</span><span class="sxs-lookup"><span data-stu-id="d32af-128">If both statements are running under the same transaction, any changes made by a DML statement after the SELECT statement has started execution are not visible to the read operation.</span></span>  
  
 <span data-ttu-id="d32af-129">Инструкция WAITFOR внутри инструкции SELECT не выдает транзакцию во время ожидания, то есть пока не будет сформирована первая строка.</span><span class="sxs-lookup"><span data-stu-id="d32af-129">A WAITFOR statement inside a SELECT statement does not yield the transaction while it is waiting, that is, until the first row is produced.</span></span> <span data-ttu-id="d32af-130">А это означает, что пока инструкция WAITFOR ждет, другие пакеты не могут выполняться в рамках одного соединения.</span><span class="sxs-lookup"><span data-stu-id="d32af-130">This implies that no other batches can execute within the same connection while a WAITFOR statement is waiting.</span></span>  
  
### <a name="mars-session-cache"></a><span data-ttu-id="d32af-131">Кэш сеанса режима MARS</span><span class="sxs-lookup"><span data-stu-id="d32af-131">MARS Session Cache</span></span>  
 <span data-ttu-id="d32af-132">При открытии соединения с включенным режимом MARS создается логический сеанс, что требует дополнительных затрат.</span><span class="sxs-lookup"><span data-stu-id="d32af-132">When a connection is opened with MARS enabled, a logical session is created, which adds additional overhead.</span></span> <span data-ttu-id="d32af-133">Чтобы свести к минимуму нагрузку и повысить производительность, **SqlClient** кэширует сеанс режима MARS в рамках соединения.</span><span class="sxs-lookup"><span data-stu-id="d32af-133">To minimize overhead and enhance performance, **SqlClient** caches the MARS session within a connection.</span></span> <span data-ttu-id="d32af-134">Кэш может содержать максимум 10 сеансов режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-134">The cache contains at most 10 MARS sessions.</span></span> <span data-ttu-id="d32af-135">Это значение не может быть изменено пользователем.</span><span class="sxs-lookup"><span data-stu-id="d32af-135">This value is not user adjustable.</span></span> <span data-ttu-id="d32af-136">При достижении лимита сеансов создается новый сеанс - ошибка не формируется.</span><span class="sxs-lookup"><span data-stu-id="d32af-136">If the session limit is reached, a new session is created—an error is not generated.</span></span> <span data-ttu-id="d32af-137">Сам кэш и содержащиеся в нем сеансы принадлежат одному соединению, они не могут использоваться в нескольких соединениях.</span><span class="sxs-lookup"><span data-stu-id="d32af-137">The cache and sessions contained in it are per-connection; they are not shared across connections.</span></span> <span data-ttu-id="d32af-138">Когда сеанс освобождается, он возвращается в пул, если только не был достигнут верхний предел пула.</span><span class="sxs-lookup"><span data-stu-id="d32af-138">When a session is released, it is returned to the pool unless the pool's upper limit has been reached.</span></span> <span data-ttu-id="d32af-139">Если пул кэша заполнен, то сеанс закрывается.</span><span class="sxs-lookup"><span data-stu-id="d32af-139">If the cache pool is full, the session is closed.</span></span> <span data-ttu-id="d32af-140">Сеансы режима MARS не имеют срока действия.</span><span class="sxs-lookup"><span data-stu-id="d32af-140">MARS sessions do not expire.</span></span> <span data-ttu-id="d32af-141">Они очищаются только при удалении объекта соединения.</span><span class="sxs-lookup"><span data-stu-id="d32af-141">They are only cleaned up when the connection object is disposed.</span></span> <span data-ttu-id="d32af-142">Кэш сеансов режима MARS предварительно не загружается.</span><span class="sxs-lookup"><span data-stu-id="d32af-142">The MARS session cache is not preloaded.</span></span> <span data-ttu-id="d32af-143">Он загружается, когда приложению требуется больше сеансов.</span><span class="sxs-lookup"><span data-stu-id="d32af-143">It is loaded as the application requires more sessions.</span></span>  
  
### <a name="thread-safety"></a><span data-ttu-id="d32af-144">Потокобезопасность</span><span class="sxs-lookup"><span data-stu-id="d32af-144">Thread Safety</span></span>  
 <span data-ttu-id="d32af-145">Операции режима MARS не обеспечивают безопасность потока.</span><span class="sxs-lookup"><span data-stu-id="d32af-145">MARS operations are not thread-safe.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="d32af-146">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="d32af-146">Connection Pooling</span></span>  
 <span data-ttu-id="d32af-147">Как и любые другие соединения, соединения, для которых включен режим MARS, организуются в пулы.</span><span class="sxs-lookup"><span data-stu-id="d32af-147">MARS-enabled connections are pooled like any other connection.</span></span> <span data-ttu-id="d32af-148">Если приложение открывает два соединения (одно с включенным режимом MARS и другое, для которого режим MARS отключен), два эти соединения помещаются в отдельные пулы.</span><span class="sxs-lookup"><span data-stu-id="d32af-148">If an application opens two connections, one with MARS enabled and one with MARS disabled, the two connections are in separate pools.</span></span> <span data-ttu-id="d32af-149">Дополнительные сведения см. в разделе [SQL пулов соединений Server (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="d32af-149">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
### <a name="sql-server-batch-execution-environment"></a><span data-ttu-id="d32af-150">Среда выполнения пакетов SQL Server</span><span class="sxs-lookup"><span data-stu-id="d32af-150">SQL Server Batch Execution Environment</span></span>  
 <span data-ttu-id="d32af-151">При открытии соединения определяется среда по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d32af-151">When a connection is opened, a default environment is defined.</span></span> <span data-ttu-id="d32af-152">Затем эта среда копируется в логический сеанс режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-152">This environment is then copied into a logical MARS session.</span></span>  
  
 <span data-ttu-id="d32af-153">Среда пакетного выполнения состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="d32af-153">The batch execution environment includes the following components:</span></span>  
  
-   <span data-ttu-id="d32af-154">Заданных параметров (например, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span><span class="sxs-lookup"><span data-stu-id="d32af-154">Set options (for example, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span></span>  
  
-   <span data-ttu-id="d32af-155">Контекста безопасности (роль пользователя-приложения)</span><span class="sxs-lookup"><span data-stu-id="d32af-155">Security context (user/application role)</span></span>  
  
-   <span data-ttu-id="d32af-156">Контекста базы данных (текущая база данных)</span><span class="sxs-lookup"><span data-stu-id="d32af-156">Database context (current database)</span></span>  
  
-   <span data-ttu-id="d32af-157">Переменных состояния выполнения (например, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span><span class="sxs-lookup"><span data-stu-id="d32af-157">Execution state variables (for example, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span></span>  
  
-   <span data-ttu-id="d32af-158">Временных таблиц верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="d32af-158">Top-level temporary tables</span></span>  
  
 <span data-ttu-id="d32af-159">При работе в режиме MARS среда выполнения по умолчанию ассоциируется с соединением.</span><span class="sxs-lookup"><span data-stu-id="d32af-159">With MARS, a default execution environment is associated to a connection.</span></span> <span data-ttu-id="d32af-160">Каждый новый пакет, начинающий выполнение в рамках данного соединения, получает копию среды по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d32af-160">Every new batch that starts executing under a given connection receives a copy of the default environment.</span></span> <span data-ttu-id="d32af-161">Всякий раз при выполнении кода все изменения в среде выполнения применяются к данному конкретному пакету.</span><span class="sxs-lookup"><span data-stu-id="d32af-161">Whenever code is executed under a given batch, all changes made to the environment are scoped to the specific batch.</span></span> <span data-ttu-id="d32af-162">Как только выполнение завершается, настройки выполнения копируются в среду по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d32af-162">Once execution finishes, the execution settings are copied into the default environment.</span></span> <span data-ttu-id="d32af-163">Если один пакет выдает несколько команд для последовательного выполнения в рамках одной транзакции, семантика такая же, как и при прошлых соединениях клиентов или серверов.</span><span class="sxs-lookup"><span data-stu-id="d32af-163">In the case of a single batch issuing several commands to be executed sequentially under the same transaction, semantics are the same as those exposed by connections involving earlier clients or servers.</span></span>  
  
### <a name="parallel-execution"></a><span data-ttu-id="d32af-164">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="d32af-164">Parallel Execution</span></span>  
 <span data-ttu-id="d32af-165">Режим MARS не предназначен для использования во всех ситуациях, когда приложению требуется несколько соединений.</span><span class="sxs-lookup"><span data-stu-id="d32af-165">MARS is not designed to remove all requirements for multiple connections in an application.</span></span> <span data-ttu-id="d32af-166">Если приложению требуется настоящее параллельное выполнение команд для сервера, следует использовать несколько соединений.</span><span class="sxs-lookup"><span data-stu-id="d32af-166">If an application needs true parallel execution of commands against a server, multiple connections should be used.</span></span>  
  
 <span data-ttu-id="d32af-167">Например, рассмотрим следующую ситуацию.</span><span class="sxs-lookup"><span data-stu-id="d32af-167">For example, consider the following scenario.</span></span> <span data-ttu-id="d32af-168">Создаются два объекта команд, один для обработки результирующего набора, а другой для обновления данных. Они используют одно соединение с режимом MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-168">Two command objects are created, one for processing a result set and another for updating data; they share a common connection via MARS.</span></span> <span data-ttu-id="d32af-169">В этом сценарии `Transaction`.`Commit`</span><span class="sxs-lookup"><span data-stu-id="d32af-169">In this scenario, the `Transaction`.`Commit`</span></span> <span data-ttu-id="d32af-170">Сбой на обновление, пока не будут прочитаны все результаты для первого объекта команды, выдается следующее исключение:</span><span class="sxs-lookup"><span data-stu-id="d32af-170">fails on the update until all the results have been read on the first command object, yielding the following exception:</span></span>  
  
 <span data-ttu-id="d32af-171">Сообщение: контекст транзакции используется другим сеансом.</span><span class="sxs-lookup"><span data-stu-id="d32af-171">Message: Transaction context in use by another session.</span></span>  
  
 <span data-ttu-id="d32af-172">Источник: поставщик данных .NET SqlClient</span><span class="sxs-lookup"><span data-stu-id="d32af-172">Source: .Net SqlClient Data Provider</span></span>  
  
 <span data-ttu-id="d32af-173">Ожидается: (значение NULL).</span><span class="sxs-lookup"><span data-stu-id="d32af-173">Expected: (null)</span></span>  
  
 <span data-ttu-id="d32af-174">Получено: System.Data.SqlClient.SqlException</span><span class="sxs-lookup"><span data-stu-id="d32af-174">Received: System.Data.SqlClient.SqlException</span></span>  
  
 <span data-ttu-id="d32af-175">Есть три способа обработки этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="d32af-175">There are three options for handling this scenario:</span></span>  
  
1.  <span data-ttu-id="d32af-176">Запустить транзакцию после создания модуля чтения с тем, чтобы он не был частью транзакции.</span><span class="sxs-lookup"><span data-stu-id="d32af-176">Start the transaction after the reader is created, so that it is not part of the transaction.</span></span> <span data-ttu-id="d32af-177">После этого любое обновление будет становиться собственной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="d32af-177">Every update then becomes its own transaction.</span></span>  
  
2.  <span data-ttu-id="d32af-178">Зафиксировать всю работу после закрытия модуля чтения.</span><span class="sxs-lookup"><span data-stu-id="d32af-178">Commit all work after the reader is closed.</span></span> <span data-ttu-id="d32af-179">Это создает потенциал для последующего пакета обновлений.</span><span class="sxs-lookup"><span data-stu-id="d32af-179">This has the potential for a substantial batch of updates.</span></span>  
  
3.  <span data-ttu-id="d32af-180">Не использовать режим MARS, вместо этого использовать отдельное соединение для каждого объекта команды, что было стандартным решением до появления режима MARS.</span><span class="sxs-lookup"><span data-stu-id="d32af-180">Don't use MARS; instead use a separate connection for each command object as you would have before MARS.</span></span>  
  
### <a name="detecting-mars-support"></a><span data-ttu-id="d32af-181">Обнаружение поддержки режима MARS</span><span class="sxs-lookup"><span data-stu-id="d32af-181">Detecting MARS Support</span></span>  
 <span data-ttu-id="d32af-182">Приложение может проверить, поддерживается ли режим MARS, считав значение `SqlConnection.ServerVersion`.</span><span class="sxs-lookup"><span data-stu-id="d32af-182">An application can check for MARS support by reading the `SqlConnection.ServerVersion` value.</span></span> <span data-ttu-id="d32af-183">Основным номером должно быть 9 для SQL Server 2005 и 10 для SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d32af-183">The major number should be 9 for SQL Server 2005 and 10 for SQL Server 2008.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32af-184">См. также</span><span class="sxs-lookup"><span data-stu-id="d32af-184">See Also</span></span>  
 [<span data-ttu-id="d32af-185">Несколько активных результирующих наборов (MARS)</span><span class="sxs-lookup"><span data-stu-id="d32af-185">Multiple Active Result Sets (MARS)</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [<span data-ttu-id="d32af-186">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d32af-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
