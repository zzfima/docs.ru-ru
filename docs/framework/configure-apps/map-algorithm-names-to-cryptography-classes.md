---
title: Отображение имен алгоритмов на криптографические классы
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912866"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Отображение имен алгоритмов на криптографические классы
Существует четыре способа, с помощью которых разработчик может создать криптографический объект, используя Windows SDK:  
  
- Создайте объект с помощью оператора **New** .  
  
- Создайте объект, реализующий определенный алгоритм шифрования, вызвав метод **CREATE** для абстрактного класса для этого алгоритма.  
  
- Создайте объект, реализующий определенный алгоритм шифрования, вызвав <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.  
  
- Создайте объект, реализующий класс криптографических алгоритмов (например, симметричный блочный шифр), вызвав метод **CREATE** абстрактного класса для этого типа алгоритма (например, <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Например, предположим, что разработчик хочет вычислить хэш SHA1 набора байтов. <xref:System.Security.Cryptography> Пространство имен содержит две реализации алгоритма SHA1, одну исключительно управляемую реализацию и одну оболочку CryptoAPI. Разработчик может выбрать создание экземпляра конкретной реализации SHA1 (например, <xref:System.Security.Cryptography.SHA1Managed>), вызвав оператор **New** . Однако если не имеет значения, какой класс загружает общеязыковая среда выполнения, пока класс реализует хэш-алгоритм SHA1, разработчик может создать объект, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод. Этот метод вызывает **System. Security. Cryptography. CryptoConfig. CreateFromName («System. Security. Cryptography. SHA1»)** , который должен возвращать реализацию алгоритма хэширования SHA1.  
  
 Разработчик также может вызвать **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** , так как по умолчанию конфигурация криптографии включает короткие имена для алгоритмов, поставляемых в .NET Framework.  
  
 Если не имеет значения, какой алгоритм хэширования используется, разработчик может вызвать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий преобразование хэширования.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Сопоставление имен алгоритмов в файлах конфигурации  
 По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объект для всех четырех сценариев. Однако администратор компьютера может изменить тип объекта, возвращаемый методами в двух последних сценариях. Для этого необходимо связать понятное имя алгоритма с классом, который вы хотите использовать в файле конфигурации компьютера (Machine. config).  
  
 В следующем примере показано, как настроить среду выполнения таким образом, чтобы **система System. Security. криптографически. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** и **System. Security. Cryptography. HashAlgorithm. Create Возврат объекта.** `MySHA1HashClass`  
  
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
  
 Имя атрибута можно указать в [элементе < cryptoClass\> ](./file-schema/cryptography/cryptoclass-element.md) (в предыдущем примере имя атрибута `MySHA1Hash`). Значением атрибута в  **\<элементе > cryptoClass** является строка, которую среда CLR использует для поиска класса. Можно использовать любую строку, которая соответствует требованиям, указанным в указании [полных имен типов](../reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Многие имена алгоритмов могут сопоставляться с одним и тем же классом. Элемент элементе nameentry > сопоставляет класс с одним понятным именем алгоритма. [ \<](./file-schema/cryptography/nameentry-element.md) Атрибут **Name** может быть либо строкой, используемой при вызове метода **System. Security. Cryptography. CryptoConfig. CreateFromName** , либо именем абстрактного криптографического <xref:System.Security.Cryptography> класса в пространстве имен. Значением атрибута **Class** является имя атрибута в  **\<элементе > cryptoClass** .  
  
> [!NOTE]
> Алгоритм SHA1 можно получить, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод или **Security. CryptoConfig. CreateFromName ("SHA1")** . Каждый метод гарантирует только то, что он возвращает объект, реализующий алгоритм SHA1. Нет необходимости сопоставлять каждое понятное имя алгоритма с тем же классом в файле конфигурации.  
  
 Список имен по умолчанию и классов, с которыми они сопоставляются, <xref:System.Security.Cryptography.CryptoConfig>см. в разделе.  
  
## <a name="see-also"></a>См. также

- [Cryptographic Services](../../standard/security/cryptographic-services.md)
- [Настройка криптографических классов](configure-cryptography-classes.md)
