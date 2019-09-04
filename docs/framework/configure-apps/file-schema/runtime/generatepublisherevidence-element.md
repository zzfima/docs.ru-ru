---
title: Элемент <generatePublisherEvidence>
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd3105e573d40ae234ba7e122f20566911124d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252539"
---
# <a name="generatepublisherevidence-element"></a>\<Элемент > generatePublisherEvidence
Указывает, создает <xref:System.Security.Policy.Publisher> ли среда выполнения свидетельство для управления доступом для кода (CAS).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, создает <xref:System.Security.Policy.Publisher> ли среда выполнения свидетельство.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не создает <xref:System.Security.Policy.Publisher> свидетельство.|  
|`true`|Создает <xref:System.Security.Policy.Publisher> свидетельство. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> В .NET Framework 4 и более поздних версиях этот элемент не влияет на время загрузки сборки. Дополнительные сведения см. в разделе "упрощение политики безопасности" раздела [изменения в системе безопасности](../../../security/security-changes.md).  
  
 Среда CLR пытается проверить подпись Authenticode во время загрузки, чтобы создать <xref:System.Security.Policy.Publisher> свидетельство для сборки. Однако по умолчанию большинству приложений не требуется <xref:System.Security.Policy.Publisher> свидетельство. Стандартная политика CAS не зависит от <xref:System.Security.Policy.PublisherMembershipCondition>. Следует избегать ненужных затрат на запуск, связанных с проверкой подписи издателя, если приложение не выполняется на компьютере с настраиваемой политикой CAS или планирует удовлетворить требования <xref:System.Security.Permissions.PublisherIdentityPermission> к в среде с частичным доверием. (Требования для разрешений идентификации всегда выполняются в среде с полным доверием.)  
  
> [!NOTE]
> Рекомендуется, чтобы службы использовали `<generatePublisherEvidence>` элемент для повышения производительности при запуске.  Использование этого элемента также может помочь избежать задержек, которые могут привести к превышению времени ожидания и отмене запуска службы.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<generatePublisherEvidence>` элемент, чтобы отключить проверку политики издателя CAS для приложения.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
