---
title: "&lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;behavior&gt; &lt;serviceBehaviors&gt; рабочего процесса
Элемент **behavior** содержит коллекцию параметров для поведения службы.  Каждое поведение индексируется по атрибуту **name**.  Службы могут связаться с каждым поведением посредством этого имени, используя атрибут **behaviorConfiguration** элемента [\<конечная точка\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md).  Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.  
  
## Синтаксис  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name=String">  
      <bufferReceive maxPendingMessagesPerChannel=”Integer” />  
      <etwTracking profileName=”String” />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName=”String”   
          honstLockRenewalPeriod=”TimeSpan”  
          instanceCompletionAction=”DeleteNothing/DeleteAll”  
          instanceEncodingAction=”None/GZip”  
          instanceLockedExceptionAction=”NoRetry/BasicRetry/AggressiveRetry”  
          runnableInstancesDetectionPeriod=”TimeSpan” />  
      <workflowIdle timeToPersist=”TimeSpan”  
          timeToUnload=”TimeSpan” />  
      <workflowUnhandledException action=”Abandon/AbandonAndSuspend/Cancel/Terminate” />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Уникальная строка, содержащая имя конфигурации поведения.  Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<bufferReceive\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Поведение службы позволяет ей использовать отслеживание ETW совместно с <xref:System.Activities.Tracking.ETWTrackingParticipant>.|  
|[\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.|  
|[\<sqlWorkflowInstanceStore\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|Поведение службы, которое позволяет настроить функцию <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, поддерживающую сохранение сведений о состоянии для экземпляров службы рабочего процесса в базе данных SQL Server 2005 или SQL Server 2008.|  
|[\<workflowIdle\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.|  
|[\<workflowInstanceManagement\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.|  
|[\<workflowUnhandledException\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Коллекция элементов поведений службы.|