---
title: "Элемент &lt;PreferComInsteadOfManagedRemoting&gt; | Microsoft Docs"
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
  - "<PreferComInsteadOfManagedRemoting> - элемент"
  - "PreferComInsteadOfManagedRemoting - элемент"
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Элемент &lt;PreferComInsteadOfManagedRemoting&gt;
Задает, будет ли среда выполнения использовать COM\-взаимодействие вместо удаленного взаимодействия для всех вызовов за пределами границ домена приложения.  
  
## Синтаксис  
  
```  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будет ли среда выполнения использовать COM\-взаимодействие вместо удаленного взаимодействия за пределами границ домена приложения.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|За пределами границ домена приложения среда выполнения будет использовать удаленное взаимодействие.  Это значение по умолчанию.|  
|`true`|За пределами границ домена приложения среда выполнения будет использовать COM\-взаимодействие.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Если для атрибута `enabled` задано значение `true`, среда выполнения ведет себя следующим образом:  
  
-   Среда выполнения не вызывает [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) для интерфейса [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md), если интерфейс [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) входит в домен через интерфейс модели COM.  Вместо этого она создает вокруг объекта оболочку [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) \(вызываемая оболочка времени выполнения\).  
  
-   Среда выполнения возвращает E\_NOINTERFACE, когда она получает вызов `QueryInterface` для интерфейса [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) для любой оболочки [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) \(вызываемая оболочка COM\), которая была создана в этом домене.  
  
 Эти два поведения гарантируют, что все вызовы через COM\-интерфейсы между управляемыми объектами через границы домена приложения используют модель COM и COM\-взаимодействие, а не удаленное взаимодействие.  
  
## Пример  
 В следующем примере показано, как указать, что среда выполнения должна использовать COM\-взаимодействие вместо изоляции.  
  
```  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)