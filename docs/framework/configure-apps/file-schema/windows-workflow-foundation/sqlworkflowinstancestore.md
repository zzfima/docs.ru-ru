---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 56a44fdb62062903ca3ad00f8105a66ccab02cca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151966"
---
# <a name="sqlworkflowinstancestore"></a>\<sqlWorkflowInstanceStore>
Поведение службы, позволяющее настроить функцию <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, поддерживающую сохранение сведений о состоянии для экземпляров службы рабочего процесса в базу данных SQL Server 2005 или SQL Server 2008. Для получения более подробной [SQL Workflow Instance Store](../../../windows-workflow-foundation/sql-workflow-instance-store.md)информации об этой функции, см.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<поведение>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sqlWorkflowInstanceStore>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String"
                                hostLockRenewalPeriod="TimeSpan"
                                instanceCompletionAction="DeleteNothing/DeleteAll"
                                instanceEncodingAction="None/GZip"
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|connectionString|Строка, содержащая строку подключения, используемую для соединения с основной базой данной сохраняемости.|  
|connectionStringName|Строка, содержащая именованную строку соединения с сервером базы данных. Примером названной строки соединения является "DefaultConnectionString".|  
|hostLockRenewalPeriod|Значение Timespan, определяющее время, в течение которого узел должен обновить блокировку на экземпляре. Если узел не возобновит блокировку в указанный период времени, то экземпляр будет разблокирован и может быть принят другим узлом.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение. Если этот атрибут имеет нулевое значение, экземпляр рабочего процесса сохраняется и выгружается сразу после того, как становится неактивным. Если задать этому атрибуту значение TimeSpan.MaxValue, операция выгрузки будет фактически отключена. Простаивающие экземпляры рабочего процесса не выгружаются.|  
|instanceCompletionAction|Значение, которое указывает, будут сохранены данные экземпляра рабочего процесса в хранилище сохраняемости после завершения работы экземпляра рабочего процесса или удалены на этом этапе. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Перечисленные действия состоят из удаления данных экземпляра из хранилища сохраняемости или отказа от удаления данных после завершения операции экземпляром.<br /><br /> Если экземпляры сохраняются после завершения, то это вызывает быстрый рост базы данных постоянного хранения, что влияет на производительность базы данных. Следует настроить политику очищения базы данных для периодического удаления этих записей, чтобы гарантировать уровень производительности базы данных, удовлетворяющий требованиям пользователя.|  
|instanceEncodingOption|Необязательное значение, которое указывает, производится ли сжатие информации о состоянии экземпляра при использовании алгоритма GZip, прежде чем она будет сохранена в хранилище сохраняемости. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Возможные значения для <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>этого свойства, который не указывает сжатия, и <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>, который указывает, что данные экземпляра сжимается и использует алгоритм gzip.|  
|instanceLockedExceptionAction|Значение, определяющее действие, которое возникает в ответ на исключение, если узел пытается заблокировать экземпляр, который в настоящий момент заблокирован другим узлом. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Допустимые варианты для данного поля: Нет (None), простой повтор (Basic Retry) и агрессивный повтор (Aggressive Retry). По умолчанию используется None. В следующем списке приводятся описания этих трех вариантов.<br /><br /> — Нет. Узел службы не пытается заблокировать экземпляр и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему.<br />- Базовая повторная попытка. Узел службы повторно пытается заблокировать экземпляр с линейным интервалом повторений и передает исключение вызывающему в конце последовательности.<br />- Агрессивная повторная попытка. Узел службы повторно пытается заблокировать экземпляр (с экспоненциально увеличивающейся задержкой) и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему в конце последовательности.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение> \<сервисовПоведение>](behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [Хранилище экземпляров рабочих процессов SQL](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
