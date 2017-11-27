---
title: "Поток транзакций WS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
caps.latest.revision: "43"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7043956427561e4485bdad6a98673b997bc88e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ws-transaction-flow"></a>Поток транзакций WS
В этом образце показано использование координируемой клиентом транзакции и параметры клиента и сервера для организации потока транзакции с использованием протокола WS-Atomic Transaction или OleTransactions. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора, но операции достигается за счет демонстрируют использование `TransactionFlowAttribute` с **параметр transactionflowoption со** Перечисление, чтобы определить, в какой степени транзакций включен поток. В области поточной транзакции в базу данных записывается журнал запрошенных операций, который сохраняется до завершения транзакции, координируемой клиентом, и если транзакция клиента не завершена, транзакция веб-службы следит, чтобы соответствующие обновления базы данных не были зафиксированы.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 После установления связи со службой и транзакцией клиент обращается к нескольким операциям службы. Контракт службы определяется показанным ниже образом, при этом все операции показывают различные параметры `TransactionFlowOption`.  
  
```  
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
  
-   запрос операции `Add` должен включать поточную транзакцию;  
  
-   запрос операции `Subtract` может включать поточную транзакцию;  
  
-   запрос операции `Multiply` не может содержать поточную транзакцию из-за явно установленного параметра NotAllowed;  
  
-   запрос операции `Divide` не может содержать поточную транзакцию из-за отсутствия атрибута `TransactionFlow`.  
  
 Для включения потока транзакций, привязки с [ \<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) включено свойство должно использоваться в дополнение к атрибутам соответствующую операцию. В этом образце конфигурация службы предоставляет в дополнение к конечной точке обмена метаданными конечные точки TCP и HTTP. Конечная точка TCP и конечной точки HTTP используйте следующие привязки, которые имеют [ \<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) включено свойство.  
  
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
>  Предоставляемая системой привязка netTcpBinding позволяет задавать протокол transactionProtocol, а предоставляемая системой привязка wsHttpBinding использует только протокол WSAtomicTransactionOctober2004 с большими возможностями взаимодействия. Протокол OleTransactions могут использовать только клиенты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 Для класса, реализующего интерфейс `ICalculator`, всем методам в качестве атрибута задано свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>, имеющее значение `true`. Этот параметр означает, что все действия, предпринятые в рамках метода, происходят в области транзакции. В этом случае предпринятые действия включают запись в журнал базы данных. Если запрос операции включает поточную транзакцию, действия происходят в области входящей транзакции или автоматически создается новая область транзакции.  
  
> [!NOTE]
>  Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> определяет локальное поведение реализаций методов службы и не определяет возможность или требования клиента передавать транзакцию.  
  
```  
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
  
```  
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```  
  
> [!NOTE]
>  Поведение этого образца не зависит от выбранного протокола или транспорта.  
  
 После установления связи со службой клиент создает новую область `TransactionScope`, в которую заключены вызовы операций службы.  
  
```  
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
  
-   Запрос `Add` передает нужную транзакцию службе, а действия службы происходят в области транзакции клиента.  
  
-   Первый запрос `Subtract` также передает разрешенную транзакцию службе, действия службы снова происходят в области транзакции клиента.  
  
-   Второй запрос `Subtract` выполняется в новой области транзакции, объявленной с помощью параметра `TransactionScopeOption.Suppress`. Он подавляет первоначальную внешнюю транзакцию клиента, и запрос не передает транзакцию службе. Этот подход позволяет клиенту явно отказаться и защититься от передачи транзакции службе, если в этом нет необходимости. Действия службы происходят в области новой, несвязанной транзакции.  
  
-   Запрос `Multiply` не передает транзакцию службе, так как созданное клиентом определение интерфейса `ICalculator` включает объект <xref:System.ServiceModel.TransactionFlowAttribute>, которому присвоено значение <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.  
  
-   Запрос `Divide` не передает транзакцию службе, так как созданное клиентом определение интерфейса `ICalculator` не включает `TransactionFlowAttribute`. Действия службы снова происходят в области новой, несвязанной транзакции.  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
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
  
```  
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
  
1.  Для сборки версии C# .NET или Visual Basic этого решения следуйте инструкциям в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2.  Убедитесь, что установлен SQL Server Express Edition, SQL Server, а в файле конфигурации приложения службы правильно задана строка подключения. Чтобы выполнить образец без использования базы данных, установите значение `usingSql` в файле конфигурации приложения службы равным `false`  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Если планируется выполнять образец на нескольких компьютерах, включите координатор распределенных транзакций согласно приведенным ниже инструкциям и воспользуйтесь средством WsatConfig.exe из пакета Windows SDK для поддержки сетевых транзакций WCF. В разделе [Настройка поддержки транзакций WS-AT](http://go.microsoft.com/fwlink/?LinkId=190370) сведения о настройке WsatConfig.exe.  
  
 В зависимости от того, запускается ли образец на одном или нескольких компьютерах, необходимо настроить координатор распределенных транзакций (Майкрософт) (MSDTC), включив поток сетевых транзакций, и с помощью средства WsatConfig.exe включить сетевую поддержку транзакций [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>Настройка координатора распределенных транзакций (Майкрософта) (MSDTC) на поддержку выполнения образца  
  
1.  На компьютере службы, работающем под управлением Windows Server 2003 или Windows XP настройте MSDTC, разрешите входящие сетевые транзакции, согласно следующим инструкциям.  
  
    1.  Из **запустить** меню, перейдите к **панели управления**, затем **Администрирование**, а затем **служб компонентов**.  
  
    2.  Разверните **служб компонентов**. Откройте **компьютеров** папки.  
  
    3.  Щелкните правой кнопкой мыши **Мой компьютер** и выберите **свойства**.  
  
    4.  На **MSDTC** щелкните **конфигурация безопасности**.  
  
    5.  Проверьте **сетевой доступ DTC** и **Разрешить входящие**.  
  
    6.  Нажмите кнопку **ОК**, нажмите кнопку **Да** перезапустить службу MSDTC.  
  
    7.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
2.  На компьютере службы, работающем под управлением Windows Server 2008 или Windows Vista настройте MSDTC, разрешив входящие сетевые транзакции, согласно следующим инструкциям.  
  
    1.  Из **запустить** меню, перейдите к **панели управления**, затем **Администрирование**, а затем **служб компонентов**.  
  
    2.  Разверните **служб компонентов**. Откройте **компьютеров** папки. Выберите **координатор распределенных транзакций**.  
  
    3.  Щелкните правой кнопкой мыши **координатор** и выберите **свойства**.  
  
    4.  На **безопасности** установите флажок **сетевой доступ DTC** и **Разрешить входящие**.  
  
    5.  Нажмите кнопку **ОК**, нажмите кнопку **Да** перезапустить службу MSDTC.  
  
    6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
3.  На клиентском компьютере настройте координатор распределенных транзакций, чтобы он разрешал исходящие сетевые транзакции.  
  
    1.  Из **запустить** меню, перейдите к `Control Panel`, затем **Администрирование**, а затем **служб компонентов**.  
  
    2.  Щелкните правой кнопкой мыши **Мой компьютер** и выберите **свойства**.  
  
    3.  На **MSDTC** щелкните **конфигурация безопасности**.  
  
    4.  Проверьте **сетевой доступ DTC** и **Разрешить исходящие**.  
  
    5.  Нажмите кнопку **ОК**, нажмите кнопку **Да** перезапустить службу MSDTC.  
  
    6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
