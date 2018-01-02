---
title: "&lt;diagnostics&gt; для активации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20b956bb58142f26fa1402f1f974b3984ed759f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a>&lt;diagnostics&gt; для активации
Настраивает диагностические функции прослушивателя службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
 \<system.serviceModel.activation >  
\<Диагностика >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`performanceCountersEnabled`|Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
