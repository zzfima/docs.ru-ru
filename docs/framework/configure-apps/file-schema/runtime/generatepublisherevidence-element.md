---
title: "&lt;generatePublisherEvidence&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7f7debed03526dbd7a5b2e24ff8a370921fe020
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a>&lt;generatePublisherEvidence&gt; элемент
Указывает, будет ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельство для управления доступом для кода (CAS).  
  
 \<configuration>  
\<Среда выполнения >  
\<generatePublisherEvidence >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будет ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельства.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Не создает <xref:System.Security.Policy.Publisher> свидетельства.|  
|`true`|Создает <xref:System.Security.Policy.Publisher> свидетельства. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздней версии, этот элемент не оказывает влияния на время загрузки сборки. Дополнительные сведения см. в подразделе «Упрощение политики безопасности» [изменения системы безопасности](../../../../../docs/framework/security/security-changes.md).  
  
 Общеязыковая среда выполнения (CLR) пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки. Тем не менее, по умолчанию, большинство приложений не обязательно <xref:System.Security.Policy.Publisher> свидетельства. Стандартные политики разграничения доступа кода не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>. Следует избегать при запуске издержки, связанные с проверкой подписи издателя, если приложение выполняется на компьютере с помощью настраиваемой политики разграничения доступа кода или предназначено для <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием. (Запросы разрешений идентификации всегда выполнена в среде с полным доверием).  
  
> [!NOTE]
>  Мы рекомендуем, службы используют `<generatePublisherEvidence>` элемент, чтобы повысить производительность при запуске.  С помощью этого элемента помогает избежать задержек, которые может вызвать тайм-аута и отмене запуска службы.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку политики издателя для приложения.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
