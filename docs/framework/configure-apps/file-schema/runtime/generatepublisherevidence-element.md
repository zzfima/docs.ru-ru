---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0861436ca727d63cdae58e3222826bf6414610
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489445"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > элемент
Указывает, является ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельство для Управление доступом для кода (CAS).  
  
 \<configuration>  
\<Среда выполнения >  
\<generatePublisherEvidence>  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, является ли среда выполнения создает <xref:System.Security.Policy.Publisher> свидетельства.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
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
>  В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки. Дополнительные сведения см. в разделе «Упрощение политики безопасности» в [изменения системы безопасности](../../../../../docs/framework/security/security-changes.md).  
  
 Среда CLR (CLR) пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки. Тем не менее, по умолчанию, большинство приложений не обязательно <xref:System.Security.Policy.Publisher> свидетельства. Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>. Следует избегать при запуске затраты, связанные с проверкой подписи издателя, если приложение выполняет на компьютере с нестандартной политики CAS, или собирается для <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием. (Для разрешения идентификаторов всегда удовлетворяются в среде с полным доверием.)  
  
> [!NOTE]
>  Мы рекомендуем, службы используют `<generatePublisherEvidence>` элемент для повышения производительности запуска.  С помощью этого элемента также может помочь избежать задержек, которые могут вызвать тайм-аута и отмене запуска службы.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку для издателя политику CAS для приложения.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
