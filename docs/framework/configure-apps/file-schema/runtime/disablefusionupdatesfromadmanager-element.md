---
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: 4e7375fddaa98b45766b29d911d555f773edcafa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117442"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<Дисаблефусионупдатесфромадманажер > элемент
Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<дисаблефусионупдатесфромадманажер >**  
  
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
  
|значения|Описание|  
|-----------|-----------------|  
|0|Не отключайте возможность переопределения параметров Fusion. Это поведение по умолчанию, начиная с .NET Framework 4.|  
|1|Отключить возможность переопределения параметров Fusion. Это позволяет вернуться к поведению более ранних версий .NET Framework.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Заметки  
 Начиная с .NET Framework 4, поведение по умолчанию — разрешить объекту <xref:System.AppDomainManager> переопределять параметры конфигурации с помощью свойства <xref:System.AppDomainSetup.ConfigurationFile%2A> или метода <xref:System.AppDomainSetup.SetConfigurationBytes%2A> объекта <xref:System.AppDomainSetup>, который передается в реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>. в подклассе <xref:System.AppDomainManager>. Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения. Для других доменов приложений они переопределяют параметры конфигурации, которые были переданы методу <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>.  
  
 Можно либо передать новые сведения о конфигурации, либо передать значение null (`Nothing` в Visual Basic), чтобы исключить переданные конфигурации.  
  
 Не следует передавать сведения о конфигурации как в свойство <xref:System.AppDomainSetup.ConfigurationFile%2A>, так и в метод <xref:System.AppDomainSetup.SetConfigurationBytes%2A>. Если данные конфигурации передаются в оба значения, то данные, передаваемые в свойство <xref:System.AppDomainSetup.ConfigurationFile%2A>, игнорируются, так как метод <xref:System.AppDomainSetup.SetConfigurationBytes%2A> переопределяет сведения о конфигурации из файла конфигурации приложения. При использовании свойства <xref:System.AppDomainSetup.ConfigurationFile%2A> можно передать NULL (`Nothing` в Visual Basic) методу <xref:System.AppDomainSetup.SetConfigurationBytes%2A>, чтобы исключить все байты конфигурации, указанные в вызове метода <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>.  
  
 Помимо сведений о конфигурации, можно изменить следующие параметры объекта <xref:System.AppDomainSetup>, который передается в реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>и <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 В качестве альтернативы использованию элемента `<disableFusionUpdatesFromADManager>` можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды. В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и установите значение 1. В командной строке задайте для переменной среды `COMPLUS_disableFusionUpdatesFromADManager` значение 1.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью элемента `<disableFusionUpdatesFromADManager>`.  
  
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
