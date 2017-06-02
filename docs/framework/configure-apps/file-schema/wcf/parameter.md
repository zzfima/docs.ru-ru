---
title: "&lt;параметр&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;параметр&gt;
Указывает общий параметр, если объявленный тип является общим типом.  
  
## Синтаксис  
  
```  
  
<parameter index="integer"  
                      type=String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|индекс|Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.|  
|тип|Строка, которая описывает известный тип, используемый для сериализации и десериализации.|  
  
## Атрибут index  
  
|Значение|Описание|  
|--------------|--------------|  
|"0"|Первый параметр в общем типе.  Например, у <xref:System.Collections.Generic.List%601> есть только один параметр.  Если он используется как объявленный тип, индексу присваивается значение 0.|  
|"1"|Второй параметр в общем типе.  Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра.  Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Указывает известный тип, который может возвращаться полем или свойством объявленного типа.|  
  
## Заметки  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] известных типах\[см. в разделах [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Пример использования этого элемента см. в разделе [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
 У данного элемента конфигурации не может одновременно быть оба атрибута.  Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)