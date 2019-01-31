---
title: <diagnostics> для активации
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: ac235b9a3c125cd3fe63ccd899e2ff92d4d3f31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278460"
---
# <a name="diagnostics-for-activation"></a>\<Диагностика > для активации
Настраивает диагностические функции прослушивателя службы Windows Communication Foundation (WCF).  
  
 \<system.serviceModel.activation>  
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
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
