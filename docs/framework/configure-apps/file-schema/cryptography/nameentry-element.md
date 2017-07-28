---
title: "Элемент &lt;nameEntry&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<nameEntry> - элемент"
  - "nameEntry - элемент"
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Элемент &lt;nameEntry&gt;
Сопоставление имени класса с понятным именем алгоритма, позволяющим одному классу иметь несколько понятных имен.  
  
## Синтаксис  
  
```  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**name**|Обязательный атрибут.<br /><br /> Задание понятного имени алгоритма, реализуемого в криптографическом классе.|  
|**класс**|Обязательный атрибут.<br /><br /> Задание значение для атрибута **name** в элементе [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md).|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`system.web`|Определяет корневой элемент для раздела конфигурации ASP.NET.|  
  
## Заметки  
 Атрибут **name** может представлять собой имя одного из абстрактных классов пространства имен <xref:System.Security.Cryptography>.  При вызове метода **Create** для абстрактного криптографического класса имя абстрактного класса передается в метод [Security.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic).  **CreateFromName** возвращает экземпляр типа, указанный с помощью атрибута **class**.  Если в атрибуте **name** содержится краткое имя \(например, RSA\), это имя можно использовать при вызове метода **CreateFromName**.  
  
## Пример  
 В следующем примере показано, как использовать элемент **\<nameEntry\>** для создания ссылки на криптографический класс и конфигурирования среды выполнения.  В этом случае можно передать строку "RSA" в метод <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> и использовать метод <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> для получения объекта `MyCryptoRSAClass`.  
  
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