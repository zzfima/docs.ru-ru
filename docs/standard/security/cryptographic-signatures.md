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
ms.openlocfilehash: 3f9d83a0edb6dc2261931e422b0ae4c735d2e0d1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086100"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="6c9e5-102">Криптографические подписи</span><span class="sxs-lookup"><span data-stu-id="6c9e5-102">Cryptographic Signatures</span></span>
<a name="top"></a> <span data-ttu-id="6c9e5-103">Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="6c9e5-104">Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="6c9e5-105">Подробнее о цифровых подписях см. в разделе [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c9e5-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>  
  
 <span data-ttu-id="6c9e5-106">В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
-   [<span data-ttu-id="6c9e5-107">Создание подписей</span><span class="sxs-lookup"><span data-stu-id="6c9e5-107">Generating Signatures</span></span>](#generate)  
  
-   [<span data-ttu-id="6c9e5-108">Проверка подписей</span><span class="sxs-lookup"><span data-stu-id="6c9e5-108">Verifying Signatures</span></span>](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a><span data-ttu-id="6c9e5-109">Создание подписей</span><span class="sxs-lookup"><span data-stu-id="6c9e5-109">Generating Signatures</span></span>  
 <span data-ttu-id="6c9e5-110">Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="6c9e5-111">В примере ниже демонстрируется применение цифровой подписи к хэш-значению.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="6c9e5-112">Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> с целью формирования набора, состоящего из открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="6c9e5-113">Затем экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="6c9e5-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="6c9e5-114">При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="6c9e5-115">Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="6c9e5-116">В этом примере используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="6c9e5-117">Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>  
  
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
  
### <a name="signing-xml-files"></a><span data-ttu-id="6c9e5-118">Подписывание XML-файлов</span><span class="sxs-lookup"><span data-stu-id="6c9e5-118">Signing XML Files</span></span>  
 <span data-ttu-id="6c9e5-119">.NET Framework предоставляет пространство имен <xref:System.Security.Cryptography.Xml> , которое позволяет подписывать XML.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="6c9e5-120">Подписывание XML имеет важное значение в случае, если вы хотите убедиться в том, что XML-файл исходит от конкретного источника.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="6c9e5-121">Например, если вы пользуетесь службой котировки акций, которая использует XML, вы можете проверить источник XML-файла, если он подписан.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>  
  
 <span data-ttu-id="6c9e5-122">Классы в этом пространстве имен следуют [XML-Signature Syntax and Processing рекомендация](https://www.w3.org/TR/xmldsig-core/) из консорциума World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>  
  
 [<span data-ttu-id="6c9e5-123">К началу</span><span class="sxs-lookup"><span data-stu-id="6c9e5-123">Back to top</span></span>](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a><span data-ttu-id="6c9e5-124">Проверка подписей</span><span class="sxs-lookup"><span data-stu-id="6c9e5-124">Verifying Signatures</span></span>  
 <span data-ttu-id="6c9e5-125">Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="6c9e5-125">To verify that data was signed by a particular party, you must have the following information:</span></span>  
  
-   <span data-ttu-id="6c9e5-126">открытый ключ стороны, подписавшей данные;</span><span class="sxs-lookup"><span data-stu-id="6c9e5-126">The public key of the party that signed the data.</span></span>  
  
-   <span data-ttu-id="6c9e5-127">цифровая подпись;</span><span class="sxs-lookup"><span data-stu-id="6c9e5-127">The digital signature.</span></span>  
  
-   <span data-ttu-id="6c9e5-128">подписанные данные;</span><span class="sxs-lookup"><span data-stu-id="6c9e5-128">The data that was signed.</span></span>  
  
-   <span data-ttu-id="6c9e5-129">хэш-алгоритм, который использовался при создании подписи.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-129">The hash algorithm used by the signer.</span></span>  
  
 <span data-ttu-id="6c9e5-130">Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="6c9e5-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="6c9e5-131">Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="6c9e5-132">Для указания открытого ключа нужно знать значения модуля и экспоненты.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="6c9e5-133">(Эти значения должны быть предоставлены стороной, создавшей открытый и закрытый ключи.) Сначала создайте <xref:System.Security.Cryptography.RSACryptoServiceProvider> объекта, содержащего открытый ключ, который будет проверять подпись, а затем инициализируйте <xref:System.Security.Cryptography.RSAParameters> структуры значениями модуля и экспоненты, которые определяют открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>  
  
 <span data-ttu-id="6c9e5-134">В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="6c9e5-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="6c9e5-135">Свойству `Modulus` присваивается байтовый массив `ModulusData` , а свойству `Exponent` — байтовый массив `ExponentData`.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-135">The `Modulus` property is set to the value of a byte array called `ModulusData` and the `Exponent` property is set to the value of a byte array called `ExponentData`.</span></span>  
  
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
  
 <span data-ttu-id="6c9e5-136">После создания объекта <xref:System.Security.Cryptography.RSAParameters> можно инициализировать новый экземпляр класса <xref:System.Security.Cryptography.RSACryptoServiceProvider> значениями, указанными в <xref:System.Security.Cryptography.RSAParameters>.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="6c9e5-137">Экземпляр <xref:System.Security.Cryptography.RSACryptoServiceProvider> , в свою очередь, передается в конструктор класса <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>  
  
 <span data-ttu-id="6c9e5-138">Этот процесс показан в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-138">The following example illustrates this process.</span></span> <span data-ttu-id="6c9e5-139">В этом коде `HashValue` и `SignedHashValue` — байтовые массивы, предоставленные удаленной стороной.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-139">In this example, `HashValue` and `SignedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="6c9e5-140">Удаленная сторона подписала объект `HashValue` с помощью алгоритма SHA1, создающего цифровую подпись `SignedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-140">The remote party has signed the `HashValue` using the SHA1 algorithm, producing the digital signature `SignedHashValue`.</span></span> <span data-ttu-id="6c9e5-141">Классу</span><span class="sxs-lookup"><span data-stu-id="6c9e5-141">The</span></span>  
  
 <span data-ttu-id="6c9e5-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> проверяет допустимость цифровой подписи, используемой для подписания объекта `HashValue`.</span><span class="sxs-lookup"><span data-stu-id="6c9e5-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `HashValue`.</span></span>  
  
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
  
 <span data-ttu-id="6c9e5-143">Если подпись действительна, этот фрагмент кода выдаст сообщение «`The signature is valid`», а в противном случае — сообщение «`The signature is not valid`».</span><span class="sxs-lookup"><span data-stu-id="6c9e5-143">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9e5-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6c9e5-144">See also</span></span>

- [<span data-ttu-id="6c9e5-145">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6c9e5-145">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
