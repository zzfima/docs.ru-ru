---
title: "&lt;sqlWorkflowInstanceStore&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;sqlWorkflowInstanceStore&gt;
Поведение службы, которое позволяет настроить функцию <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, поддерживающую сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.  Дополнительные сведения об этой функции см. в разделе [Хранилище экземпляров рабочих процессов SQL](../../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  
  
## Синтаксис  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <sqlWorkflowInstanceStore   
          connectionStringName=”String”   
          honstLockRenewalPeriod=”TimeSpan”  
          instanceCompletionAction=”DeleteNothing/DeleteAll”  
          instanceEncodingAction=”None/GZip”  
          instanceLockedExceptionAction=”NoRetry/BasicRetry/AggressiveRetry”  
          runnableInstancesDetectionPeriod=”TimeSpan” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|connectionString|Строка, содержащая строку подключения, используемую для соединения с основной базой данной сохраняемости.|  
|connectionStringName|Строка, содержащая именованную строку соединения с сервером базы данных.  Примером именованной строки соединения является «DefaultConnectionString».|  
|honstLockRenewalPeriod|Значение Timespan, определяющее время, в течение которого узел должен обновить блокировку на экземпляре.  Если узел не возобновит блокировку в указанный период времени, то экземпляр будет разблокирован и может быть принят другим узлом.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение.  Если этот атрибут имеет нулевое значение, экземпляр рабочего процесса сохраняется и выгружается сразу после того, как становится неактивным.  Если задать этому атрибуту значение TimeSpan.MaxValue, операция выгрузки будет фактически отключена.  Простаивающие экземпляры рабочего процесса не выгружаются.|  
|instanceCompletionAction|Значение, которое указывает, будут сохранены данные экземпляра рабочего процесса в хранилище сохраняемости после завершения работы экземпляра рабочего процесса или удалены на этом этапе.  Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Перечисленные действия состоят из удаления данных экземпляра из хранилища сохраняемости или отказа от удаления данных после завершения операции экземпляром.<br /><br /> Если экземпляры сохраняются после завершения, то это вызывает быстрый рост базы данных постоянного хранения, что влияет на производительность базы данных.  Следует настроить политику очищения базы данных для периодического удаления этих записей, чтобы гарантировать уровень производительности базы данных, удовлетворяющий требованиям пользователя.|  
|instanceEncodingOption|Необязательное значение, которое указывает, производится ли сжатие информации о состоянии экземпляра при использовании алгоритма GZip, прежде чем она будет сохранена в хранилище сохраняемости.  Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceEncodingAction>.  Возможные значения для этого свойства «None», что означает отсутствие сжатия, и «GZip», что означает, что данные экземпляра сжимаются с использованием алгоритма gzip.|  
|instanceLockedExceptionAction|Значение, определяющее действие, которое возникает в ответ на исключение, если узел пытается заблокировать экземпляр, который в настоящий момент заблокирован другим узлом.  Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Допустимые варианты для данного поля: Нет \(None\), простой повтор \(Basic Retry\) и агрессивный повтор \(Aggressive Retry\).  По умолчанию используется значение None.  В следующем списке приводятся описания этих трех вариантов.<br /><br /> -   Отсутствует.  Узел службы не пытается заблокировать экземпляр и передает исключение <xref:System.Runtime.Persistence.InstanceLockedException> вызывающему.<br />-   Простой повтор.  Узел службы повторно пытается заблокировать экземпляр с линейным интервалом повторений и передает исключение вызывающему в конце последовательности.<br />-   Агрессивный повтор.  Узел службы повторно пытается заблокировать экземпляр \(с экспоненциально увеличивающейся задержкой\) и передает исключение <xref:System.Runtime.Persistence.InstanceLockedException> вызывающему в конце последовательности.|  
|runnableInstancesDetectionPeriod||  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<behavior\> для \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## См. также  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>   
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>   
 [Хранилище экземпляров рабочих процессов SQL](../../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)