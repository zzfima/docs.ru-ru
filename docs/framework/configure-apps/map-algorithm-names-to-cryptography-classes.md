---
title: Отображение имен алгоритмов на криптографические классы
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 6bf6e79923f0b3119c516ed97e0e86971368a34c
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083665"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Отображение имен алгоритмов на криптографические классы
Существует четыре способа создания криптографического объекта с помощью [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Создание объекта с помощью **новый** оператор.  
  
-   Создайте объект, реализующий конкретный криптографический алгоритм, вызвав **создать** метод к абстрактному классу данного алгоритма.  
  
-   Создайте объект, реализующий конкретный криптографический алгоритм, вызвав <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.  
  
-   Создание объекта, реализующего класс алгоритмов шифрования (например, симметричный блочный шифр) путем вызова **создать** метод на абстрактный класс для этого типа алгоритма (такие как <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Например предположим, что разработчику нужно вычислить хэш SHA1 набора байтов. <xref:System.Security.Cryptography> Пространство имен содержит две реализации алгоритма SHA1, одну реализацию полностью управляемыми и тот, который создает оболочку для CryptoAPI. Разработчик может выбрать для создания экземпляра конкретной реализации SHA1 (такие как <xref:System.Security.Cryptography.SHA1Managed>) путем вызова **новый** оператор. Тем не менее, если он не имеет значения, какой класс, среда CLR загружает до тех пор, пока этот класс реализует хэш-алгоритм SHA1, разработчик может создать объект путем вызова <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод. Этот метод вызывает метод **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, который должен возвращать реализацию алгоритма хэширования SHA1.  
  
 Разработчик также может вызвать **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** так, как по умолчанию конфигурации шифрования включает в себя короткие имена для алгоритмов, в .NET Framework.  
  
 Если это неважно, используется алгоритм хеширования, разработчик может вызвать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий интерфейс хэширования преобразования.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Отображение имен алгоритмов в файлах конфигурации  
 По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объекта для всех четырех сценариев. Тем не менее администратор компьютера можно изменить тип объекта, которое возвращают методы в последних двух сценариях. Чтобы сделать это, необходимо сопоставить с понятным именем алгоритма к классу, который вы хотите использовать в файле конфигурации компьютера (Machine.config).  
  
 В следующем примере показано, как настроить среду выполнения, чтобы **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, и  **System.Security.Cryptography.HashAlgorithm.Create** возвращают `MySHA1HashClass` объекта.  
  
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
  
 Можно указать имя атрибута в [< cryptoClass\> элемент](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (предыдущий пример имен атрибута `MySHA1Hash`). Значение атрибута в  **\<cryptoClass >** элемент представляет собой строку, среда CLR использует для поиска класса. Можно использовать любую строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Многие имена алгоритмов можно сопоставить с того же класса. [ \<NameEntry > элемент](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма. **Имя** атрибут может быть либо строкой, которая используется при вызове **System.Security.Cryptography.CryptoConfig.CreateFromName** метода или имени класса абстрактный криптографии в <xref:System.Security.Cryptography> пространства имен. Значение **класс** атрибут — это имя атрибута в  **\<cryptoClass >** элемент.  
  
> [!NOTE]
>  Вы можете получить алгоритм SHA1, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> или **Security.CryptoConfig.CreateFromName("SHA1")** метод. Каждый метод только гарантирует, что он возвращает объект, реализующий алгоритм SHA1. Необходимо сопоставить каждый понятное имя алгоритма в тот же класс в файле конфигурации.  
  
 Список имен по умолчанию и классы, они сопоставляются, см. в разделе <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>См. также
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
- [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
