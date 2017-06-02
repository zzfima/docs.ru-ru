---
title: "Элемент &lt;generatePublisherEvidence&gt; | Microsoft Docs"
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
  - "<generatePublisherEvidence> - элемент"
  - "generatePublisherEvidence - элемент"
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Элемент &lt;generatePublisherEvidence&gt;
Указывает, будет ли среда выполнения создает свидетельство <xref:System.Security.Policy.Publisher> для управления доступом для кода \(CAS\).  
  
## Синтаксис  
  
```  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будет ли среда выполнения создает свидетельство <xref:System.Security.Policy.Publisher>.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Не создает свидетельств <xref:System.Security.Policy.Publisher>.|  
|`true`|Создает свидетельство <xref:System.Security.Policy.Publisher>.  Это значение по умолчанию.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## Заметки  
  
> [!NOTE]
>  В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версиях этот элемент не влияет на время загрузки сборки.  Дополнительные сведения об системе политики безопасности см. [Изменения системы безопасности](../../../../../docs/framework/security/security-changes.md).  
  
 Среда CLR пытается подтвердить подпись Authenticode во время загрузки, чтобы создать свидетельство <xref:System.Security.Policy.Publisher> для сборки.  Однако по умолчанию большинство приложений не требует свидетельства <xref:System.Security.Policy.Publisher>.  Стандартная политика управления доступа для кода \(CAS\) не использует класс <xref:System.Security.Policy.PublisherMembershipCondition>.  Следует избегать дополнительного использования ресурсов при запуске, связанного с проверкой подписи издателя, за исключением случаев, когда приложение выполняется на компьютере с пользовательской политикой управления доступом для кода \(CAS\) или предназначено для обработки запросов по классу <xref:System.Security.Permissions.PublisherIdentityPermission> в среде с частичным доверием. \(Запросы разрешений идентификации всегда выполняются в среде с полным доверием.\)  
  
> [!NOTE]
>  Для увеличения производительности при запуске рекомендуется использовать в службах элемент `<generatePublisherEvidence>`.  Использование данного элемента также позволяет предотвратить задержки, которые могут привести к превышению времени ожидания и отмене запуска службы.  
  
## Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показано, как использовать элемент `<generatePublisherEvidence>`, чтобы отключить для приложения проверку политики издателя по управлению доступом для кода \(CAS\).  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)