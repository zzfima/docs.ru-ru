---
title: Практическое руководство. Расшифровывание XML-элементов при помощи асимметричных ключей
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
ms.openlocfilehash: 5ed1e2eb2518366da0a57655d7a8691e23f725d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706140"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="84695-102">Практическое руководство. Расшифровывание XML-элементов при помощи асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="84695-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="84695-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="84695-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="84695-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="84695-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="84695-105">Дополнительные сведения о стандарте шифрования XML см. в разделе рекомендации по [синтаксису XML-подписи](https://www.w3.org/TR/xmldsig-core/)консорциум W3C (W3C) и обработке.</span><span class="sxs-lookup"><span data-stu-id="84695-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="84695-106">В примере в этой процедуре выполняется расшифровка XML-элемента, который был зашифрован с помощью методов, описанных в разделе [инструкции. Шифрование XML-элементов с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="84695-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="84695-107">Он находит элемент <`EncryptedData`>, расшифровывает элемент, а затем заменяет элемент исходным XML-элементом с открытым текстом.</span><span class="sxs-lookup"><span data-stu-id="84695-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="84695-108">Этот пример выполняет расшифровку XML-элемента с использованием двух ключей.</span><span class="sxs-lookup"><span data-stu-id="84695-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="84695-109">Он извлекает ранее созданный закрытый ключ RSA из контейнера ключей, а затем использует ключ RSA для расшифровки ключа сеанса, хранящегося в элементе <`EncryptedKey`> элемента <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="84695-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="84695-110">После этого пример использует сеансовый ключ для расшифровки XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="84695-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="84695-111">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="84695-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="84695-112">Расшифровка XML-элемента с использованием асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="84695-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="84695-113">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="84695-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="84695-114">Извлеките ранее созданный асимметричный ключ из контейнера при помощи объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="84695-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="84695-115">Этот ключ автоматически извлекается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="84695-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="84695-116">Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml> для расшифровки документа.</span><span class="sxs-lookup"><span data-stu-id="84695-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="84695-117">Добавьте сопоставление ключа и имени, чтобы связать ключ RSA с элементом в документе, который следует расшифровать.</span><span class="sxs-lookup"><span data-stu-id="84695-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="84695-118">Для ключа необходимо использовать то же имя, которое использовалось при шифровании документа.</span><span class="sxs-lookup"><span data-stu-id="84695-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="84695-119">Обратите внимание, что это имя отличается от имени, используемого для определения ключа в контейнере ключей, заданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="84695-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="84695-120">Вызовите метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, чтобы расшифровать <`EncryptedData`элемента >.</span><span class="sxs-lookup"><span data-stu-id="84695-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="84695-121">Этот метод использует ключ RSA для расшифровки сеансового ключа и автоматически использует этот сеансовый ключ для расшифровки XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="84695-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="84695-122">Он также автоматически заменяет элемент <`EncryptedData`> исходным открытым текстом.</span><span class="sxs-lookup"><span data-stu-id="84695-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="84695-123">Сохраните XML-документ.</span><span class="sxs-lookup"><span data-stu-id="84695-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="84695-124">Пример</span><span class="sxs-lookup"><span data-stu-id="84695-124">Example</span></span>  
 <span data-ttu-id="84695-125">В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="84695-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="84695-126">Также предполагается, что `test.xml` содержит XML-элемент, который был зашифрован с помощью методов, описанных в разделе [как шифровать XML-элементы с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="84695-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84695-127">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="84695-127">Compiling the Code</span></span>  
  
- <span data-ttu-id="84695-128">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="84695-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="84695-129">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="84695-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="84695-130">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="84695-130">.NET Framework Security</span></span>  
 <span data-ttu-id="84695-131">Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="84695-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="84695-132">Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="84695-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="84695-133">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="84695-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="84695-134">Не следует внедрять ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="84695-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="84695-135">Внедренные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="84695-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="84695-136">После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.</span><span class="sxs-lookup"><span data-stu-id="84695-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="84695-137">Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.</span><span class="sxs-lookup"><span data-stu-id="84695-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84695-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="84695-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="84695-139">Практическое руководство. Шифрование XML-элементов с помощью асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="84695-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
