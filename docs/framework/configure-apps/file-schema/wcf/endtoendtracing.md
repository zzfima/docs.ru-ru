---
title: '&lt;endToEndTracing&gt;'
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: c2f5e33eff4fdc6dfa85bcc10b59a7c1436cabb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519403"
---
# <a name="ltendtoendtracinggt"></a>&lt;endToEndTracing&gt;
Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.  
  
 \<system.ServiceModel>  
\<диагностические >  
\<endToEndTracing >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`activityTracing`|Логическое значение, указывающее, включено ли отслеживание действия.|  
|`messageFlowTracing`|Логическое значение, указывающее, включено ли отслеживание потока сообщений.|  
|`propagateActivity`|Логическое значение, указывающее, задано ли атрибуту propagate значение true.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Диагностика >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Определяет параметры WCF для проверки во время выполнения и управления администратором.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [Сквозная трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
