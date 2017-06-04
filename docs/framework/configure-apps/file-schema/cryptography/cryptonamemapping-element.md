---
title: "Элемент &lt;cryptoNameMapping&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoNameMapping> - элемент"
  - "cryptoNameMapping - элемент"
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Элемент &lt;cryptoNameMapping&gt;
Сопоставление классов с понятными именами.  
  
## Синтаксис  
  
```  
  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`cryptoClasses`|Содержит список криптографических классов, сопоставленных с понятными именами, указанным в элементе **\<nameEntry\>**.|  
|`nameEntry`|Сопоставление имени класса с понятным именем алгоритма, позволяющим одному классу иметь несколько понятных имен.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`cryptographySettings`|Этот элемент содержит параметры криптографии.|  
|`cryptoNameMapping`|Сопоставление классов с понятными именами.|  
|`mscorlib`|Содержит элемент \<cryptographySettings\>.|  
  
## Пример  
 В следующем примере показано, как использовать элемент **\<cryptoNameMapping\>** для создания ссылки на криптографический класс и конфигурирования среды выполнения.  В этом случае можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для получения объекта `MyCryptoRSAClass`.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## См. также  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Схема параметров криптографии](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Службы криптографии](../../../../../docs/standard/security/cryptographic-services.md)   
 [Настройка криптографических классов](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)