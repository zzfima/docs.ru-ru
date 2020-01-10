---
title: Практическое руководство. Расшифровка XML-элементов при помощи сертификатов X.509
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 46fbefbf7a427ec0d60a34ecc2166f8499d08575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708892"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="bb14f-102">Практическое руководство. Расшифровка XML-элементов при помощи сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="bb14f-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="bb14f-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="bb14f-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="bb14f-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="bb14f-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="bb14f-105">Дополнительные сведения о стандарте шифрования XML см. в спецификации консорциум W3C (W3C) для XML-шифрования, расположенного по адресу <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="bb14f-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="bb14f-106">В этом примере расшифровывается XML-элемент, который был зашифрован с помощью методов, описанных в разделе [инструкции: как шифровать XML-элементы с помощью сертификатов X. 509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bb14f-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="bb14f-107">Он находит элемент <`EncryptedData`>, расшифровывает элемент, а затем заменяет элемент исходным XML-элементом с открытым текстом.</span><span class="sxs-lookup"><span data-stu-id="bb14f-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="bb14f-108">В примере кода этой процедуры выполняется расшифровка XML-элемента при помощи сертификата X.509 из локального хранилища сертификатов текущей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb14f-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="bb14f-109">В примере используется метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> для автоматического получения сертификата X. 509 и расшифровки ключа сеанса, хранящегося в <`EncryptedKey`> элемента <`EncryptedData`.</span><span class="sxs-lookup"><span data-stu-id="bb14f-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="bb14f-110">После этого метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> автоматически использует сеансовый ключ для расшифровки XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="bb14f-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="bb14f-111">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="bb14f-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="bb14f-112">Расшифровка XML-элемента с использованием сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="bb14f-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="bb14f-113">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="bb14f-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="bb14f-114">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для расшифровки.</span><span class="sxs-lookup"><span data-stu-id="bb14f-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="bb14f-115">Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml>, передав объект <xref:System.Xml.XmlDocument> в конструктор.</span><span class="sxs-lookup"><span data-stu-id="bb14f-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="bb14f-116">Выполните расшифровку XML-документа при помощи метода <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb14f-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="bb14f-117">Сохраните объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="bb14f-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="bb14f-118">Пример</span><span class="sxs-lookup"><span data-stu-id="bb14f-118">Example</span></span>  
 <span data-ttu-id="bb14f-119">В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="bb14f-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="bb14f-120">Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="bb14f-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="bb14f-121">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="bb14f-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bb14f-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bb14f-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="bb14f-123">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="bb14f-123">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="bb14f-124">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="bb14f-124">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bb14f-125">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb14f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="bb14f-126">Используемый в этом примере сертификат X.509 предназначен исключительно для тестирования.</span><span class="sxs-lookup"><span data-stu-id="bb14f-126">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="bb14f-127">Приложения должны использовать сертификат X.509, созданный доверенным центром сертификации или сервером сертификатов Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="bb14f-127">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb14f-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb14f-128">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="bb14f-129">Практическое руководство. Шифрование XML-элементов с помощью сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="bb14f-129">How to: Encrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
