---
title: "Отображение имен алгоритмов на криптографические классы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "криптографические алгоритмы"
  - "шифрование, сопоставление имен алгоритмов"
  - "сопоставление имен алгоритмов"
  - "имена [платформа .NET Framework], сопоставление алгоритмов"
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Отображение имен алгоритмов на криптографические классы
Существует четыре способа создания криптографического объекта с помощью [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   создание объекта с помощью оператора **new**;  
  
-   создание объекта, реализующего конкретный криптографический алгоритм, с помощью метода **Create**, относящегося к абстрактному классу данного алгоритма;  
  
-   создание объекта, реализующего конкретный алгоритм шифрования, с помощью метода [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic);  
  
-   создание объекта, реализующего класс алгоритмов шифрования \(например, симметричный блочный шифр\) с помощью метода **Create** , относящегося к абстрактному классу алгоритмов данного типа \(например, <xref:System.Security.Cryptography.SymmetricAlgorithm>\).  
  
 Предположим, что разработчику нужно вычислить хэш\-код SHA1 для набора байтов.  Пространство имен <xref:System.Security.Cryptography> содержит две реализации алгоритма SHA1: одна — полностью управляемая реализация, другая оборачивает CryptoAPI.  Разработчик может создать экземпляр конкретной реализации SHA1 \(например, [SHA1Managed class](frlrfSystemSecurityCryptographySHA1ManagedClassTopic)\) с помощью оператора **new**.  Однако если не имеет значения, какой класс загружается средой CLR в процессе реализации классом хэш\-алгоритма SHA1, объект можно создать, вызвав метод [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic).  Этот метод вызывает метод **System.Security.Cryptography.CryptoConfig.CreateFromName\("System.Security.Cryptography.SHA1"\)**, который возвращает реализацию хэш\-алгоритма SHA1.  
  
 Разработчик может также вызвать **System.Security.Cryptography.CryptoConfig.CreateFromName\("SHA1"\)**, поскольку по умолчанию конфигурация шифрования включает короткие имена для алгоритмов, поставляемых в комплекте .NET Framework.  
  
 Если используется произвольный хэш\-алгоритм, разработчик может вызвать метод [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic), возвращающий объект, реализующий преобразование хэширования.  
  
## Сопоставление имен алгоритмов в файлах конфигурации  
 По умолчанию среда выполнения возвращает объект [System.Security.Cryptography.SHA1CryptoServiceProvider class](frlrfSystemSecurityCryptographySHA1CryptoServiceProviderClassTopic) во всех четырех сценариях.  Однако в последних двух сценариях администратор компьютера может изменить тип возвращаемого этими методами объекта.  Для этого необходимо сопоставить понятное имя алгоритма с классом, используемым в файле конфигурации компьютера \(Machine.config\).  
  
 В следующем примере показана настройка среды выполнения таким образом, чтобы методы **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName\("SHA1"\)** и **System.Security.Cryptography.HashAlgorithm.Create** возвращали объект `MySHA1HashClass`.  
  
```  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 Имя атрибута можно задать в элементе [\<cryptoClass\>](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) \(в предыдущем примере атрибут имел имя `MySHA1Hash`\).  Значением атрибута в элементе **\<cryptoClass\>** является строка, используемая средой CLR для поиска класса.  Можно использовать любую строку, отвечающую требованиям, описанным в разделе [Указание полных имен типов](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 С одним классом может быть сопоставлено много имен алгоритмов.  Элемент [\<nameEntry\> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма.  Атрибут **name** может быть либо строкой, используемой при вызове метода **System.Security.Cryptography.CryptoConfig.CreateFromName**, либо именем абстрактного криптографического класса в пространстве имен <xref:System.Security.Cryptography>.  Значением атрибута **class** является имя атрибута в элементе **\<cryptoClass\>**.  
  
> [!NOTE]
>  Алгоритм SHA1 можно получить с помощью метода [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic) или метода **Security.CryptoConfig.CreateFromName\("SHA1"\)**.  Каждый метод возвращает только объект, реализующий алгоритм SHA1.  Нет необходимости сопоставлять каждое понятное имя алгоритма с одним и тем же классом в файле конфигурации.  
  
 Список имен по умолчанию, а также сопоставляемых с ними классов см. в классе [CryptoConfig](frlrfSystemSecurityCryptographyCryptoConfigClassTopic).  
  
## См. также  
 [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)   
 [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)