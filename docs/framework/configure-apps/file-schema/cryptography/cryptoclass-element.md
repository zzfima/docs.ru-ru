---
title: "Элемент &lt;cryptoClass&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoClass> - элемент"
  - "cryptoClass - элемент"
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Элемент &lt;cryptoClass&gt;
Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).  
  
## Синтаксис  
  
```  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`customClassName`|Обязательный атрибут.<br /><br /> Содержит данные для криптографического класса.  Этот атрибут используется для предоставления краткого имени класса.  Можно задавать любую строку, отвечающую требованиям, описанным в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`cryptoClasses`|Содержит список криптографических классов, сопоставленных с понятными именами, указанным в элементе [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).|  
|`cryptographySettings`|Этот элемент содержит параметры криптографии.|  
|`cryptoNameMapping`|Сопоставление классов с понятными именами.|  
|`mscorlib`|Содержит элемент [\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).|  
  
## Пример  
 В следующем примере показано, как использовать элемент **\<cryptoClass\>**, чтобы ссылаться на криптографический класс и конфигурировать среду выполнения.  В этом случае можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для получения объекта `MyCryptoRSAClass`.  
  
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