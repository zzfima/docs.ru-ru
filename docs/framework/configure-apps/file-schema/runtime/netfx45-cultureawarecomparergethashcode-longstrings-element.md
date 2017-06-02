---
title: "Элемент &lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; | Microsoft Docs"
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
  - "NetFx45_CultureAwareComparerGetHashCode_LongStrings - элемент"
  - "Элемент <NetFx45_CultureAwareComparerGetHashCode_LongStrings>"
  - "GetHashCode - метод"
  - "хэш-коды, вычисление"
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Элемент &lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt;
Определяет, использует ли среда выполнения постоянный объем памяти для вычисления хэш\-кодов методом <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>.  
  
 \<configuration\>  
\<runtime\>  
\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>  
  
## Синтаксис  
  
```vb  
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, выделяет ли среда CLR постоянный объем памяти при вычислении хэш\-кодов.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|0|Среда CLR выделяет переменный объем памяти методу <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> для вычисления хэш\-кодов. Это значение по умолчанию.|  
|1|Среда CLR выделяет постоянный объем памяти методу <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> для вычисления хэш\-кодов.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## Заметки  
 По умолчанию среда CLR выделяет переменный объем памяти для метода <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> и при попытке вычисления этим методом хэш\-кодов очень больших строк \(длиной свыше нескольких миллионов символов\) может быть создано исключение <xref:System.ArgumentException>. Добавив этот элемент в файл конфигурации приложения и присвоив его атрибуту `enabled` значение "1", можно определить, что метод <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> использует другой алгоритм, который выделяет для вычисления хэш\-кодов постоянный объем памяти.  
  
> [!IMPORTANT]
>  В `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` и более поздних версиях элемент [!INCLUDE[win8](../../../../../includes/win8-md.md)] не используется.  
  
## См. также  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>   
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)