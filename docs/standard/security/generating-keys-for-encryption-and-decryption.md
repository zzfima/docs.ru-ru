---
title: Создание ключей для шифрования и расшифровки
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 88d8dac83c3d5bf267ed90ffb313cd9e24b42dea
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706192"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Создание ключей для шифрования и расшифровки
Создание ключей и управление ими — это важная часть процесса шифрования. Симметричные алгоритмы требуют создания ключа и вектора инициализации (IV). Ключ следует хранить в тайне от любого, кто не должен расшифровывать ваши данные. Вектор инициализации может не быть секретным, но должен изменяться для каждого сеанса. Асимметричные алгоритмы требуют создания открытого ключа и закрытого ключа. Открытый ключ можно предоставлять кому угодно, а закрытый ключ должен быть известен только той стороне, которая будет расшифровывать данные, зашифрованные при помощи открытого ключа. В этом разделе описывается создание ключей и управление ими для симметричных и асимметричных алгоритмов.  
  
## <a name="symmetric-keys"></a>Симметричные ключи  
 Классы симметричного шифрования, предоставляемые платформой .NET Framework, требуют ключ и новый вектор инициализации (IV) для шифрования и расшифровки данных. При создании нового экземпляра одного из управляемых симметричных криптографических классов с помощью конструктора без параметров автоматически создаются новые ключ и вектор инициализации. Все пользователи, которым вы разрешаете расшифровывать свои данные, должны иметь тот же ключ и вектора инициализации и использовать тот же алгоритм. Как правило, новый ключ и вектор инициализации должны создаваться для каждого сеанса, и ни вектор инициализации, ни ключ нельзя сохранять для использования в следующем сеансе.  
  
 При передаче симметричного ключа и вектора инициализации на удаленную сторону симметричный ключ обычно шифруется с помощью асимметричного шифрования. Отправка ключа через незащищенную сеть без шифрования небезопасна, так как любой, кто перехватит ключ и вектор инициализации, сможет расшифровать данные. Дополнительные сведения об обмене данными с помощью шифрования см. в разделе [Создание криптографической схемы](../../../docs/standard/security/creating-a-cryptographic-scheme.md).  
  
 В следующем примере показано создание нового экземпляра класса <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> , реализующего алгоритм TripleDES.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 При выполнении предыдущего кода осуществляется создание нового ключа и вектора инициализации и их помещение в свойства **Key** и **IV** соответственно.  
  
 Иногда может понадобиться создать несколько ключей. В этом случае можно создать новый экземпляр класса, реализующий симметричный алгоритм, а затем создать новый ключ и вектор инициализации, вызвав методы **GenerateKey** и **GenerateIV** . В следующем примере кода показано, как создать новые ключи и IVs после внесения нового экземпляра симметричного криптографического класса.  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 При выполнении предыдущего кода ключ и вектор инициализации формируются, когда создается новый экземпляр **TripleDESCryptoServiceProvider** . Другой ключ и вектор инициализации создаются при вызове методов **GenerateKey** и **GenerateIV** .  
  
## <a name="asymmetric-keys"></a>Асимметричные ключи  
 Платформа .NET Framework предоставляет классы <xref:System.Security.Cryptography.RSACryptoServiceProvider> и <xref:System.Security.Cryptography.DSACryptoServiceProvider> для асимметричного шифрования. Эти классы создают пару открытого и закрытого ключей при использовании конструктора без параметров для создания нового экземпляра. Асимметричные ключи можно сохранять для использования в нескольких сеансах или создавать только для отдельного сеанса. В то время как открытый ключ можно сделать общедоступным, закрытый ключ должен быть надежно защищен.  
  
 Пара из открытого и закрытого ключей создается каждый раз, когда создается новый экземпляр класса асимметричного алгоритма. После создания нового экземпляра класса сведения ключа можно извлечь при помощи одного из двух методов:  
  
- метод <xref:System.Security.Cryptography.RSA.ToXmlString%2A> , возвращающий XML-представление сведений ключа;  
  
- метод <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> , возвращающий структуру <xref:System.Security.Cryptography.RSAParameters> , которая содержит сведения ключа.  
  
 Оба метода принимают логическое значение, указывающее, следует ли возвращать только сведения об открытом ключе или сведения как об открытом, так и о закрытом ключе. Класс **RSACryptoServiceProvider** можно инициализировать значением структуры **RSAParameters** при помощи метода <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> .  
  
 Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере. Если необходимо хранить закрытый ключ, следует использовать для этого контейнер ключа. Дополнительные сведения о хранении закрытого ключа в контейнере ключей см. в разделе [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 Следующий пример кода создает новый экземпляр класса **RSACryptoServiceProvider** посредством создания пары из открытого и закрытого ключей и сохраняет сведения об открытом ключе в структуре **RSAParameters** .  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a>См. также:

- [Шифрование данных](../../../docs/standard/security/encrypting-data.md)
- [Расшифровка данных](../../../docs/standard/security/decrypting-data.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
- [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)
