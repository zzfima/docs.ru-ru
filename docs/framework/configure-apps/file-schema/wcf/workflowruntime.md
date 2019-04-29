---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: db5e1083c07d4e204eb19eaae9257ed44439132e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673151"
---
# <a name="workflowruntime"></a>\<workflowRuntime >
Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб на основе рабочего процесса Windows Communication Foundation (WCF).  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<workflowRuntime >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|cachedInstanceExpiration|Необязательное значение <xref:System.TimeSpan>, определяющее максимальный период времени, в течение которого экземпляр рабочего процесса может оставаться в памяти в неактивном состоянии до принудительной выгрузки или прекращения. Если среда выполнения рабочего процесса имеет параметр `PersistenceService`, выполняющий unloadOnIdle, этот атрибут игнорируется.|  
|enablePerformanceCounters|Необязательное логическое значение, определяющее, включены ли счетчики производительности. Счетчики производительности предоставляют статистические данные о различных рабочих процессах, но они могут вызывать снижение производительности при запуске подсистемы среды выполнения рабочего процесса и при выполнении экземпляров рабочего процесса. Значение по умолчанию — `true`.|  
|имя|Строка, содержащая имя подсистемы среды выполнения рабочих процессов. Имя используется в выходных данных для различения данной среды выполнения от других сред выполнения, которые могут выполняться в системе, например в счетчиках производительности.<br /><br /> Значение по умолчанию - пустая строка.|  
|validateOnCreate|Необязательное логическое значение, указывающее, будет ли выполняться проверка определения рабочего процесса при открытии WorkflowServiceHost.  Если этому атрибуту задано значение `true`, проверка рабочего процесса выполняется при каждом вызове `WorkflowServiceHost.Open`. В случае обнаружения ошибок проверки возникает ошибка <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.<br /><br /> Если это свойство имеет значение `false`, проверка определения рабочего процесса не выполняется.<br /><br /> Значение по умолчанию для этого свойства — `true`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|commonParameters|Коллекция общих параметров, используемых службой. Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.|  
|службы|Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>. Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>. Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов. Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объект ведущего приложения Windows Workflow Foundation, см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).  
  
## <a name="example"></a>Пример  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [Файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
