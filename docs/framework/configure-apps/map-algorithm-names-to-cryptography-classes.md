---
title: Отображение имен алгоритмов на криптографические классы
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2dc03c3aa6808ed4ce0c22f4e69fa8c98cb7aebd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Отображение имен алгоритмов на криптографические классы
Существует четыре способа создания криптографического объекта с помощью [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Создание объекта с помощью **новый** оператор.  
  
-   Создание объекта, реализующего конкретный криптографический алгоритм с помощью метода **создать** метод к абстрактному классу данного алгоритма.  
  
-   Создание объекта, реализующего конкретный криптографический алгоритм с помощью метода <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.  
  
-   Создание объекта, реализующего класс алгоритмов шифрования (например, симметричный блочный шифр) с помощью метода **создать** метод абстрактного класса для этого типа алгоритма (например, <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Например предположим, что разработчику нужно вычислить хэш SHA1 набора байтов. <xref:System.Security.Cryptography> Пространство имен содержит две реализации алгоритма SHA1, одна реализация полностью управляемые и один, который упаковывает CryptoAPI. Разработчик может использовать для создания экземпляра конкретной реализации SHA1 (такие как <xref:System.Security.Cryptography.SHA1Managed>) путем вызова **новый** оператор. Тем не менее, если он не имеет значения, какой класс общеязыковая среда выполнения загружает при условии, что класс реализует хэш-алгоритмом SHA1, разработчик может создать объект путем вызова <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод. Этот метод вызывает метод **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, который должен вернуть реализацию хэш-алгоритмом SHA1.  
  
 Разработчик также может вызывать **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** так, как по умолчанию конфигурации шифрования включает в себя короткие имена для алгоритмов, поставляется в .NET Framework.  
  
 Если он не имеет значения, используется алгоритм хеширования, разработчик может вызывать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий интерфейс хэширования преобразования.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Сопоставление имен алгоритмов в файлах конфигурации  
 По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объекта для всех четырех сценариев. Тем не менее администратор компьютера может изменить тип объекта, возвращаемые методами в двух последних случаях. Чтобы сделать это, необходимо сопоставить с понятным именем алгоритма класса, который будет использоваться в файле конфигурации компьютера (Machine.config).  
  
 В следующем примере показано, как настройки среды выполнения, чтобы **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, и  **System.Security.Cryptography.HashAlgorithm.Create** возвращают `MySHA1HashClass` объекта.  
  
```xml  
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
  
 Можно указать имя атрибута в [< cryptoClass\> элемент](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (предыдущий пример имена атрибут `MySHA1Hash`). Значение атрибута в  **\<cryptoClass >** элемент представляет собой строку, общеязыковая среда выполнения использует для поиска класса. Можно использовать любую строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Много имен алгоритмов можно сопоставить с того же класса. [ \<NameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма. **Имя** атрибута может быть либо строка, используемая при вызове **System.Security.Cryptography.CryptoConfig.CreateFromName** метода или имени класса абстрактный шифрования в <xref:System.Security.Cryptography> пространства имен. Значение **класса** атрибут — это имя атрибута в  **\<cryptoClass >** элемента.  
  
> [!NOTE]
>  Алгоритм SHA1 можно получить, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> или **Security.CryptoConfig.CreateFromName("SHA1")** метод. Каждый метод гарантирует только то, что он возвращает объект, реализующий алгоритм SHA1. Необходимо сопоставить каждое понятное имя алгоритма в тот же класс в файле конфигурации.  
  
 Список имен по умолчанию и классы, они сопоставляются. в разделе <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>См. также  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
