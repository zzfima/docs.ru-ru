---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b4b1903182cfa20944d919f57ff1e09e07953b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsqlworkflowinstancestoregt"></a>&lt;sqlWorkflowInstanceStore&gt;
Поведение службы, можно настроить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> функции, которая поддерживает сохранение сведений о состоянии экземплярами службы рабочего процесса в базу данных SQL Server 2005 или SQL Server 2008. Дополнительные сведения об этой функции см. в разделе [хранилище экземпляров рабочих процессов SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
\<система. ServiceModel >  
\<поведения >  
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
|connectionStringName|Строка, содержащая именованную строку соединения для сервера базы данных. Примером именованной строки соединения является «DefaultConnectionString».|  
|honstLockRenewalPeriod|Значение Timespan, определяющее время, в течение которого узел должен обновить блокировку на экземпляре. Если узел не возобновит блокировку в указанный период времени, то экземпляр будет разблокирован и может быть принят другим узлом.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение. Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после рабочий процесс становится неактивным. Задав этому атрибуту значение TimeSpan.MaxValue фактически операция выгрузки будет отключена. Простаивающие экземпляры рабочего процесса не выгружаются.|  
|instanceCompletionAction|Значение, которое указывает, будут сохранены данные экземпляра рабочего процесса в хранилище сохраняемости после завершения работы экземпляра рабочего процесса или удалены на этом этапе. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Перечисленные действия состоят из удаления данных экземпляра из хранилища сохраняемости или отказа от удаления данных после завершения операции экземпляром.<br /><br /> Если экземпляры сохраняются после завершения, то это вызывает быстрый рост базы данных постоянного хранения, что влияет на производительность базы данных. Следует настроить политику очищения базы данных для периодического удаления этих записей, чтобы гарантировать уровень производительности базы данных, удовлетворяющий требованиям пользователя.|  
|instanceEncodingOption|Необязательное значение, которое указывает, производится ли сжатие информации о состоянии экземпляра при использовании алгоритма GZip, прежде чем она будет сохранена в хранилище сохраняемости. Это значение имеет тип `System.Activities.DurableInstancing.InstanceEncodingAction`. Допустимые значения для этого свойства — «Нет», который указывает на отсутствие сжатия и «GZip», который указывает этот экземпляр данных сжат и с использованием алгоритма gzip.|  
|instanceLockedExceptionAction|Значение, определяющее действие, которое возникает в ответ на исключение, если узел пытается заблокировать экземпляр, который в настоящий момент заблокирован другим узлом. Это значение имеет тип <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Допустимые варианты для данного поля: Нет (None), простой повтор (Basic Retry) и агрессивный повтор (Aggressive Retry). По умолчанию используется значение None. В следующем списке приводятся описания этих трех вариантов.<br /><br /> — Нет. Узел службы не пытается заблокировать экземпляр и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему.<br />-Простой повтор. Узел службы повторно пытается заблокировать экземпляр с линейным интервалом повторений и передает исключение вызывающему в конце последовательности.<br />-Агрессивный повтор. Узел службы повторно пытается заблокировать экземпляр (с экспоненциально увеличивающейся задержкой) и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему в конце последовательности.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение > из \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
 [Хранилище экземпляров рабочих процессов SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
