---
title: <add> из <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 65b8a34250a22da79e900f6bee894b501c5ad6ba
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284548"
---
# <a name="add-of-participants"></a>\<Добавить > из \<участников >
Настройте участника отслеживания, который будет прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки). Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.  
  
 Дополнительные сведения об отслеживании рабочих процессов и участники отслеживания, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
\<system.serviceModel>  
\<Отслеживание >  
\<Участники >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|имя|Строка, задающая имя участника отслеживания.|  
|profileName|Строка, задающая имя профиля отслеживания, который определяет, на какие записи отслеживания подписан участник.|  
|тип|Строка, задающая тип участника отслеживания.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Участники >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Список участников отслеживания|  
  
## <a name="remarks"></a>Примечания  
 Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители. Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.  
  
 События отслеживания могут использоваться несколькими участниками отслеживания одновременно. Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.  
  
 Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW. Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием. Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий. Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.  
  
 Идентификатор поставщика, который используется участником отслеживания ETW использует для внесения записей отслеживания в ETW, определяется в  **\<диагностики >** раздел. Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан. Это определяется **profileName** атрибут  **\<Добавить >** элемент. После их определения участник отслеживания добавляется  **\<etwTracking >** поведение службы. При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.  
  
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
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Участники отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
