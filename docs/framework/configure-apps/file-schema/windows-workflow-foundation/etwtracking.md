---
title: "&lt;etwTracking&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;etwTracking&gt;
Поведение службы позволяет ей использовать отслеживание ETW совместно с <xref:System.Activities.Tracking.ETWTrackingParticipant>.  
  
## Синтаксис  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <etwTracking profileName=”String” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|profileName|Строка, указывающая имя профиля отслеживания, связанного с этим поведением.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<behavior\> для \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## Заметки  
 Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.  
  
 Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.  Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.  
  
## Пример  
 В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.  
  
 Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе **\<diagnostics\>**.  Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.  Это определяется атрибутом **profileName** элемента **\<add\>**.  После их определения участник отслеживания добавляется к поведению службы **\<etwTracking\>**.  При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.  
  
```  
  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Участники отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)