---
title: Практическое руководство. Проверка цифровых подписей XML-документов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: 5d562c23d3b0fd7eda5dc273932ada77709641a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706010"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="a64b3-102">Практическое руководство. Проверка цифровых подписей XML-документов</span><span class="sxs-lookup"><span data-stu-id="a64b3-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="a64b3-103">Классы в пространстве имен <xref:System.Security.Cryptography.Xml> можно использовать для проверки XML-данных, подписанных цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="a64b3-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="a64b3-104">Цифровые подписи XML (XMLDSIG) позволяют убедиться, что данные не были изменены после подписания.</span><span class="sxs-lookup"><span data-stu-id="a64b3-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="a64b3-105">Дополнительные сведения о стандарте XMLDSIG см. в спецификации консорциум W3C (W3C) по адресу <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
 <span data-ttu-id="a64b3-106">В примере кода в этой процедуре показано, как проверить цифровую подпись XML, содержащуюся в элементе <`Signature`>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="a64b3-107">Пример извлекает открытый ключ RSA из контейнера ключей и затем использует этот ключ для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="a64b3-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="a64b3-108">Сведения о том, как создать цифровую подпись, которую можно проверить с помощью этого метода, см. [в разделе как подписывать XML-документы с помощью цифровых подписей](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="a64b3-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="a64b3-109">Проверка цифровой подписи XML-документа</span><span class="sxs-lookup"><span data-stu-id="a64b3-109">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="a64b3-110">Чтобы проверить документ, необходимо использовать тот же асимметричный ключ, который использовался для подписи.</span><span class="sxs-lookup"><span data-stu-id="a64b3-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="a64b3-111">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей, который использовался для подписи.</span><span class="sxs-lookup"><span data-stu-id="a64b3-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="a64b3-112">Получите открытый ключ при помощи класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="a64b3-113">Этот ключ автоматически загружается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="a64b3-114">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="a64b3-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="a64b3-115">Объект <xref:System.Xml.XmlDocument> содержит подписанный XML-документ, подлежащий проверке.</span><span class="sxs-lookup"><span data-stu-id="a64b3-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="a64b3-116">Создайте новый объект <xref:System.Security.Cryptography.Xml.SignedXml> и передайте в него объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="a64b3-117">Найдите элемент <`signature`> и создайте новый объект <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="a64b3-118">Загрузите XML-код первого <`signature`элемента > в объект <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="a64b3-119">Проверьте подпись, используя  метод <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> и открытый ключ RSA.</span><span class="sxs-lookup"><span data-stu-id="a64b3-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="a64b3-120">Этот метод возвращает логическое значение, указывающее на успешное выполнение или сбой операции.</span><span class="sxs-lookup"><span data-stu-id="a64b3-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="a64b3-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a64b3-121">Example</span></span>  
 <span data-ttu-id="a64b3-122">В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="a64b3-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="a64b3-123">Файл `"test.xml"` должен быть подписан с помощью методов, описанных в разделе [как подписывать XML-документы с помощью цифровых подписей](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="a64b3-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a64b3-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a64b3-124">Compiling the Code</span></span>  
  
- <span data-ttu-id="a64b3-125">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="a64b3-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="a64b3-126">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="a64b3-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a64b3-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a64b3-127">.NET Framework Security</span></span>  
 <span data-ttu-id="a64b3-128">Не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="a64b3-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="a64b3-129">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="a64b3-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="a64b3-130">Не следует внедрять закрытый ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="a64b3-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="a64b3-131">Встроенные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="a64b3-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64b3-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a64b3-132">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="a64b3-133">Практическое руководство. Подписание XML-документов с помощью цифровых подписей</span><span class="sxs-lookup"><span data-stu-id="a64b3-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
