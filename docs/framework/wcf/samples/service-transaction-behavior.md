---
title: Транзакционное поведение службы
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: db120df1b2efd28cc484c3749bb22fc2196e9dd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768258"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="78834-102">Транзакционное поведение службы</span><span class="sxs-lookup"><span data-stu-id="78834-102">Service Transaction Behavior</span></span>
<span data-ttu-id="78834-103">В этом образце показано использование координируемой клиентом транзакции и параметры ServiceBehaviorAttribute и OperationBehaviorAttribute, управляющие поведением транзакции службы.</span><span class="sxs-lookup"><span data-stu-id="78834-103">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="78834-104">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующем службу калькулятора, но ведется журнал выполненных операций в таблицу базы данных, а также нарастающий итог операций калькулятора.</span><span class="sxs-lookup"><span data-stu-id="78834-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="78834-105">Операции записи в таблицу журнала сервера зависят от результата координируемой клиентом транзакции - если транзакция клиента не была завершена, транзакция веб-службы подтверждает, что обновления базы данных не будут зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="78834-105">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78834-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="78834-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="78834-107">Контракт этой службы определяет, что для всех операций требуется поток транзакций с запросами:</span><span class="sxs-lookup"><span data-stu-id="78834-107">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",  
                    SessionMode = SessionMode.Required)]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Subtract(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Multiply(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Divide(double n);  
}  
```  
  
 <span data-ttu-id="78834-108">Чтобы включить поток входящих транзакций, для службы настраивается системная привязка wsHttpBinding, атрибут transactionFlow которой имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="78834-108">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="78834-109">Эта привязка использует поддерживающий взаимодействие протокол WSAtomicTransactionOctober2004:</span><span class="sxs-lookup"><span data-stu-id="78834-109">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="transactionalBinding" transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="78834-110">После инициации подключения к службе и транзакции клиент обращается к нескольким операциям службы в пределах области транзакции, а затем завершает транзакцию и закрывает подключение:</span><span class="sxs-lookup"><span data-stu-id="78834-110">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>  
  
```csharp
// Create a client  
CalculatorClient client = new CalculatorClient();  
  
// Create a transaction scope with the default isolation level of Serializable  
using (TransactionScope tx = new TransactionScope())  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation.  
    double value = 100.00D;  
    Console.WriteLine("  Adding {0}, running total={1}",  
                                        value, client.Add(value));  
  
    // Call the Subtract service operation.  
    value = 45.00D;  
    Console.WriteLine("  Subtracting {0}, running total={1}",  
                                        value, client.Subtract(value));  
  
    // Call the Multiply service operation.  
    value = 9.00D;  
    Console.WriteLine("  Multiplying by {0}, running total={1}",  
                                        value, client.Multiply(value));  
  
    // Call the Divide service operation.  
    value = 15.00D;  
    Console.WriteLine("  Dividing by {0}, running total={1}",  
                                        value, client.Divide(value));  
  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
  
// Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
 <span data-ttu-id="78834-111">На стороне службы имеется три атрибута, которые влияют на поведение транзакции службы. Это происходит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="78834-111">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>  
  
-   <span data-ttu-id="78834-112">В атрибуте `ServiceBehaviorAttribute`.</span><span class="sxs-lookup"><span data-stu-id="78834-112">On the `ServiceBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="78834-113">Свойство `TransactionTimeout` задает период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="78834-113">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="78834-114">В этом образце это время составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="78834-114">In this sample it is set to 30 seconds.</span></span>  
  
    -   <span data-ttu-id="78834-115">Свойство `TransactionIsolationLevel` указывает уровень изоляции транзакций, поддерживаемый службой.</span><span class="sxs-lookup"><span data-stu-id="78834-115">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="78834-116">Он должен совпадать с уровнем изоляции клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-116">This is required to match the client's isolation level.</span></span>  
  
    -   <span data-ttu-id="78834-117">Свойство `ReleaseServiceInstanceOnTransactionComplete` определяет, используется ли экземпляр службы повторно по завершении транзакции.</span><span class="sxs-lookup"><span data-stu-id="78834-117">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="78834-118">При установке для него значения `false` служба использует один и тот же экземпляр службы для разных запросов операций.</span><span class="sxs-lookup"><span data-stu-id="78834-118">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="78834-119">Это требуется для определения нарастающего итога.</span><span class="sxs-lookup"><span data-stu-id="78834-119">This is required to maintain the running total.</span></span> <span data-ttu-id="78834-120">Если свойство имеет значение `true`, после каждого завершенного действия создается новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="78834-120">If set to `true`, a new instance is generated after each completed action.</span></span>  
  
    -   <span data-ttu-id="78834-121">Свойство `TransactionAutoCompleteOnSessionClose` определяет, завершаются ли ожидающие обработки транзакции при завершении сеанса.</span><span class="sxs-lookup"><span data-stu-id="78834-121">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="78834-122">При установке для него `false`, отдельные операции должны установить <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> свойства `true` или явным образом требовать вызова <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> метод для выполнения транзакций.</span><span class="sxs-lookup"><span data-stu-id="78834-122">By setting it to `false`, the individual operations are required to either set the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> property to `true` or to explicitly require a call to the <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> method to complete transactions.</span></span> <span data-ttu-id="78834-123">В этом образце продемонстрированы оба подхода.</span><span class="sxs-lookup"><span data-stu-id="78834-123">This sample demonstrates both approaches.</span></span>  
  
-   <span data-ttu-id="78834-124">В атрибуте `ServiceContractAttribute`.</span><span class="sxs-lookup"><span data-stu-id="78834-124">On the `ServiceContractAttribute`:</span></span>  
  
    -   <span data-ttu-id="78834-125">Свойство `SessionMode` определяет, согласовывает ли служба соответствующие запросы в логический сеанс.</span><span class="sxs-lookup"><span data-stu-id="78834-125">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="78834-126">Поскольку служба включает операции, для которых свойство OperationBehaviorAttribute TransactionAutoComplete имеет значение `false` (Multiply и Divide), необходимо задавать `SessionMode.Required`.</span><span class="sxs-lookup"><span data-stu-id="78834-126">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="78834-127">Например, операция Multiply не завершает свою транзакцию и вместо этого ожидает очередного вызова операции Divide, чтобы завершить транзакцию с помощью метода `SetTransactionComplete`; служба должна уметь определять, что операции выполняются в рамках одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="78834-127">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>  
  
-   <span data-ttu-id="78834-128">В атрибуте `OperationBehaviorAttribute`.</span><span class="sxs-lookup"><span data-stu-id="78834-128">On the `OperationBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="78834-129">Свойство `TransactionScopeRequired` определяет, должны ли действия операции выполняться в области транзакции.</span><span class="sxs-lookup"><span data-stu-id="78834-129">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="78834-130">Оно устанавливается равным `true` для всех операций в этом образце, и, поскольку клиент направляет свои транзакции всем операциям, действия выполняются в области соответствующей транзакции клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-130">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>  
  
    -   <span data-ttu-id="78834-131">Свойство `TransactionAutoComplete` указывает, следует ли автоматически завершать транзакцию, в которой выполняется метод, при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="78834-131">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="78834-132">Как говорилось выше, это свойство устанавливается равным `true` для операций Add и Subtract и `false` для операций Multiply и Divide.</span><span class="sxs-lookup"><span data-stu-id="78834-132">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="78834-133">Операции Add и Subtract завершают свои действия автоматически, операция Divide завершает свои действия через явный вызов метода `SetTransactionComplete`, а операция Multiply не завершает свои действия, а ожидает очередного вызова, например операции Divide, чтобы завершить свои действия.</span><span class="sxs-lookup"><span data-stu-id="78834-133">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>  
  
 <span data-ttu-id="78834-134">Реализация службы с атрибутами выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="78834-134">The attributed service implementation is as follows:</span></span>  
  
```csharp
[ServiceBehavior(  
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
    TransactionTimeout = "00:00:30",  
    ReleaseServiceInstanceOnTransactionComplete = false,  
    TransactionAutoCompleteOnSessionClose = false)]  
public class CalculatorService : ICalculator  
{  
    double runningTotal;  
  
    public CalculatorService()  
    {  
        Console.WriteLine("Creating new service instance...");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Add(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));  
        runningTotal = runningTotal + n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Subtract(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));  
        runningTotal = runningTotal - n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Multiply(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal * n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Divide(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal / n;  
        OperationContext.Current.SetTransactionComplete();  
        return runningTotal;  
    }  
  
    // Logging method ommitted for brevity  
}   
```  
  
 <span data-ttu-id="78834-135">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-135">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="78834-136">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-136">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Starting transaction  
Performing calculations...  
  Adding 100, running total=100  
  Subtracting 45, running total=55  
  Multiplying by 9, running total=495  
  Dividing by 15, running total=33  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="78834-137">Журнал запросов операций службы отображается в окне консоли службы.</span><span class="sxs-lookup"><span data-stu-id="78834-137">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="78834-138">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-138">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Press <ENTER> to terminate service.  
Creating new service instance...  
  Writing row 1 to database: Adding 100 to 0  
  Writing row 2 to database: Subtracting 45 from 100  
  Writing row 3 to database: Multiplying 55 by 9  
  Writing row 4 to database: Dividing 495 by 15  
```  
  
 <span data-ttu-id="78834-139">Обратите внимание, что помимо сохранения нарастающего итога всех вычислений, служба также сообщает о создании экземпляров (в данном образце один экземпляр) и записывает запросы операций в базу данных.</span><span class="sxs-lookup"><span data-stu-id="78834-139">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="78834-140">Поскольку все запросы выполняются в транзакции клиента, в случае невозможности завершить транзакцию происходит откат всех операций базы данных.</span><span class="sxs-lookup"><span data-stu-id="78834-140">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="78834-141">Это можно показать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="78834-141">This can be demonstrated in a number of ways:</span></span>  
  
-   <span data-ttu-id="78834-142">Скройте комментарием клиентский вызов метода `tx.Complete`() и выполните пример заново - клиент выйдет из области транзакции без завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="78834-142">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>  
  
-   <span data-ttu-id="78834-143">Скройте комментарием вызов операции Divide службы - действие, вызванное операцией Multiply, не будет завершено, в результате чего не удастся завершить и транзакцию клиента.</span><span class="sxs-lookup"><span data-stu-id="78834-143">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>  
  
-   <span data-ttu-id="78834-144">Создайте необработанное исключение в любом месте области транзакции клиента - в этом случае клиенту также не удастся завершить транзакцию.</span><span class="sxs-lookup"><span data-stu-id="78834-144">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>  
  
 <span data-ttu-id="78834-145">В результате реализации любого из этих сценариев ни одна из выполняемых в пределах области операций не будет зафиксирована, и чисто сохраняемых в базе данных строк не увеличится.</span><span class="sxs-lookup"><span data-stu-id="78834-145">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78834-146">В процессе построения файл базы данных копируется в папку bin.</span><span class="sxs-lookup"><span data-stu-id="78834-146">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="78834-147">Чтобы следить за тем, какие строки сохраняются в журнале, необходимо проверять эту копию файла базы данных, а не файл, входящий в проект Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="78834-147">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="78834-148">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="78834-148">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="78834-149">Убедитесь, что установлен SQL Server 2005 Express Edition или SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="78834-149">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="78834-150">В файле службы App.config может быть задано значение `connectionString` базы данных либо взаимодействие с базой данных может быть отключено (значение appSettings `usingSql` равно `false`).</span><span class="sxs-lookup"><span data-stu-id="78834-150">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>  
  
2. <span data-ttu-id="78834-151">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="78834-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="78834-152">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="78834-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="78834-153">Если запустить образец на компьютерах, необходимо настроить Майкрософт распределенных транзакций координатора) (MSDTC) включив поток сетевых транзакций, и используйте средство WsatConfig.exe Включение сети транзакций Windows Communication Foundation (WCF) Поддержка.</span><span class="sxs-lookup"><span data-stu-id="78834-153">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="78834-154">Настройка координатора распределенных транзакций (Майкрософт) на поддержку выполнения образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="78834-154">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>  
  
1. <span data-ttu-id="78834-155">На компьютере службы настройте координатор MSDTC на разрешение входящих сетевых транзакций.</span><span class="sxs-lookup"><span data-stu-id="78834-155">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>  
  
    1.  <span data-ttu-id="78834-156">Из **запустить** меню перейдите к **панели управления**, затем **Администрирование**, а затем **службы компонентов**.</span><span class="sxs-lookup"><span data-stu-id="78834-156">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="78834-157">Щелкните правой кнопкой мыши **Мой компьютер** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="78834-157">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="78834-158">На **MSDTC** щелкните **конфигурация безопасности**.</span><span class="sxs-lookup"><span data-stu-id="78834-158">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="78834-159">Проверьте **сетевой доступ DTC** и **Разрешить входящий**.</span><span class="sxs-lookup"><span data-stu-id="78834-159">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5.  <span data-ttu-id="78834-160">Нажмите кнопку **Да** перезапустите службы MS DTC, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78834-160">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="78834-161">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="78834-161">Click **OK** to close the dialog box.</span></span>  
  
2. <span data-ttu-id="78834-162">На компьютере службы и на клиентском компьютере настройте брандмауэр Windows, чтобы включить координатор распределенных транзакций (Майкрософт) в список исключений.</span><span class="sxs-lookup"><span data-stu-id="78834-162">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>  
  
    1.  <span data-ttu-id="78834-163">С панели управления запустите брандмауэр Windows.</span><span class="sxs-lookup"><span data-stu-id="78834-163">Run the Windows Firewall application from Control Panel.</span></span>  
  
    2.  <span data-ttu-id="78834-164">Из **исключения** щелкните **добавить программу**.</span><span class="sxs-lookup"><span data-stu-id="78834-164">From the **Exceptions** tab, click **Add Program**.</span></span>  
  
    3.  <span data-ttu-id="78834-165">Перейдите в папку C:\WINDOWS\System32.</span><span class="sxs-lookup"><span data-stu-id="78834-165">Browse to the folder C:\WINDOWS\System32.</span></span>  
  
    4.  <span data-ttu-id="78834-166">Выберите Msdtc.exe и нажмите кнопку **откройте**.</span><span class="sxs-lookup"><span data-stu-id="78834-166">Select Msdtc.exe and click **Open**.</span></span>  
  
    5.  <span data-ttu-id="78834-167">Нажмите кнопку **ОК** закрыть **добавить программу** диалоговое окно и нажмите кнопку **ОК** еще раз, чтобы закрыть приложение брандмауэра Windows.</span><span class="sxs-lookup"><span data-stu-id="78834-167">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>  
  
3. <span data-ttu-id="78834-168">На клиентском компьютере настройте координатор распределенных транзакций, чтобы он разрешал исходящие сетевые транзакции.</span><span class="sxs-lookup"><span data-stu-id="78834-168">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1.  <span data-ttu-id="78834-169">Из **запустить** меню перейдите к **панели управления**, затем **Администрирование**, а затем **службы компонентов**.</span><span class="sxs-lookup"><span data-stu-id="78834-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="78834-170">Щелкните правой кнопкой мыши **Мой компьютер** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="78834-170">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="78834-171">На **MSDTC** щелкните **конфигурация безопасности**.</span><span class="sxs-lookup"><span data-stu-id="78834-171">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="78834-172">Проверьте **сетевой доступ DTC** и **Разрешить исходящий трафик**.</span><span class="sxs-lookup"><span data-stu-id="78834-172">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5.  <span data-ttu-id="78834-173">Нажмите кнопку **Да** перезапустите службы MS DTC, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="78834-173">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="78834-174">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="78834-174">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="78834-175">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="78834-175">The samples may already be installed on your machine.</span></span> <span data-ttu-id="78834-176">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="78834-176">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="78834-177">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="78834-177">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="78834-178">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="78834-178">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`  
