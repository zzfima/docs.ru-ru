---
title: Практическое руководство. Подписание XML-документов при помощи цифровых подписей
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSACryptoServiceProvider class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: 0df036b3336527f3cc0e48d9a7ec835ab9f1cf4a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706049"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="08a15-102">Практическое руководство. Подписание XML-документов при помощи цифровых подписей</span><span class="sxs-lookup"><span data-stu-id="08a15-102">How to: Sign XML Documents with Digital Signatures</span></span>
<span data-ttu-id="08a15-103">Можно использовать классы в пространстве имен <xref:System.Security.Cryptography.Xml> для подписания XML-документа или его части при помощи цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="08a15-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="08a15-104">Цифровые подписи XML (XMLDSIG) позволяют убедиться, что данные не были изменены после подписания.</span><span class="sxs-lookup"><span data-stu-id="08a15-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="08a15-105">Дополнительные сведения о стандарте XMLDSIG см. в разделе рекомендации по [синтаксису XML-подписи](https://www.w3.org/TR/xmldsig-core/)консорциум W3C (W3C) и обработке.</span><span class="sxs-lookup"><span data-stu-id="08a15-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="08a15-106">В примере кода в этой процедуре показано, как подписать весь XML-документ с помощью цифровой подписи и присоединить подпись к документу в элементе <`Signature`>.</span><span class="sxs-lookup"><span data-stu-id="08a15-106">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="08a15-107">Пример создает ключ подписывания RSA, добавляет его в безопасный контейнер ключей и затем использует этот ключ для создания цифровой подписи XML-документа.</span><span class="sxs-lookup"><span data-stu-id="08a15-107">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="08a15-108">Впоследствии ключ можно извлечь для проверки цифровой подписи XML либо использовать для подписывания другого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="08a15-108">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
 <span data-ttu-id="08a15-109">Сведения о том, как проверить цифровую подпись XML, созданную с помощью этой процедуры, см. [в разделе как проверить цифровые подписи XML-документов](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="08a15-109">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="08a15-110">Создание цифровой подписи XML-документа</span><span class="sxs-lookup"><span data-stu-id="08a15-110">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="08a15-111">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="08a15-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="08a15-112">Создайте асимметричный ключ, используя класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="08a15-112">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="08a15-113">Этот ключ автоматически сохраняется в контейнер ключей при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="08a15-113">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="08a15-114">Этот ключ будет использоваться для подписывания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="08a15-114">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="08a15-115">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="08a15-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="08a15-116">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="08a15-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="08a15-117">Создайте новый объект <xref:System.Security.Cryptography.Xml.SignedXml> и передайте в него объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="08a15-117">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="08a15-118">Добавьте ключ подписывания RSA в объект <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="08a15-118">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="08a15-119">Создайте объект <xref:System.Security.Cryptography.Xml.Reference>, определяющий, что именно требуется подписать.</span><span class="sxs-lookup"><span data-stu-id="08a15-119">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="08a15-120">Чтобы подписать весь документ целиком, установите для свойства <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> значение `""`.</span><span class="sxs-lookup"><span data-stu-id="08a15-120">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="08a15-121">Добавьте объект <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> в объект <xref:System.Security.Cryptography.Xml.Reference>.</span><span class="sxs-lookup"><span data-stu-id="08a15-121">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="08a15-122">Преобразование позволяет проверяющему представить XML-данные в той же самой форме, которую использовал подписавший.</span><span class="sxs-lookup"><span data-stu-id="08a15-122">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="08a15-123">XML-данные могут быть представлены различными способами, поэтому этот шаг крайне важен для выполнения проверки.</span><span class="sxs-lookup"><span data-stu-id="08a15-123">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="08a15-124">Добавьте объект <xref:System.Security.Cryptography.Xml.Reference> в объект <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="08a15-124">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="08a15-125">Вычислите подпись, вызвав метод <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>.</span><span class="sxs-lookup"><span data-stu-id="08a15-125">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="08a15-126">Извлеките XML-представление сигнатуры (<`Signature`элемент >) и сохраните его в новом объекте <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="08a15-126">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="08a15-127">Добавьте элемент в объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="08a15-127">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="08a15-128">Сохраните документ.</span><span class="sxs-lookup"><span data-stu-id="08a15-128">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="08a15-129">Пример</span><span class="sxs-lookup"><span data-stu-id="08a15-129">Example</span></span>  
 <span data-ttu-id="08a15-130">В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="08a15-130">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="08a15-131">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="08a15-131">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08a15-132">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="08a15-132">Compiling the Code</span></span>  
  
- <span data-ttu-id="08a15-133">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="08a15-133">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="08a15-134">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="08a15-134">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="08a15-135">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="08a15-135">.NET Framework Security</span></span>  
 <span data-ttu-id="08a15-136">Не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="08a15-136">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="08a15-137">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="08a15-137">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="08a15-138">Не следует внедрять закрытый ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="08a15-138">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="08a15-139">Встроенные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="08a15-139">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a15-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a15-140">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="08a15-141">Практическое руководство. Проверка цифровых подписей XML-документов</span><span class="sxs-lookup"><span data-stu-id="08a15-141">How to: Verify the Digital Signatures of XML Documents</span></span>](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md)
