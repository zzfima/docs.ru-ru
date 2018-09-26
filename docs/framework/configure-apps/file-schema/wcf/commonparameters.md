---
title: '&lt;Общие параметры&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 5e4c19c48709ffd81cb00e9820e6c3cdb297ec7e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47086402"
---
# <a name="ltcommonparametersgt"></a>&lt;Общие параметры&gt;
Представляет коллекцию параметров, используемых глобально в нескольких службах. Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<workflowRuntime >  
\<commonParameters >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|Добавляет в коллекцию пару общих параметров вида «имя-значение», используемых службами.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<workflowRuntime >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб на основе рабочего процесса Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
> [!NOTE]
>  Служба отслеживания SQL не использует постоянно значение `ConnectionString`, если оно задано в разделе `<commonParameters>`. В некоторых операциях, например при извлечении свойства `StateMachineWorkflowInstance.StateHistory`, может произойти ошибка. Чтобы обойти эту проблему, задайте атрибут `ConnectionString` в разделе конфигурации для поставщика отслеживания, как показано в следующем примере.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 Обратите внимание, что `EnableRetries` параметра можно задать либо на глобальном уровне (как показано в *CommonParameters* раздел) или для отдельных служб, поддерживающих `EnableRetries` (как показано в *служб*раздел).  
  
 В следующем примере кода показано, как изменять общие параметры программным образом.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).  
  
## <a name="example"></a>Пример  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
