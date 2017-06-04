---
title: "Транзакционное поведение службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "образец транзакционного поведения службы [Windows Communication Foundation]"
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Транзакционное поведение службы
В этом образце показано использование координируемой клиентом транзакции и параметры ServiceBehaviorAttribute и OperationBehaviorAttribute, управляющие поведением транзакции службы.Этот образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует службу калькулятора, однако в нем на сервере в таблице базы данных ведется журнал выполненных операций, а также нарастающий итог операций калькулятора.Операции записи в таблицу журнала сервера зависят от результата координируемой клиентом транзакции — если транзакция клиента не была завершена, транзакция веб\-службы подтверждает, что обновления базы данных не будут зафиксированы.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Контракт этой службы определяет, что для всех операций требуется поток транзакций с запросами:  
  
```  
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
  
 Чтобы включить поток входящих транзакций, для службы настраивается системная привязка wsHttpBinding, атрибут transactionFlow которой имеет значение `true`.Эта привязка использует поддерживающий взаимодействие протокол WSAtomicTransactionOctober2004:  
  
```  
<bindings>  
  <wsHttpBinding>  
    <binding name="transactionalBinding" transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
  
```  
  
 После инициации подключения к службе и транзакции клиент обращается к нескольким операциям службы в пределах области транзакции, а затем завершает транзакцию и закрывает подключение:  
  
```  
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
  
 На стороне службы имеется три атрибута, которые влияют на поведение транзакции службы. Это происходит следующим образом.  
  
-   В атрибуте `ServiceBehaviorAttribute`.  
  
    -   Свойство `TransactionTimeout` задает период времени, в течение которого транзакция должна быть завершена.В этом образце это время составляет 30 секунд.  
  
    -   Свойство `TransactionIsolationLevel` указывает уровень изоляции транзакций, поддерживаемый службой.Он должен совпадать с уровнем изоляции клиента.  
  
    -   Свойство `ReleaseServiceInstanceOnTransactionComplete` определяет, используется ли экземпляр службы повторно по завершении транзакции.При установке для него значения `false` служба использует один и тот же экземпляр службы для разных запросов операций.Это требуется для определения нарастающего итога.Если свойство имеет значение `true`, после каждого завершенного действия создается новый экземпляр.  
  
    -   Свойство `TransactionAutoCompleteOnSessionClose` определяет, завершаются ли ожидающие обработки транзакции при завершении сеанса.При установке для него значения `false` отдельные операции должны установить для свойства `OperationBehaviorAttribute``TransactionAutoComplete` значение `true` или явным образом требовать вызова метода `SetTransactionComplete` для завершения транзакций.В этом образце продемонстрированы оба подхода.  
  
-   В атрибуте `ServiceContractAttribute`.  
  
    -   Свойство `SessionMode` определяет, согласовывает ли служба соответствующие запросы в логический сеанс.Поскольку служба включает операции, для которых свойство OperationBehaviorAttribute TransactionAutoComplete имеет значение `false` \(Multiply и Divide\), необходимо задавать `SessionMode.Required`.Например, операция Multiply не завершает свою транзакцию и вместо этого ожидает очередного вызова операции Divide, чтобы завершить транзакцию с помощью метода `SetTransactionComplete`; служба должна уметь определять, что операции выполняются в рамках одного сеанса.  
  
-   В атрибуте `OperationBehaviorAttribute`.  
  
    -   Свойство `TransactionScopeRequired` определяет, должны ли действия операции выполняться в области транзакции.Оно устанавливается равным `true` для всех операций в этом образце, и, поскольку клиент направляет свои транзакции всем операциям, действия выполняются в области соответствующей транзакции клиента.  
  
    -   Свойство `TransactionAutoComplete` указывает, следует ли автоматически завершать транзакцию, в которой выполняется метод, при отсутствии необработанных исключений.Как говорилось выше, это свойство устанавливается равным `true` для операций Add и Subtract и `false` для операций Multiply и Divide.Операции Add и Subtract завершают свои действия автоматически, операция Divide завершает свои действия через явный вызов метода `SetTransactionComplete`, а операция Multiply не завершает свои действия, а ожидает очередного вызова, например операции Divide, чтобы завершить свои действия.  
  
 Реализация службы с атрибутами выглядит следующим образом.  
  
```  
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
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
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
  
 Журнал запросов операций службы отображается в окне консоли службы.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Press <ENTER> to terminate service.  
Creating new service instance...  
  Writing row 1 to database: Adding 100 to 0  
  Writing row 2 to database: Subtracting 45 from 100  
  Writing row 3 to database: Multiplying 55 by 9  
  Writing row 4 to database: Dividing 495 by 15  
```  
  
 Обратите внимание, что помимо сохранения нарастающего итога всех вычислений, служба также сообщает о создании экземпляров \(в данном образце один экземпляр\) и записывает запросы операций в базу данных.Поскольку все запросы выполняются в транзакции клиента, в случае невозможности завершить транзакцию происходит откат всех операций базы данных.Это можно показать несколькими способами.  
  
-   Скройте комментарием клиентский вызов метода `tx.Complete`\(\) и выполните пример заново — клиент выйдет из области транзакции без завершения транзакции.  
  
-   Скройте комментарием вызов операции Divide службы — действие, вызванное операцией Multiply, не будет завершено, в результате чего не удастся завершить и транзакцию клиента.  
  
-   Создайте необработанное исключение в любом месте области транзакции клиента — в этом случае клиенту также не удастся завершить транзакцию.  
  
 В результате реализации любого из этих сценариев ни одна из выполняемых в пределах области операций не будет зафиксирована, и чисто сохраняемых в базе данных строк не увеличится.  
  
> [!NOTE]
>  В процессе построения файл базы данных копируется в папку bin.Чтобы следить за тем, какие строки сохраняются в журнале, необходимо проверять эту копию файла базы данных, а не файл, входящий в проект Visual Studio.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что установлен SQL Server 2005 Express Edition или SQL Server 2005.В файле службы App.config может быть задано значение `connectionString` базы данных либо взаимодействие с базой данных может быть отключено \(значение appSettings `usingSql` равно `false`\).  
  
2.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
 Если образец выполняется на нескольких компьютерах, необходимо настроить координатор распределенных транзакций \(Майкрософт\), включив поток сетевых транзакций, и с помощью средства WsatConfig.exe включить сетевую поддержку транзакций [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
### Настройка координатора распределенных транзакций \(Майкрософт\) на поддержку выполнения образца на нескольких компьютерах  
  
1.  На компьютере службы настройте координатор MSDTC на разрешение входящих сетевых транзакций.  
  
    1.  В меню **Пуск** выберите **Панель управления**, **Администрирование**, **Службы компонентов**.  
  
    2.  Щелкните правой кнопкой мыши **Мой компьютер** и выберите **Свойства**.  
  
    3.  На вкладке **MSDTC** щелкните **Настройка безопасности**.  
  
    4.  Установите флажки **Доступ к сети DTC** и **Разрешить входящие**.  
  
    5.  Нажмите кнопку **Да**, чтобы перезапустить службу MSDTC, после чего нажмите кнопку **ОК**.  
  
    6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
2.  На компьютере службы и на клиентском компьютере настройте брандмауэр Windows, чтобы включить координатор распределенных транзакций \(Майкрософт\) в список исключений.  
  
    1.  С панели управления запустите брандмауэр Windows.  
  
    2.  На вкладке **Исключения** нажмите кнопку **Добавить программу**.  
  
    3.  Перейдите в папку C:\\WINDOWS\\System32.  
  
    4.  Выберите файл Msdtc.exe и нажмите кнопку **Открыть**.  
  
    5.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Добавление программы** и снова нажмите кнопку **ОК**, чтобы закрыть приложение "Брандмауэр Windows".  
  
3.  На клиентском компьютере настройте координатор распределенных транзакций, чтобы он разрешал исходящие сетевые транзакции.  
  
    1.  В меню **Пуск** выберите **Панель управления**, **Администрирование**, **Службы компонентов**.  
  
    2.  Щелкните правой кнопкой мыши **Мой компьютер** и выберите **Свойства**.  
  
    3.  На вкладке **MSDTC** щелкните **Настройка безопасности**.  
  
    4.  Установите флажки **Доступ к сети DTC** и **Разрешить исходящие**.  
  
    5.  Нажмите кнопку **Да**, чтобы перезапустить службу MSDTC, после чего нажмите кнопку **ОК**.  
  
    6.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`  
  
## См. также