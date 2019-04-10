---
title: Практическое руководство. Расшифровка XML-элементов с помощью асимметричных ключей
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 303c7db984b682d24a8f0e00160eb2d0827a84e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314429"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="a5425-102">Практическое руководство. Расшифровка XML-элементов с помощью асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="a5425-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="a5425-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a5425-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="a5425-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="a5425-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="a5425-105">Дополнительные сведения о стандарте XML-шифрования см. в рекомендации консорциума World Wide Web (W3C) [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="a5425-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="a5425-106">В этом примере выполняет расшифровку XML-элемент, который был зашифрован при помощи методов, описанных в [как: Шифрование XML-элементов с помощью асимметричного ключа](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a5425-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="a5425-107">Он находит <`EncryptedData`> элемент, его расшифровка и затем заменяет элемент с исходным XML-элементом открытого текста.</span><span class="sxs-lookup"><span data-stu-id="a5425-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="a5425-108">Этот пример выполняет расшифровку XML-элемента с использованием двух ключей.</span><span class="sxs-lookup"><span data-stu-id="a5425-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="a5425-109">Он извлекает ранее созданный закрытый ключ RSA из контейнера ключей, а затем использует ключ RSA для расшифровки сеансового ключа в <`EncryptedKey`> элемента <`EncryptedData`> элемента.</span><span class="sxs-lookup"><span data-stu-id="a5425-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="a5425-110">После этого пример использует сеансовый ключ для расшифровки XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="a5425-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="a5425-111">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="a5425-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="a5425-112">Расшифровка XML-элемента с использованием асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="a5425-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="a5425-113">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="a5425-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="a5425-114">Извлеките ранее созданный асимметричный ключ из контейнера при помощи объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="a5425-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="a5425-115">Этот ключ автоматически извлекается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="a5425-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="a5425-116">Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml> для расшифровки документа.</span><span class="sxs-lookup"><span data-stu-id="a5425-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="a5425-117">Добавьте сопоставление ключа и имени, чтобы связать ключ RSA с элементом в документе, который следует расшифровать.</span><span class="sxs-lookup"><span data-stu-id="a5425-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="a5425-118">Для ключа необходимо использовать то же имя, которое использовалось при шифровании документа.</span><span class="sxs-lookup"><span data-stu-id="a5425-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="a5425-119">Обратите внимание, что это имя отличается от имени, используемого для определения ключа в контейнере ключей, заданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="a5425-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="a5425-120">Вызовите <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> метод для расшифровки <`EncryptedData`> элемента.</span><span class="sxs-lookup"><span data-stu-id="a5425-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="a5425-121">Этот метод использует ключ RSA для расшифровки сеансового ключа и автоматически использует этот сеансовый ключ для расшифровки XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="a5425-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="a5425-122">Он также автоматически заменяет <`EncryptedData`> элемент исходным открытым текстом.</span><span class="sxs-lookup"><span data-stu-id="a5425-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="a5425-123">Сохраните XML-документ.</span><span class="sxs-lookup"><span data-stu-id="a5425-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="a5425-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a5425-124">Example</span></span>  
 <span data-ttu-id="a5425-125">В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="a5425-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="a5425-126">Также предполагается, что `test.xml` содержит XML-элемента, зашифрованного с помощью методики, описанные в [как: Шифрование XML-элементов с помощью асимметричного ключа](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a5425-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5425-127">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a5425-127">Compiling the Code</span></span>  
  
-   <span data-ttu-id="a5425-128">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="a5425-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="a5425-129">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="a5425-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a5425-130">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a5425-130">.NET Framework Security</span></span>  
 <span data-ttu-id="a5425-131">Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="a5425-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="a5425-132">Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="a5425-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="a5425-133">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="a5425-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="a5425-134">Не следует внедрять ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="a5425-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="a5425-135">Внедренные ключи могут быть легко прочитаны из сборки с помощью [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, таком как Блокнот.</span><span class="sxs-lookup"><span data-stu-id="a5425-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="a5425-136">После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.</span><span class="sxs-lookup"><span data-stu-id="a5425-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="a5425-137">Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.</span><span class="sxs-lookup"><span data-stu-id="a5425-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5425-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a5425-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="a5425-139">Практическое руководство. Шифрование XML-элементов с помощью асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="a5425-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
