---
title: "&lt;participants&gt; (WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;participants&gt; (WCF)
Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их \(в зависимости от настройки\).  Включает запись результата в определенном виде \(например, в виде файла, консоли, ETW\), обработку или сбор записей или любое другое требуемое сочетание.  
  
 Дополнительные сведения об отслеживании рабочего процесса и участниках отслеживания см. в разделах [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md) и [Участники отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md).  
  
## Синтаксис  
  
```vb  
  
<tracking>   
   <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
   </participants>   
</tracking>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|Содержит настройки участника отслеживания.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<tracking\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.|  
  
## Заметки  
 Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.  Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.  
  
 События отслеживания могут использоваться несколькими участниками отслеживания одновременно.  Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.  
  
 Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.  Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.  Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.  Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.  
  
## Пример  
 В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.  
  
 Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе `<diagnostics>`.  Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.  Это определяется атрибутом `profileName` элемента `<add>`.  После их определения участник отслеживания добавляется к поведению службы `<etwTracking>`.  При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.  
  
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
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>   
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehavior>   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Участники отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)