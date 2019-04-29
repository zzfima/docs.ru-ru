---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 8601f1c7f4e1dbf911020c328652c371bf039124
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794438"
---
# <a name="sqlworkflowinstancestore"></a>\<sqlWorkflowInstanceStore >
Поведение службы, которое позволяет настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функция, которая поддерживает сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008. Дополнительные сведения об этой функции см. в разделе [Store экземпляра рабочего процесса SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
\<system.ServiceModel>  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<sqlWorkflowInstanceStore >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|connectionString|Строка, содержащая строку подключения, используемая для подключения к основной базе данных сохраняемости.|  
|connectionStringName|Строка, содержащая именованную строку соединения для сервера базы данных. Примером именованную строку соединения является «DefaultConnectionString».|  
|honstLockRenewalPeriod|Значение Timespan, определяющее время, в течение которого узел должен обновить блокировку на экземпляре. Если узел не возобновит блокировку в указанный период времени, то экземпляр будет разблокирован и может быть принят другим узлом.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение. Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после становится неактивным. Установка для данного атрибута TimeSpan.MaxValue эффективно отключает операция выгрузки. Простаивающие экземпляры рабочего процесса не выгружаются.|  
|instanceCompletionAction|Значение, которое указывает, будут сохранены данные экземпляра рабочего процесса в хранилище сохраняемости после завершения работы экземпляра рабочего процесса или удалены на этом этапе. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Перечисленные действия состоят из удаления данных экземпляра из хранилища сохраняемости или отказа от удаления данных после завершения операции экземпляром.<br /><br /> Если экземпляры сохраняются после завершения, то это вызывает быстрый рост базы данных постоянного хранения, что влияет на производительность базы данных. Следует настроить политику очищения базы данных для периодического удаления этих записей, чтобы гарантировать уровень производительности базы данных, удовлетворяющий требованиям пользователя.|  
|instanceEncodingOption|Необязательное значение, которое указывает, производится ли сжатие информации о состоянии экземпляра при использовании алгоритма GZip, прежде чем она будет сохранена в хранилище сохраняемости. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Возможные значения для этого свойства: <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>, который указывает на отсутствие сжатия и <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>, который указывает, что данные экземпляра сжимаются с использованием алгоритма gzip.|  
|instanceLockedExceptionAction|Значение, определяющее действие, которое возникает в ответ на исключение, если узел пытается заблокировать экземпляр, который в настоящий момент заблокирован другим узлом. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Ниже приведены допустимые варианты для этого поля. None, простой повтор и Агрессивный повтор. По умолчанию используется значение None. В следующем списке приводятся описания этих трех вариантов.<br /><br /> — Нет. Узел службы не пытается заблокировать экземпляр и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему.<br />-Простой повтор. Узел службы повторно пытается заблокировать экземпляр с линейным интервалом повторений и передает исключение вызывающему в конце последовательности.<br />-Агрессивный повтор. Узел службы повторно пытается заблокировать экземпляр (с экспоненциально увеличивающейся задержкой) и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему в конце последовательности.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение > из \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [Хранилище экземпляров рабочих процессов SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
