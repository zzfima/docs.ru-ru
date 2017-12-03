---
title: "&lt;Участники&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e20cc8ed26feccf6fcf7fae40d2a219cd103dbb0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltparticipantsgt"></a>&lt;Участники&gt;
Настройте список участников отслеживания, которые будут прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки). Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.  
  
 Дополнительные сведения об отслеживании рабочих процессов и участниках отслеживания см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
\<system.serviceModel >  
\<Отслеживание >  
\<Участники >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|Содержит настройки участника отслеживания.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Отслеживание >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.|  
  
## <a name="remarks"></a>Примечания  
 Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители. Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.  
  
 События отслеживания могут использоваться несколькими участниками отслеживания одновременно. Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.  
  
 Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW. Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием. Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий. Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.  
  
 Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздела. Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан. Это определяется **profileName** атрибут  **\<Добавить >** элемента. После их определения участник отслеживания добавляется к  **\<etwTracking >** поведение службы. При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.  
  
```xml
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
