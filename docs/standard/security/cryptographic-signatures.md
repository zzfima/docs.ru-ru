---
title: "Криптографические подписи"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 866d31662b8ae7d5c887af7d86007cb93a57d88f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="cryptographic-signatures"></a>Криптографические подписи
<a name="top"></a> Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных. Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания. Подробнее о цифровых подписях см. в разделе [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).  
  
 В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType>.  
  
-   [Создание подписей](#generate)  
  
-   [Проверка подписей](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a>Создание подписей  
 Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера. В примере ниже демонстрируется применение цифровой подписи к хэш-значению. Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> с целью формирования набора, состоящего из открытого и закрытого ключей. Затем экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись. Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм. В этом примере используется алгоритм SHA1. Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a>Подписывание XML-файлов  
 .NET Framework предоставляет пространство имен <xref:System.Security.Cryptography.Xml> , которое позволяет подписывать XML. Подписывание XML имеет важное значение в случае, если вы хотите убедиться в том, что XML-файл исходит от конкретного источника. Например, если вы пользуетесь службой котировки акций, которая использует XML, вы можете проверить источник XML-файла, если он подписан.  
  
 Классы в этом пространстве имен следуют рекомендации консорциума W3C относительно синтаксиса и обработки XML-подписей [XML-Signature Syntax and Processing](http://go.microsoft.com/fwlink/?LinkId=136777) .  
  
 [К началу](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a>Проверка подписей  
 Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:  
  
-   открытый ключ стороны, подписавшей данные;  
  
-   цифровая подпись;  
  
-   подписанные данные;  
  
-   хэш-алгоритм, который использовался при создании подписи.  
  
 Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны. Для указания открытого ключа нужно знать значения модуля и экспоненты. (Эти значения должны быть предоставлены стороной, создавшей открытый и закрытый ключи.) Сначала создайте <xref:System.Security.Cryptography.RSACryptoServiceProvider> объекта, содержащего открытый ключ, который проверки подписи, а затем инициализируйте <xref:System.Security.Cryptography.RSAParameters> структуры значениями модуля и экспоненты, которые определяют открытый ключ.  
  
 В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> . Свойству `Modulus` присваивается байтовый массив `ModulusData` , а свойству `Exponent` — байтовый массив `ExponentData`.  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 После создания объекта <xref:System.Security.Cryptography.RSAParameters> можно инициализировать новый экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> значениями, указанными в <xref:System.Security.Cryptography.RSAParameters>. Экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> , в свою очередь, передается в конструктор класса <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.  
  
 Этот процесс показан в приведенном ниже примере. В этом коде `HashValue` и `SignedHashValue` — байтовые массивы, предоставленные удаленной стороной. Удаленная сторона подписала объект `HashValue` с помощью алгоритма SHA1, создающего цифровую подпись `SignedHashValue`. Классу  
  
 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> проверяет допустимость цифровой подписи, используемой для подписания объекта `HashValue`.  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
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
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
