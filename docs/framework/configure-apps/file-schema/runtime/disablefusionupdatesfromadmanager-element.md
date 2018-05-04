---
title: '&lt;disableFusionUpdatesFromADManager&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e5e33cd3d250b26f0a83a87c4f7ce438af22e96
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a>&lt;disableFusionUpdatesFromADManager&gt; элемент
Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<disableFusionUpdatesFromADManager >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, отключен ли по умолчанию возможность переопределения параметров Fusion.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключайте возможность переопределения параметров Fusion. Это поведение по умолчанию, начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Отключите возможность переопределения параметров Fusion. При этом восстанавливается поведение предыдущих версий платформы .NET Framework.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], поведение по умолчанию разрешено <xref:System.AppDomainManager> для переопределения параметров конфигурации с помощью <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод <xref:System.AppDomainSetup> объекта, передаваемого в вашу реализацию из <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод в вашем подклассе <xref:System.AppDomainManager>. Для домена приложения по умолчанию, изменить параметры переопределяют параметры, указанные в файле конфигурации приложения. Для других доменов приложений они переопределяют параметры конфигурации, которые были переданы <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод.  
  
 Можно передать новые сведения о конфигурации, или передайте значение null (`Nothing` в Visual Basic) для исключения сведений о конфигурации, который был передан.  
  
 Не следует передавать сведения о конфигурации и <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство и <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод. Если как передать сведения о конфигурации, сведения о передаче <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство игнорируется, так как <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод переопределяет сведения о конфигурации из файла конфигурации приложения. Если вы используете <xref:System.AppDomainSetup.ConfigurationFile%2A> свойства, можно передать значение null (`Nothing` в Visual Basic) для <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод, чтобы удалить любые байты конфигурации, которые были указаны в вызове <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод.  
  
 Помимо сведений о конфигурации, можно изменить следующие параметры на <xref:System.AppDomainSetup> объекта, передаваемого в вашу реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, и <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 В качестве альтернативы с помощью `<disableFusionUpdatesFromADManager>` элемента, можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды. В реестре создайте параметр DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` под `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и задайте значение 1. В командной строке, задайте переменную среды `COMPLUS_disableFusionUpdatesFromADManager` значение 1.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью `<disableFusionUpdatesFromADManager>` элемента.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
