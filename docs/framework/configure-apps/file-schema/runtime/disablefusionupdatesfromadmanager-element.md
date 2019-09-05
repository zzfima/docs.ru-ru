---
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b65711ad8c404d1c4f54a6197faf598e2215226f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252651"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<Элемент > Дисаблефусионупдатесфромадманажер
Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Дисаблефусионупдатесфромадманажер >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, отключена ли возможность по умолчанию переопределять параметры Fusion.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключайте возможность переопределения параметров Fusion. Это поведение по умолчанию, начиная с .NET Framework 4.|  
|1|Отключить возможность переопределения параметров Fusion. Это позволяет вернуться к поведению более ранних версий .NET Framework.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework 4, поведение по умолчанию заключается в том, <xref:System.AppDomainManager> чтобы разрешить объекту переопределять параметры конфигурации с <xref:System.AppDomainSetup.ConfigurationFile%2A> помощью свойства <xref:System.AppDomainSetup> или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метода объекта, который передается в вашу реализацию. метода в подклассе <xref:System.AppDomainManager>. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения. Для других доменов приложений они переопределяют параметры конфигурации, переданные <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> в метод или. <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>  
  
 Можно либо передать новые сведения о конфигурации, либо передать значение NULL`Nothing` (в Visual Basic), чтобы исключить переданные конфигурации.  
  
 Не следует передавать сведения о конфигурации как в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, так <xref:System.AppDomainSetup.SetConfigurationBytes%2A> и в метод. Если данные о конфигурации передаются в оба значения, то данные, <xref:System.AppDomainSetup.ConfigurationFile%2A> передаваемые в свойство, игнорируются, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> так как метод переопределяет сведения о конфигурации из файла конфигурации приложения. При <xref:System.AppDomainSetup.ConfigurationFile%2A> использовании свойства можно передать значение null (`Nothing` <xref:System.AppDomainSetup.SetConfigurationBytes%2A> в Visual Basic) методу, чтобы исключить все байты конфигурации <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> , указанные в вызове метода или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .  
  
 Помимо сведений о конфигурации, можно изменить следующие параметры <xref:System.AppDomainSetup> объекта, который передается в реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>,, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, и<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A>  
  
 В качестве альтернативы использованию `<disableFusionUpdatesFromADManager>` элемента можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды. В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и установите значение 1. В командной строке задайте для переменной `COMPLUS_disableFusionUpdatesFromADManager` среды значение 1.  
  
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

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Обнаружение сборок в среде выполнения](../../../deployment/how-the-runtime-locates-assemblies.md)
