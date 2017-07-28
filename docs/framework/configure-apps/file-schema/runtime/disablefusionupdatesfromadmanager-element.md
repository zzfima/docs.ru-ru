---
title: "Элемент &lt;disableFusionUpdatesFromADManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<disableFusionUpdatesFromADManager> - элемент"
  - "disableFusionUpdatesFromADManager - элемент"
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Элемент &lt;disableFusionUpdatesFromADManager&gt;
Задает, отключено ли поведение по умолчанию, которое разрешает хост\-приложению среды выполнения переопределять параметры конфигурации для домена приложения.  
  
## Синтаксис  
  
```  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|enabled|Обязательный атрибут.<br /><br /> Задает, отключена ли доступная по умолчанию возможность переопределять параметры Fusion.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|0|Не отключать возможность переопределения параметров Fusion.  Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], это поведение по умолчанию.|  
|1|Отключить возможность переопределения параметров Fusion.  Это позволяет вернуться к поведению предыдущих версий платформы .NET Framework.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], по умолчанию объекту <xref:System.AppDomainManager> разрешено переопределять параметры конфигурации с помощью свойства <xref:System.AppDomainSetup.ConfigurationFile%2A> или метода <xref:System.AppDomainSetup.SetConfigurationBytes%2A> объекта <xref:System.AppDomainSetup>, передаваемого в вашу реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName> в вашем подклассе <xref:System.AppDomainManager>.  Для домена приложения по умолчанию изменяемые вами параметры переопределяют параметры, которые были заданы в файле конфигурации приложения.  Для других доменов приложений они переопределяют параметры конфигурации, которые были переданы методу <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName>.  
  
 Вы можете передать или новые сведения о конфигурации, или значение NULL \(`Nothing` в Visual Basic\), чтобы удалить переданные сведения о конфигурации.  
  
 Не передавайте сведения о конфигурации одновременно свойству <xref:System.AppDomainSetup.ConfigurationFile%2A> и методу <xref:System.AppDomainSetup.SetConfigurationBytes%2A>.  Если передать сведения о конфигурации и свойству, и методу, сведения, переданные свойству <xref:System.AppDomainSetup.ConfigurationFile%2A>, игнорируются, так как метод <xref:System.AppDomainSetup.SetConfigurationBytes%2A> переопределяет сведения о конфигурации из файла конфигурации приложения.  Если используется свойство <xref:System.AppDomainSetup.ConfigurationFile%2A>, можно передать значение NULL \(`Nothing` в Visual Basic\) методу <xref:System.AppDomainSetup.SetConfigurationBytes%2A>, чтобы удалить любые байты конфигурации, которые были указаны в вызове метода <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName>.  
  
 Помимо сведений о конфигурации, в объекте <xref:System.AppDomainSetup>, переданном в вашу реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName>, можно изменить указанные ниже параметры: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> и <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Вместо использования элемента `<disableFusionUpdatesFromADManager>`, поведение по умолчанию можно отключить, создав параметр реестра или задав переменную среды.  В реестре создайте ключ типа DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework` и задайте для него значение 1.  В командной строке задайте для переменной среды `COMPLUS_disableFusionUpdatesFromADManager` значение 1.  
  
## Пример  
 В следующем примере кода показано, как отключить возможность переопределения параметров Fusion с помощью элемента `<disableFusionUpdatesFromADManager>`.  
  
```  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)