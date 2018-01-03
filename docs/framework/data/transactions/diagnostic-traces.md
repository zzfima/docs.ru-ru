---
title: "Диагностическая трассировка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cb16bb2d492caca7957e6d58eadddf9bf1568b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="diagnostic-traces"></a>Диагностическая трассировка
Трассировка — это процесс публикации определенных сообщений, создаваемых во время выполнения. При использовании трассировки требуется механизм для сбора и записи передаваемых сообщений. Получателями сообщений трассировки являются прослушиватели. В задачу прослушивателя входит сбор, хранение и маршрутизация сообщений трассировки. Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту, например, в журнал событий, окно или текстовый файл.  
  
 Один из таких прослушивателей, <xref:System.Diagnostics.DefaultTraceListener>, автоматически создается и инициализируется при включении трассировки. Для передачи выходных данных трассировки каким-либо дополнительным источникам необходимо создать и инициализировать дополнительные прослушиватели трассировки. Создаваемые прослушиватели должны соответствовать индивидуальным требованиям пользователя. Например, может потребоваться текстовая запись всех выходных данных трассировки. В этом случае можно создать прослушиватель, который при включении будет записывать все выходные данные в новый текстовый файл. С другой стороны, возможно, потребуется только просмотр выходных данных во время выполнения приложения. В этом случае следует создать прослушиватель, который будет направлять все выходные данные в окно консоли. Прослушиватель <xref:System.Diagnostics.EventLogTraceListener> может направлять выходные данные трассировки в журнал событий, а прослушиватель <xref:System.Diagnostics.TextWriterTraceListener> может записывать их в поток.  
  
## <a name="enabling-tracing"></a>Включение трассировки  
 Чтобы включить трассировку во время обработки транзакции, необходимо отредактировать файл конфигурации приложения. Пример.  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 Трассировки <xref:System.Transactions> записываются в источник с именем «System.Transactions». С помощью `add` можно задать имя и тип прослушивателя трассировки, который требуется использовать. В данном примере создается прослушиватель с именем "tx" и добавляется стандартный прослушиватель трассировки .NET Framework (<xref:System.Diagnostics.XmlWriterTraceListener>) в качестве типа, который требуется использовать. Чтобы задать имя файла журнала для этого прослушивателя, используйте `initializeData`. Кроме того, можно заменить простое имя файла полным путем.  
  
 Каждому типу сообщений трассировки назначается уровень, определяющий степень важности типа. Если уровень трассировки домена приложения не превышает уровень типа событий, создается сообщение. Уровень трассировки контролируется параметром `switchValue` в файле конфигурации. Уровни, связанные с диагностическими сообщениями трассировки, определены в следующей таблице.  
  
|Уровень трассировки|Описание|  
|-----------------|-----------------|  
|Critical|Указывает на серьезные сбои, например:<br /><br /> -Ошибка, может привести к немедленно потере функциональности пользователя.<br />-Событие, и администратор должен предпринять действия, чтобы избежать потери функциональности.<br />-Зависает кода.<br />— Это уровень трассировки также может предоставить достаточно контекст для интерпретации других важных трассировок. Это позволяет определить последовательность операций, приводящих в серьезному сбою.|  
|Ошибка|Ошибка (например, в результате обнаружения недопустимой конфигурации или недопустимого поведения в сети), которая может привести к потере функциональности.|  
|Предупреждение|Условие, которое может привести к ошибке или критическому сбою (например, в результате неправильного выделения памяти или превышения заданного предела). Предупреждение также может быть сформировано в ходе стандартной обработки ошибок пользовательского кода (например, в результате прерывания транзакции, истечения времени ожидания, непрохождения проверки подлинности).|  
|Сведения|Сообщения, полезные для мониторинга и диагностики состояния системы, измерения производительности или профилирования. К ним, в частности, относятся события транзакции и времени существования зачисления, такие как создание или фиксация транзакции, выход за существенную границу или выделение существенных ресурсов. Эта информация может затем использоваться разработчиком для планирования загрузки и управления производительностью.|  
  
## <a name="trace-codes"></a>Коды трассировки  
 В следующей таблице перечислены коды трассировки, формируемые инфраструктурой <xref:System.Transactions>. В таблице включены идентификатор трассировки кода <xref:System.Diagnostics.EventTypeFilter.EventType%2A> уровень перечисления для трассировки и дополнительные данные, содержащиеся в **TraceRecord** для трассировки. Кроме того, соответствующий уровень трассировки трассировки хранятся также в **TraceRecord**.  
  
|TraceCode|EventType|Дополнительные данные в TraceRecord|  
|---------------|---------------|-------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|Идентификатор TransactionTraceId локальной транзакции, идентификатор TransactionTraceId распределенной транзакции|  
|EnlistmentCreated|Info|TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions|  
|EnlistmentCallbackNegative|Предупреждение|TransactionTraceId, EnlistmentTraceId,<br /><br /> Обратный вызов (forcerollback/aborted/indoubt)|  
|TransactionRollbackCalled|Предупреждение|TransactionTraceId|  
|TransactionAborted|Предупреждение|TransactionTraceId|  
|TransactionInDoubt|Предупреждение|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult. Ниже представлены возможные значения.<br /><br /> -Новую транзакцию.<br />-Переданной транзакции.<br />-Переданный зависимой транзакции.<br />-С помощью текущей транзакции.<br />-Ни одна транзакция.<br /><br /> Идентификатор TransactionTraceId новой текущей транзакции|  
|TransactionScopeDisposed|Info|TransactionTraceId области «ожидается «текущей транзакции.|  
|TransactionScopeIncomplete|Предупреждение|TransactionTraceId области «ожидается «текущей транзакции.|  
|TransactionScopeNestedIncorrectly|Предупреждение|TransactionTraceId области «ожидается «текущей транзакции.|  
|TransactionScopeCurrentTransactionChanged|Предупреждение|Идентификатор TransactionTraceId прежней текущей транзакции, другой идентификатор TransactionTraceId|  
|TransactionScopeTimeout|Предупреждение|TransactionTraceId области «ожидается «текущей транзакции.|  
|DependentCloneCreated|Info|TransactionTraceId, тип созданной зависимой транзакции (RollbackIfNotComplete/BlockCommitUntilComplete)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|GUID диспетчера ресурсов (из базы)|  
|Reenlist|Info|GUID диспетчера ресурсов (из базы)|  
|TransactionSerialized|Info|TransactionTraceId|  
|TransactionException|Ошибка|Сообщение об исключении|  
|InvalidOperationException|Ошибка|Сообщение об исключении|  
|InternalError|Critical|Сообщение об исключении|  
|TransferEvent||При десериализации или повышении транзакции <xref:System.Transactions> до распределенной транзакции выполняется запись текущего идентификатора ActivityID из контекста ExecutionContext и идентификатора распределенной транзакции.<br /><br /> Когда координатор DTC передает обратный вызов управляемому коду, в контексте ExecutionContext в качестве идентификатора ActivityID устанавливается идентификатор распределенной транзакции в течение выполнения обратного вызова.|  
|ConfiguredDefaultTimeoutAdjusted|Предупреждение|Дополнительные данные отсутствуют.|  
|TransactionTimeout|Предупреждение|Идентификатор TransactionTraceId транзакции, время ожидания которой истекает.|  
  
 Схема XML для каждого из указанных выше элемента дополнительных данных имеет следующий формат.  
  
### <a name="transactiontraceidentifier"></a>TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a>EnlistmentTraceIdentifier  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a>Идентификатор диспетчера ресурсов  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a>Проблемы безопасности, связанные с трассировкой  
 Когда вы как администратор включить трассировку, конфиденциальные сведения могут быть записаны в журнал трассировки, общедоступный по умолчанию. Чтобы устранить любые угрозу безопасности, следует хранить журнал трассировки в безопасном месте контролируется правами доступа папки и файла.
