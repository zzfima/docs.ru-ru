---
title: Криптографические подписи
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de64af1a4617af39b0ef8e054292a402d6a145e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350460"
---
# <a name="cryptographic-signatures"></a>Криптографические подписи

Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных. Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания. Подробнее о цифровых подписях см. в разделе [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).

В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType> .

## <a name="generating-signatures"></a>Создание подписей

Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера. В примере ниже демонстрируется применение цифровой подписи к хэш-значению. Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> с целью формирования набора, состоящего из открытого и закрытого ключей. Затем экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись. Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм. В этом примере используется алгоритм SHA1. Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.

Due to collision problems with SHA1, Microsoft recommends SHA256 or better.

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As New RSACryptoServiceProvider()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSACryptoServiceProvider to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
    End Sub
End Module
```

```csharp
using System;
using System.Security.Cryptography;

class Class1
{
   static void Main()
   {
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSACryptoServiceProvider to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

### <a name="signing-xml-files"></a>Подписывание XML-файлов

.NET Framework предоставляет пространство имен <xref:System.Security.Cryptography.Xml> , которое позволяет подписывать XML. Подписывание XML имеет важное значение в случае, если вы хотите убедиться в том, что XML-файл исходит от конкретного источника. Например, если вы пользуетесь службой котировки акций, которая использует XML, вы можете проверить источник XML-файла, если он подписан.

Классы в этом пространстве имен следуют рекомендации консорциума W3C относительно синтаксиса и обработки XML-подписей [XML-Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/) .

## <a name="verifying-signatures"></a>Проверка подписей

Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:

- открытый ключ стороны, подписавшей данные;

- цифровая подпись;

- подписанные данные;

- хэш-алгоритм, который использовался при создании подписи.

Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны. Для указания открытого ключа нужно знать значения модуля и экспоненты. (The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.

В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> . Свойству `Modulus` присваивается байтовый массив `modulusData` , а свойству `Exponent` — байтовый массив `exponentData`.

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

После создания объекта <xref:System.Security.Cryptography.RSAParameters> можно инициализировать новый экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> значениями, указанными в <xref:System.Security.Cryptography.RSAParameters>. Экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> , в свою очередь, передается в конструктор класса <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.

Этот процесс показан в приведенном ниже примере. В этом коде `hashValue` и `signedHashValue` — байтовые массивы, предоставленные удаленной стороной. Удаленная сторона подписала объект `hashValue` с помощью алгоритма SHA1, создающего цифровую подпись `signedHashValue`. The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.

```vb
Dim rsa As New RSACryptoServiceProvider()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

Если подпись действительна, этот фрагмент кода выдаст сообщение «`The signature is valid`», а в противном случае — сообщение «`The signature is not valid`».

## <a name="see-also"></a>См. также

- [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)
