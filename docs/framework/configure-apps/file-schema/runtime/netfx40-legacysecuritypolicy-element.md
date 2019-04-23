---
title: Элемент <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a0ca8560fcd5d7f9d171df3e3b4c3f42e78641
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075994"
---
# <a name="netfx40legacysecuritypolicy-element"></a>\<NetFx40_LegacySecurityPolicy > элемент
Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.  
  
 \<configuration>  
\<Среда выполнения >  
<NetFx40_LegacySecurityPolicy>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли среда выполнения политику разграничения доступа кода прежних версий.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения использует политику разграничения доступа кода прежних версий. Это значение по умолчанию.|  
|`true`|Среда выполнения использует политику разграничения доступа кода прежних версий.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 3.5 и более ранних версий политика разграничения доступа кода настроена на срабатывание всегда. В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], необходимо включить политику CAS.  
  
 Политика разграничения доступа кода зависит от версии. Пользовательские политики разграничения доступа кода, которые существуют в более ранних версиях платформы .NET Framework, необходимо заново определить в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Применение `<NetFx40_LegacySecurityPolicy>` элемент [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] сборки не влияет на [прозрачный с точки зрения безопасности код](../../../../../docs/framework/misc/security-transparent-code.md); по-прежнему применяются правила прозрачности.  
  
> [!IMPORTANT]
>  Применение `<NetFx40_LegacySecurityPolicy>` элемента может привести к снижению производительности для сборки образов в машинном коде, созданные [генератором машинных образов (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) , которые не установлены в [глобальный кэш сборок ](../../../../../docs/framework/app-domains/gac.md). На снижение производительности связано с невозможностью среды выполнения загружать сборки как образы в машинном коде при применении атрибута, что приводит к их загруженных сборок как just-in-time.  
  
> [!NOTE]
>  Если вы укажите целевой версии .NET Framework, более ранняя, чем [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] в параметрах проекта для проекта Visual Studio, политика разграничения доступа кода будет включена, включая любые настраиваемые политики разграничения доступа кода, указанных для данной версии. Тем не менее, нельзя будет использовать новое [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] типы и члены. Можно также указать более ранней версии платформы .NET Framework с помощью [ \<supportedRuntime > элемент](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) в схеме параметров запуска в вашей [файла конфигурации приложения](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Синтаксис файлов конфигурации учитывается регистр. Следует использовать синтаксис, как указано в разделах синтаксиса и пример.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано включение устаревшая политика CAS для приложения.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
