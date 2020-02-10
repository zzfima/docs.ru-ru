---
title: Поток транзакций WS
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 781934e9ab27f761e71841c2edc509f9b8022aa7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094752"
---
# <a name="ws-transaction-flow"></a>Поток транзакций WS
В этом образце показано использование координируемой клиентом транзакции и параметры клиента и сервера для организации потока транзакции с использованием протокола WS-Atomic Transaction или OleTransactions. Этот пример основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) , который реализует службу калькулятора, но операции являются атрибутами, чтобы продемонстрировать использование `TransactionFlowAttribute` с перечислением **TransactionFlowOption** , чтобы определить степень включения потока транзакций. В области поточной транзакции в базу данных записывается журнал запрошенных операций, который сохраняется до завершения транзакции, координируемой клиентом, и если транзакция клиента не завершена, транзакция веб-службы следит, чтобы соответствующие обновления базы данных не были зафиксированы.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 После установления связи со службой и транзакцией клиент обращается к нескольким операциям службы. Контракт службы определяется показанным ниже образом, при этом все операции показывают различные параметры `TransactionFlowOption`.  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);   
}  
```

 Определяет операции в порядке их выполнения:  
  
- запрос операции `Add` должен включать поточную транзакцию;  
  
- запрос операции `Subtract` может включать поточную транзакцию;  
  
- запрос операции `Multiply` не может содержать поточную транзакцию из-за явно установленного параметра NotAllowed;  
  
- запрос операции `Divide` не может содержать поточную транзакцию из-за отсутствия атрибута `TransactionFlow`.  
  
 Чтобы включить поток транзакций, в дополнение к соответствующим атрибутам операции необходимо использовать привязки с включенным свойством [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) . В этом образце конфигурация службы предоставляет в дополнение к конечной точке обмена метаданными конечные точки TCP и HTTP. Конечная точка TCP и конечная точка HTTP используют следующие привязки, для которых включено свойство [\<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) .  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
> Предоставляемая системой привязка netTcpBinding позволяет задавать протокол transactionProtocol, а предоставляемая системой привязка wsHttpBinding использует только протокол WSAtomicTransactionOctober2004 с большими возможностями взаимодействия. Протокол OleTransactions доступен только для клиентов Windows Communication Foundation (WCF).  
  
 Для класса, реализующего интерфейс `ICalculator`, всем методам в качестве атрибута задано свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>, имеющее значение `true`. Этот параметр означает, что все действия, предпринятые в рамках метода, происходят в области транзакции. В этом случае предпринятые действия включают запись в журнал базы данных. Если запрос операции включает поточную транзакцию, действия происходят в области входящей транзакции или автоматически создается новая область транзакции.  
  
> [!NOTE]
> Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> определяет локальное поведение реализаций методов службы и не определяет возможность или требования клиента передавать транзакцию.  

```csharp
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```

 На стороне клиента параметры операций `TransactionFlowOption` службы отражаются в создаваемом определении интерфейса `ICalculator` клиента. Параметры свойства `transactionFlow` службы также отражаются в конфигурации приложения клиента. Клиент может выбрать транспорт и протокол, выбрав соответствующее имя `endpointConfigurationName`.  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> Поведение этого образца не зависит от выбранного протокола или транспорта.  
  
 После установления связи со службой клиент создает новую область `TransactionScope`, в которую заключены вызовы операций службы.  

```csharp
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```

 Используются следующие вызовы операций.  
  
- Запрос `Add` передает нужную транзакцию службе, а действия службы происходят в области транзакции клиента.  
  
- Первый запрос `Subtract` также передает разрешенную транзакцию службе, действия службы снова происходят в области транзакции клиента.  
  
- Второй запрос `Subtract` выполняется в новой области транзакции, объявленной с помощью параметра `TransactionScopeOption.Suppress`. Он подавляет первоначальную внешнюю транзакцию клиента, и запрос не передает транзакцию службе. Этот подход позволяет клиенту явно отказаться и защититься от передачи транзакции службе, если в этом нет необходимости. Действия службы происходят в области новой, несвязанной транзакции.  
  
- Запрос `Multiply` не передает транзакцию службе, так как созданное клиентом определение интерфейса `ICalculator` включает объект <xref:System.ServiceModel.TransactionFlowAttribute>, которому присвоено значение <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.  
  
- Запрос `Divide` не передает транзакцию службе, так как, опять же, созданное клиентом определение интерфейса `ICalculator` не включает `TransactionFlowAttribute`. Действия службы снова происходят в области новой, несвязанной транзакции.  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 Журнал запросов операций службы отображается в окне консоли службы. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 После успешного выполнения область транзакции клиента завершается, а все действия, предпринятые в этой области, фиксируются. В частности, в базе данных службы сохраняются 5 указанных записей. Первые две произошли в области транзакции клиента.  
  
 Если в любом месте области `TransactionScope` клиента возникло исключение, транзакция не может завершиться. Из-за этого записи, помещенные в журнал в этой области, не фиксируются в базе данных. Чтобы посмотреть на эту ситуацию, повторите выполнение образца, преобразовав в комментарий вызов для завершения внешней области `TransactionScope`. При таком выполнении записываются только 3 последних действия (из второго запроса `Subtract` и запросов `Multiply` и `Divide`), потому что к ним не передавалась транзакция клиента.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Чтобы создать C# или Visual Basic версию решения .NET, следуйте инструкциям в разделе [Создание Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/building-the-samples.md) .  
  
2. Убедитесь, что установлен SQL Server Express Edition, SQL Server, а в файле конфигурации приложения службы правильно задана строка подключения. Чтобы выполнить образец без использования базы данных, установите значение `usingSql` в файле конфигурации приложения службы равным `false`  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Если планируется выполнять образец на нескольких компьютерах, включите координатор распределенных транзакций согласно приведенным ниже инструкциям и воспользуйтесь средством WsatConfig.exe из пакета Windows SDK для поддержки сетевых транзакций WCF. Сведения о настройке WsatConfig. exe см. в разделе [Настройка поддержки транзакций WS-Atomic](../feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Независимо от того, запускается ли пример на том же компьютере или на разных компьютерах, необходимо настроить Microsoft координатор распределенных транзакций (MSDTC) для включения потока сетевых транзакций и использовать средство WsatConfig. exe для включения поддержки сети транзакций WCF.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>Настройка координатора распределенных транзакций (Майкрософта) (MSDTC) на поддержку выполнения образца  
  
1. На компьютере службы, работающем под управлением Windows Server 2003 или Windows XP настройте MSDTC, разрешите входящие сетевые транзакции, согласно следующим инструкциям.  
  
    1. В меню **Пуск** последовательно выберите пункты **Панель управления**, **Администрирование**и **службы компонентов**.  
  
    2. Разверните узел **службы компонентов**. Откройте папку " **Компьютеры** ".  
  
    3. Щелкните правой кнопкой мыши **Мой компьютер** и выберите пункт **свойства**.  
  
    4. На вкладке **MSDTC** щелкните **Конфигурация безопасности**.  
  
    5. Проверьте **доступ DTC к сети** и **разрешите входящий трафик**.  
  
    6. Нажмите кнопку **ОК**, а затем нажмите кнопку **Да** , чтобы перезапустить службу MSDTC.  
  
    7. Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .  
  
2. На компьютере службы, работающем под управлением Windows Server 2008 или Windows Vista настройте MSDTC, разрешив входящие сетевые транзакции, согласно следующим инструкциям.  
  
    1. В меню **Пуск** последовательно выберите пункты **Панель управления**, **Администрирование**и **службы компонентов**.  
  
    2. Разверните узел **службы компонентов**. Откройте папку " **Компьютеры** ". Выберите **координатор распределенных транзакций**.  
  
    3. Щелкните правой кнопкой мыши **координатор DTC** и выберите пункт **свойства**.  
  
    4. На вкладке **Безопасность** проверьте **доступ к сети DTC** и **разрешите входящие**.  
  
    5. Нажмите кнопку **ОК**, а затем нажмите кнопку **Да** , чтобы перезапустить службу MSDTC.  
  
    6. Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .  
  
3. На клиентском компьютере настройте координатор распределенных транзакций, чтобы он разрешал исходящие сетевые транзакции.  
  
    1. В меню **Пуск** последовательно выберите пункты `Control Panel`, **Администрирование**и **службы компонентов**.  
  
    2. Щелкните правой кнопкой мыши **Мой компьютер** и выберите пункт **свойства**.  
  
    3. На вкладке **MSDTC** щелкните **Конфигурация безопасности**.  
  
    4. Проверьте **доступ к сети DTC** и **разрешите исходящие**подключения.  
  
    5. Нажмите кнопку **ОК**, а затем нажмите кнопку **Да** , чтобы перезапустить службу MSDTC.  
  
    6. Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
