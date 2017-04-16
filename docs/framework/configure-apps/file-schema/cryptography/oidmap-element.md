---
title: "Элемент &lt;oidMap&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidMap> - элемент"
  - "oidMap - элемент"
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;oidMap&gt;
Содержит сопоставления идентификатора объекта ASN.1 с классами.  
  
## Синтаксис  
  
```  
<oidMap>   
</oidMap>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Сопоставление идентификатора объекта ASN.1 с понятным именем.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`cryptographySettings`|Этот элемент содержит параметры криптографии.|  
|`mscorlib`|Содержит элемент `cryptographySettings` .|  
  
## Пример  
 В следующем примере показан способ использования элемента **\<oidMap\>** для сопоставления идентификатора объекта хэш\-алгоритма RIPEMD\-160 с реализацией этого алгоритма.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Схема параметров криптографии](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Службы криптографии](../../../../../docs/standard/security/cryptographic-services.md)   
 [Настройка криптографических классов](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)