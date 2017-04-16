---
title: "Элемент &lt;publisherPolicy&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<publisherPolicy> - элемент"
  - "теги контейнеров, <publisherPolicy> - элемент"
  - "publisherPolicy - элемент"
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Элемент &lt;publisherPolicy&gt;
Указывает, будет ли среда выполнения применять политику издателя.  
  
## Синтаксис  
  
```  
  
<publisherPolicy apply="yes|no"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`apply`|Указывает, нужно ли применять политику издателя.|  
  
## применение атрибута  
  
|Значение|Описание|  
|--------------|--------------|  
|`yes`|Политика издателя применяется.  Этот флажок установлен по умолчанию.|  
|`no`|Политика издателя не применяется.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Когда разработчик компонентов выпускает новую версию сборки, он может включить политику издателя, чтобы приложения, использующие старую версию, работали с новой версией.  Чтобы указать, будет ли применяться политика издателя для определенной сборки, необходимо поместить элемент **\<publisherPolicy\>** внутрь элемента **\<dependentAssembly\>**.  
  
 Значение по умолчанию для атрибута **apply** — **yes**.  Установка значения **no** атрибута **apply**  переопределяет любые предыдущие значения **yes**.  
  
 Приложению требуется разрешение, чтобы явно игнорировать политику издателя с помощью элемента [\<publisherPolicy apply\="no"\/\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.  Разрешение можно получить путем установки флага [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) в классе [SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  Дополнительные сведения см. в разделе [Разрешение безопасности перенаправления привязки сборок](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Пример  
 В следующем примере производится отключение политики издателя для сборки `myAssembly`.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)