---
title: Практическое руководство. Шифрование XML-элементов с помощью симметричного ключа
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET Framework], symmetric keys
- encryption [.NET Framework], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Advanced Encryption Standard algorithm
- Rijndael
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b792fd6eea0a33b0143fafa03641a78947d7e127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458070"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="118ec-102">Практическое руководство. Шифрование XML-элементов с помощью симметричного ключа</span><span class="sxs-lookup"><span data-stu-id="118ec-102">How to: Encrypt XML Elements with Symmetric Keys</span></span>
<span data-ttu-id="118ec-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="118ec-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="118ec-104">Шифрование XML-данных позволяет хранить или передавать важные XML-данные, не беспокоясь о том, что они могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="118ec-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="118ec-105">Эта процедура шифрует XML-элемент с помощью алгоритма AES (AES), также известного как Rijndael.</span><span class="sxs-lookup"><span data-stu-id="118ec-105">This procedure encrypts an XML element using the Advanced Encryption Standard (AES) algorithm, also known as Rijndael.</span></span>  
  
 <span data-ttu-id="118ec-106">Дополнительные сведения о расшифровке XML-элемента, который был зашифрован с помощью этой процедуры, см. [в разделе как расшифровывать XML-элементы с симметричными ключами](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="118ec-106">For information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Symmetric Keys](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="118ec-107">При использовании симметричного алгоритма, такого как AES, для шифрования XML-данных необходимо использовать один и тот же ключ как для шифрования, так и для расшифровки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="118ec-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="118ec-108">В этом примере предполагается, что зашифрованные XML-данные будут расшифровываться при помощи того же ключа и что стороны, выполняющие шифрование и расшифровку, согласуют между собой используемый алгоритм и ключ.</span><span class="sxs-lookup"><span data-stu-id="118ec-108">The example in this procedure assumes that the encrypted XML will be decrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="118ec-109">В этом примере ключ AES не сохраняется и не шифруется внутри зашифрованного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="118ec-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="118ec-110">Этот пример подходит для ситуаций, где отдельному приложению требуется зашифровать данные на основе хранящегося в памяти сеансового ключа или на основе криптографически стойкого ключа, полученного из пароля.</span><span class="sxs-lookup"><span data-stu-id="118ec-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="118ec-111">В ситуациях, когда два приложения и более нуждаются в общем доступе к зашифрованным XML-данным, рекомендуется использовать схему шифрования, основанную на асимметричном алгоритме или сертификате X.509.</span><span class="sxs-lookup"><span data-stu-id="118ec-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="118ec-112">Шифрование XML-элемента при помощи симметричного ключа</span><span class="sxs-lookup"><span data-stu-id="118ec-112">To encrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="118ec-113">Создайте симметричный ключ, используя класс <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="118ec-113">Generate a symmetric key using the <xref:System.Security.Cryptography.RijndaelManaged> class.</span></span>  <span data-ttu-id="118ec-114">Этот ключ будет использоваться для шифрования XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="118ec-114">This key will be used to encrypt the XML element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="118ec-115">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="118ec-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="118ec-116">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="118ec-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="118ec-117">Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.</span><span class="sxs-lookup"><span data-stu-id="118ec-117">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="118ec-118">В этом примере выполняется шифрование элемента `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="118ec-118">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="118ec-119">Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования <xref:System.Xml.XmlElement> при помощи симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="118ec-119">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the <xref:System.Xml.XmlElement> with the symmetric key.</span></span>  <span data-ttu-id="118ec-120">Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> возвращает зашифрованный элемент в виде массива зашифрованных байт.</span><span class="sxs-lookup"><span data-stu-id="118ec-120">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="118ec-121">Создайте объект <xref:System.Security.Cryptography.Xml.EncryptedData> и заполните его идентификатором URL-адреса элемента XML-шифрования.</span><span class="sxs-lookup"><span data-stu-id="118ec-121">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the XML Encryption element.</span></span>  <span data-ttu-id="118ec-122">Этот идентификатор URL-адреса уведомляет сторону, выполняющую расшифровку, что XML-документ содержит зашифрованный элемент.</span><span class="sxs-lookup"><span data-stu-id="118ec-122">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="118ec-123">Для указания идентификатора URL-адреса можно использовать поле <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>.</span><span class="sxs-lookup"><span data-stu-id="118ec-123">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="118ec-124">Создайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod>, инициализируемый идентификатором URL-адреса криптографического алгоритма, который использовался для создания ключа.</span><span class="sxs-lookup"><span data-stu-id="118ec-124">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the key.</span></span>  <span data-ttu-id="118ec-125">Передайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod> в свойство <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="118ec-125">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="118ec-126">Добавьте зашифрованные данные элемента в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="118ec-126">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="118ec-127">Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="118ec-127">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="118ec-128">Пример</span><span class="sxs-lookup"><span data-stu-id="118ec-128">Example</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="118ec-129">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="118ec-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="118ec-130">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="118ec-130">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="118ec-131">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="118ec-131">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="118ec-132">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="118ec-132">.NET Framework Security</span></span>  
 <span data-ttu-id="118ec-133">Никогда не храните криптографический ключ в формате обычного текста и не передавайте этот ключ в таком формате между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="118ec-133">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  <span data-ttu-id="118ec-134">Вместо этого для хранения криптографических ключей используйте безопасный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="118ec-134">Instead, use a secure key container to store cryptographic keys.</span></span>  
  
 <span data-ttu-id="118ec-135">После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.</span><span class="sxs-lookup"><span data-stu-id="118ec-135">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118ec-136">См. также</span><span class="sxs-lookup"><span data-stu-id="118ec-136">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="118ec-137">Практическое руководство. Расшифровка XML-элементов с помощью симметричных ключей</span><span class="sxs-lookup"><span data-stu-id="118ec-137">How to: Decrypt XML Elements with Symmetric Keys</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md)
