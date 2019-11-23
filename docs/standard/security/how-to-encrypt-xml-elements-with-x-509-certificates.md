---
title: Практическое руководство. Шифрование XML-элементов с помощью сертификатов X.509
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], X.509 certificates
- cryptography [.NET Framework], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d569d3c020e7329d987e957f181b34c8cfbf941a
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353864"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="7e728-102">Практическое руководство. Шифрование XML-элементов с помощью сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="7e728-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="7e728-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="7e728-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="7e728-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="7e728-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="7e728-105">Дополнительные сведения о стандарте шифрования XML см. в спецификации консорциум W3C (W3C) для XML-шифрования, расположенного по адресу <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="7e728-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="7e728-106">При помощи шифрования XML-данных можно заменить любой XML-элемент или документ элементом <`EncryptedData`>, содержащим зашифрованные XML-данные.</span><span class="sxs-lookup"><span data-stu-id="7e728-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="7e728-107">Элемент <`EncryptedData`> может включать в себя вложенные элементы, содержащие сведения о ключах и процессах, использованных при шифровании.</span><span class="sxs-lookup"><span data-stu-id="7e728-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="7e728-108">Шифрование XML-данных позволяет документу содержать несколько зашифрованных элементов, а также позволяет шифровать элемент несколько раз.</span><span class="sxs-lookup"><span data-stu-id="7e728-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="7e728-109">В примере кода в данной процедуре показано создание элемента <`EncryptedData`> наряду с несколькими вложенными элементами, которые можно использовать позже при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="7e728-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="7e728-110">Этот пример выполняет шифрование XML-элемента с использованием двух ключей.</span><span class="sxs-lookup"><span data-stu-id="7e728-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="7e728-111">Он создает тестовый сертификат X.509 при помощи [инструмента для создания сертификатов (Makecert.exe)](/windows/desktop/SecCrypto/makecert) и сохраняет этот сертификат в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7e728-111">It generates a test X.509 certificate using the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) and saves the certificate to a certificate store.</span></span> <span data-ttu-id="7e728-112">Затем пример программным образом получает сертификат и использует его для шифрования XML-элемента при помощи метода <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e728-112">The example then programmatically retrieves the certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="7e728-113">На внутреннем уровне метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> создает отдельный сеансовый ключ и использует его для шифрования XML-документа.</span><span class="sxs-lookup"><span data-stu-id="7e728-113">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="7e728-114">Этот метод шифрует сеансовый ключ и сохраняет его вместе с зашифрованным XML-элементом в новом элементе <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="7e728-114">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="7e728-115">Для расшифровки XML-элемента просто вызовите метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, который автоматически извлекает сертификат X.509 из хранилища сертификатов и выполняет необходимую расшифровку.</span><span class="sxs-lookup"><span data-stu-id="7e728-115">To decrypt the XML element, simply call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="7e728-116">Дополнительные сведения о способах расшифровки XML-элемента, зашифрованного при использовании этой процедуры, см. в разделе [Практическое руководство. Расшифровка XML-элементов при помощи сертификатов X.509](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="7e728-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
 <span data-ttu-id="7e728-117">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="7e728-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="7e728-118">Шифрование XML-элемента с использованием сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="7e728-118">To encrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="7e728-119">Используйте [инструмент для создания сертификатов (Makecert.exe)](/windows/desktop/SecCrypto/makecert), чтобы создать тестовый сертификат X.509 и поместить его в хранилище локального пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e728-119">Use the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="7e728-120">Необходимо создать ключ обмена и сделать его экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="7e728-120">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="7e728-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7e728-121">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="7e728-122">Создайте объект <xref:System.Security.Cryptography.X509Certificates.X509Store> и инициализируйте его, чтобы открыть хранилище текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e728-122">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="7e728-123">Откройте хранилище в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e728-123">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="7e728-124">Инициализируйте <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> всеми сертификатами в хранилище.</span><span class="sxs-lookup"><span data-stu-id="7e728-124">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="7e728-125">Выполните перечисление сертификатов в хранилище, чтобы найти сертификат с соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="7e728-125">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="7e728-126">В этом примере сертификат имеет имя `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="7e728-126">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="7e728-127">Закройте хранилище после нахождения сертификата.</span><span class="sxs-lookup"><span data-stu-id="7e728-127">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="7e728-128">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="7e728-128">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="7e728-129">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="7e728-129">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="7e728-130">Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.</span><span class="sxs-lookup"><span data-stu-id="7e728-130">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="7e728-131">В этом примере выполняется шифрование элемента `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="7e728-131">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="7e728-132">Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования указанного элемента при помощи сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="7e728-132">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="7e728-133">Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> возвращает зашифрованный элемент в виде объекта <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="7e728-133">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="7e728-134">Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="7e728-134">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="7e728-135">Сохраните объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7e728-135">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="7e728-136">Пример</span><span class="sxs-lookup"><span data-stu-id="7e728-136">Example</span></span>  
 <span data-ttu-id="7e728-137">В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="7e728-137">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="7e728-138">Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="7e728-138">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="7e728-139">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="7e728-139">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e728-140">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7e728-140">Compiling the Code</span></span>  
  
- <span data-ttu-id="7e728-141">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="7e728-141">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="7e728-142">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="7e728-142">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7e728-143">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7e728-143">.NET Framework Security</span></span>  
 <span data-ttu-id="7e728-144">Используемый в этом примере сертификат X.509 предназначен исключительно для тестирования.</span><span class="sxs-lookup"><span data-stu-id="7e728-144">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="7e728-145">Приложения должны использовать сертификат X.509, созданный доверенным центром сертификации или сервером сертификатов Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="7e728-145">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e728-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e728-146">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="7e728-147">Практическое руководство. Расшифровка XML-элементов при помощи сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="7e728-147">How to: Decrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)
