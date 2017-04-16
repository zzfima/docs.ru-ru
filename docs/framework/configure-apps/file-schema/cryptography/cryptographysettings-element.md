---
title: "Элемент &lt;cryptographySettings&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptographySettings> - элемент"
  - "cryptographySettings - элемент"
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Элемент &lt;cryptographySettings&gt;
Этот элемент содержит параметры криптографии.  
  
## Синтаксис  
  
```  
  
      <cryptographySettings>   
</crytopgraphySettings>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<cryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Сопоставление классов с понятными именами.|  
|[\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Содержит сопоставления идентификатора объекта ASN.1 с классами.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`mscorlib`|Содержит элемент `cryptographySettings`.|  
  
## Пример  
 В следующем примере показан способ включения в элемент **\<cryptographySettings\>** сопоставлений криптографических имен и сопоставлений идентификаторов объектов.  В этом примере настройка среды выполнения производится таким образом, что [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic) возвращает объект `MyHashClass` и класс `MyCryptoClass` сопоставляется с идентификатором 1.3.36.2.1 объекта.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Схема параметров криптографии](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Службы криптографии](../../../../../docs/standard/security/cryptographic-services.md)