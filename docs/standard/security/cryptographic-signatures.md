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
ms.openlocfilehash: 1de6b3f2eb30df270339910e7b8287101bde65ca
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706257"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="aa5e2-102">Криптографические подписи</span><span class="sxs-lookup"><span data-stu-id="aa5e2-102">Cryptographic Signatures</span></span>

<span data-ttu-id="aa5e2-103">Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="aa5e2-104">Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="aa5e2-105">Подробнее о цифровых подписях см. в разделе [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa5e2-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>

<span data-ttu-id="aa5e2-106">В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="aa5e2-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="aa5e2-107">Создание подписей</span><span class="sxs-lookup"><span data-stu-id="aa5e2-107">Generating Signatures</span></span>

<span data-ttu-id="aa5e2-108">Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="aa5e2-109">В примере ниже демонстрируется применение цифровой подписи к хэш-значению.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="aa5e2-110">Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> с целью формирования набора, состоящего из открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-110">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="aa5e2-111">Затем экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="aa5e2-111">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="aa5e2-112">При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="aa5e2-113">Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="aa5e2-114">В этом примере используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="aa5e2-115">Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="aa5e2-116">Из-за проблем с алгоритмом SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-116">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>

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

### <a name="signing-xml-files"></a><span data-ttu-id="aa5e2-117">Подписывание XML-файлов</span><span class="sxs-lookup"><span data-stu-id="aa5e2-117">Signing XML Files</span></span>

<span data-ttu-id="aa5e2-118">.NET Framework предоставляет пространство имен <xref:System.Security.Cryptography.Xml> , которое позволяет подписывать XML.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-118">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="aa5e2-119">Подписывание XML имеет важное значение в случае, если вы хотите убедиться в том, что XML-файл исходит от конкретного источника.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-119">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="aa5e2-120">Например, если вы пользуетесь службой котировки акций, которая использует XML, вы можете проверить источник XML-файла, если он подписан.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-120">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>

<span data-ttu-id="aa5e2-121">Классы в этом пространстве имен следуют рекомендации консорциума W3C относительно синтаксиса и обработки XML-подписей [XML-Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/) .</span><span class="sxs-lookup"><span data-stu-id="aa5e2-121">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>

## <a name="verifying-signatures"></a><span data-ttu-id="aa5e2-122">Проверка подписей</span><span class="sxs-lookup"><span data-stu-id="aa5e2-122">Verifying Signatures</span></span>

<span data-ttu-id="aa5e2-123">Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="aa5e2-123">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="aa5e2-124">открытый ключ стороны, подписавшей данные;</span><span class="sxs-lookup"><span data-stu-id="aa5e2-124">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="aa5e2-125">цифровая подпись;</span><span class="sxs-lookup"><span data-stu-id="aa5e2-125">The digital signature.</span></span>

- <span data-ttu-id="aa5e2-126">подписанные данные;</span><span class="sxs-lookup"><span data-stu-id="aa5e2-126">The data that was signed.</span></span>

- <span data-ttu-id="aa5e2-127">хэш-алгоритм, который использовался при создании подписи.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-127">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="aa5e2-128">Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="aa5e2-128">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="aa5e2-129">Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-129">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="aa5e2-130">Для указания открытого ключа нужно знать значения модуля и экспоненты.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-130">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="aa5e2-131">(Эти значения должны быть предоставлены стороной, создавшей пару открытого и закрытого ключей.) Сначала создайте объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> для хранения открытого ключа, который будет проверять подпись, а затем инициализирует структуру <xref:System.Security.Cryptography.RSAParameters> для значений модуля и экспоненты, задающих открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-131">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="aa5e2-132">В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="aa5e2-132">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="aa5e2-133">Свойству `Modulus` присваивается байтовый массив `modulusData` , а свойству `Exponent` — байтовый массив `exponentData`.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-133">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

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

<span data-ttu-id="aa5e2-134">После создания объекта <xref:System.Security.Cryptography.RSAParameters> можно инициализировать новый экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> значениями, указанными в <xref:System.Security.Cryptography.RSAParameters>.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-134">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="aa5e2-135">Экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> , в свою очередь, передается в конструктор класса <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-135">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="aa5e2-136">Этот процесс показан в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-136">The following example illustrates this process.</span></span> <span data-ttu-id="aa5e2-137">В этом коде `hashValue` и `signedHashValue` — байтовые массивы, предоставленные удаленной стороной.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-137">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="aa5e2-138">Удаленная сторона подписала объект `hashValue` с помощью алгоритма SHA1, создающего цифровую подпись `signedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-138">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="aa5e2-139">Метод <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> проверяет, является ли цифровая подпись допустимой и использовалась для подписывания `hashValue`.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-139">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

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

<span data-ttu-id="aa5e2-140">Если подпись действительна, этот фрагмент кода выдаст сообщение «`The signature is valid`», а в противном случае — сообщение «`The signature is not valid`».</span><span class="sxs-lookup"><span data-stu-id="aa5e2-140">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa5e2-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa5e2-141">See also</span></span>

- [<span data-ttu-id="aa5e2-142">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="aa5e2-142">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
