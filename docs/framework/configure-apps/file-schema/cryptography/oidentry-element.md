---
title: "Элемент &lt;oidEntry&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidEntry> - элемент"
  - "oidEntry - элемент"
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;oidEntry&gt;
Сопоставляет идентификатор объекта ASN.1 с понятным именем.  
  
## Синтаксис  
  
```  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**OID**|Обязательный атрибут.<br /><br /> Указывает идентификатор объекта ASN.1, соответствующий реализованному в классе алгоритму.|  
|**name**|Обязательный атрибут.<br /><br /> Задает значение атрибута **name** в теге [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`cryptographySettings`|Этот элемент содержит параметры криптографии.|  
|`mscorlib`|Содержит элемент `cryptographySettings`.|  
|`oidMap`|Содержит сопоставления идентификатора объекта ASN.1 с классами.|  
  
## Заметки  
 Идентификаторы объектов ASN.1 определяют алгоритмы в некоторых криптографических форматах.  Идентификаторы объектов сопоставляются с понятными именами для тех алгоритмов, которые необходимо определить.  Дополнительные сведения об идентификаторах объектов см. в библиотеке MSDN.  
  
## Пример  
 В следующем примере показан способ использования элемента **\<oidEntry\>** для сопоставления идентификатора объекта хэш\-алгоритма RIPEMD\-160 с реализацией этого алгоритма.  
  
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
 [Настройка криптографических классов](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)