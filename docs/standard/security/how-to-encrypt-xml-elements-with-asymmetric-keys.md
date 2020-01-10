---
title: Практическое руководство. Шифрование XML-элементов при помощи асимметричных ключей
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- AES algorithm
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys [.NET Framework]
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- key containers
- Advanced Encryption Standard algorithm
- Rijndael
- encryption [.NET Framework], asymmetric keys
ms.assetid: a164ba4f-e596-4bbe-a9ca-f214fe89ed48
ms.openlocfilehash: 2ebf3f86ac550c0179b2e26879a7df128fd529e9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706101"
---
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="18402-102">Практическое руководство. Шифрование XML-элементов при помощи асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="18402-102">How to: Encrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="18402-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="18402-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="18402-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="18402-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="18402-105">Дополнительные сведения о стандарте шифрования XML см. в спецификации консорциум W3C (W3C) для XML-шифрования, расположенного по адресу <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="18402-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="18402-106">При помощи шифрования XML-данных можно заменить любой XML-элемент или документ элементом <`EncryptedData`>, содержащим зашифрованные XML-данные.</span><span class="sxs-lookup"><span data-stu-id="18402-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span>  <span data-ttu-id="18402-107">Элемент <`EncryptedData`> может также содержать вложенные элементы, содержащие сведения о ключах и процессах, используемых при шифровании.</span><span class="sxs-lookup"><span data-stu-id="18402-107">The <`EncryptedData`> element can also contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="18402-108">Шифрование XML-данных позволяет документу содержать несколько зашифрованных элементов, а также позволяет шифровать элемент несколько раз.</span><span class="sxs-lookup"><span data-stu-id="18402-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="18402-109">В примере кода в этой процедуре показано, как создать элемент <`EncryptedData`>, а также несколько других вложенных элементов, которые можно использовать позже во время расшифровки.</span><span class="sxs-lookup"><span data-stu-id="18402-109">The code example in this procedure shows how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="18402-110">Этот пример выполняет шифрование XML-элемента с использованием двух ключей.</span><span class="sxs-lookup"><span data-stu-id="18402-110">This example encrypts an XML element using two keys.</span></span>  <span data-ttu-id="18402-111">Он создает пару из открытого и закрытого ключей RSA и сохраняет ее в безопасном контейнере ключей.</span><span class="sxs-lookup"><span data-stu-id="18402-111">It generates an RSA public/private key pair and saves the key pair to a secure key container.</span></span>  <span data-ttu-id="18402-112">Затем пример создает отдельный сеансовый ключ при помощи алгоритма AES, также известного как алгоритм Rijndael.</span><span class="sxs-lookup"><span data-stu-id="18402-112">The example then creates a separate session key using the Advanced Encryption Standard (AES) algorithm, also called the Rijndael algorithm.</span></span>  <span data-ttu-id="18402-113">Пример использует сеансовый ключ AES для шифрования XML-документа,а затем использует открытый ключ RSA для шифрования сеансового ключа AES.</span><span class="sxs-lookup"><span data-stu-id="18402-113">The example uses the AES session key to encrypt the XML document and then uses the RSA public key to encrypt the AES session key.</span></span>  <span data-ttu-id="18402-114">Наконец, в этом примере зашифрованный ключ сеанса AES и зашифрованные XML-данные сохраняются в XML-документе в новом <`EncryptedData`элемента >.</span><span class="sxs-lookup"><span data-stu-id="18402-114">Finally, the example saves the encrypted AES session key and the encrypted XML data to the XML document within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="18402-115">Чтобы расшифровать XML-элемент, необходимо извлечь из контейнера ключей закрытый ключ RSA, использовать его для расшифровки сеансового ключа и затем использовать сеансовый ключ для расшифровки документа.</span><span class="sxs-lookup"><span data-stu-id="18402-115">To decrypt the XML element, you retrieve the RSA private key from the key container, use it to decrypt the session key, and then use the session key to decrypt the document.</span></span>  <span data-ttu-id="18402-116">Дополнительные сведения о расшифровке XML-элемента, который был зашифрован с помощью этой процедуры, см. [в разделе как расшифровывать XML-элементы с помощью асимметричных ключей](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="18402-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 <span data-ttu-id="18402-117">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="18402-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="18402-118">Шифрование XML-элемента с использованием асимметричного ключа</span><span class="sxs-lookup"><span data-stu-id="18402-118">To encrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="18402-119">Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="18402-119">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="18402-120">Создайте симметричный ключ, используя класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="18402-120">Generate a symmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="18402-121">Этот ключ автоматически сохраняется в контейнер ключей при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="18402-121">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="18402-122">Этот ключ будет использоваться для шифрования сеансового ключа AES, а позднее может быть извлечен для его расшифровки.</span><span class="sxs-lookup"><span data-stu-id="18402-122">This key will be used to encrypt the AES session key and can be retrieved later to decrypt it.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="18402-123">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="18402-123">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="18402-124">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="18402-124">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="18402-125">Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.</span><span class="sxs-lookup"><span data-stu-id="18402-125">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span> <span data-ttu-id="18402-126">В этом примере выполняется шифрование элемента `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="18402-126">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="18402-127">Создайте новый сеансовый ключ при помощи класса <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="18402-127">Create a new session key using the <xref:System.Security.Cryptography.RijndaelManaged> class.</span></span>  <span data-ttu-id="18402-128">Этот ключ будет использоваться для шифрования XML-элемента, а затем будет зашифрован и помещен в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="18402-128">This key will encrypt the XML element, and then be encrypted itself and placed in the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="18402-129">Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования указанного элемента при помощи сеансового ключа.</span><span class="sxs-lookup"><span data-stu-id="18402-129">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the session key.</span></span>  <span data-ttu-id="18402-130">Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> возвращает зашифрованный элемент в виде массива зашифрованных байт.</span><span class="sxs-lookup"><span data-stu-id="18402-130">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="18402-131">Создайте объект <xref:System.Security.Cryptography.Xml.EncryptedData> и заполните его идентификатором URL-адреса зашифрованного XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="18402-131">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the encrypted XML element.</span></span>  <span data-ttu-id="18402-132">Этот идентификатор URL-адреса уведомляет сторону, выполняющую расшифровку, что XML-документ содержит зашифрованный элемент.</span><span class="sxs-lookup"><span data-stu-id="18402-132">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="18402-133">Для указания идентификатора URL-адреса можно использовать поле <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>.</span><span class="sxs-lookup"><span data-stu-id="18402-133">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  <span data-ttu-id="18402-134">XML-элемент с открытым текстом будет заменен элементом <`EncryptedData`>, инкапсулированным этим объектом <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="18402-134">The plaintext XML element will be replaced by an <`EncryptedData`> element encapsulated by this <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="18402-135">Создайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod>, инициализируемый идентификатором URL-адреса криптографического алгоритма, который использовался для сеансового создания ключа.</span><span class="sxs-lookup"><span data-stu-id="18402-135">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the session key.</span></span>  <span data-ttu-id="18402-136">Передайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod> в свойство <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="18402-136">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. <span data-ttu-id="18402-137">Создайте <xref:System.Security.Cryptography.Xml.EncryptedKey> объект, который будет содержать зашифрованный сеансовый ключ.</span><span class="sxs-lookup"><span data-stu-id="18402-137">Create an <xref:System.Security.Cryptography.Xml.EncryptedKey> object to contain the encrypted session key.</span></span>  <span data-ttu-id="18402-138">Расшифруйте сеансовый ключ, добавьте его в объект <xref:System.Security.Cryptography.Xml.EncryptedKey> и введите имя сеансового ключа и URL-адрес идентификатора ключа.</span><span class="sxs-lookup"><span data-stu-id="18402-138">Encrypt the session key, add it to the <xref:System.Security.Cryptography.Xml.EncryptedKey> object, and enter a session key name and key identifier URL.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. <span data-ttu-id="18402-139">Создайте новый объект <xref:System.Security.Cryptography.Xml.DataReference>, который сопоставляет зашифрованные данные с определенным сеансовым ключом.</span><span class="sxs-lookup"><span data-stu-id="18402-139">Create a new <xref:System.Security.Cryptography.Xml.DataReference> object that maps the encrypted data to a particular session key.</span></span>  <span data-ttu-id="18402-140">Этот необязательный шаг позволяет легко указать, что несколько частей XML-документа были зашифрованы при помощи одного ключа.</span><span class="sxs-lookup"><span data-stu-id="18402-140">This optional step allows you to easily specify that multiple parts of an XML document were encrypted by a single key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. <span data-ttu-id="18402-141">Добавьте зашифрованный ключ в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="18402-141">Add the encrypted key to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. <span data-ttu-id="18402-142">Создайте новый объект <xref:System.Security.Cryptography.Xml.KeyInfo>, чтобы указать имя ключа RSA.</span><span class="sxs-lookup"><span data-stu-id="18402-142">Create a new <xref:System.Security.Cryptography.Xml.KeyInfo> object to specify the name of the RSA key.</span></span>  <span data-ttu-id="18402-143">Добавьте его в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="18402-143">Add it to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span> <span data-ttu-id="18402-144">Это позволяет стороне, осуществляющей расшифровку, правильно определить асимметричный ключ, необходимый для расшифровки сеансового ключа.</span><span class="sxs-lookup"><span data-stu-id="18402-144">This helps the decrypting party identify the correct asymmetric key to use when decrypting the session key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. <span data-ttu-id="18402-145">Добавьте зашифрованные данные элемента в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="18402-145">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. <span data-ttu-id="18402-146">Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="18402-146">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. <span data-ttu-id="18402-147">Сохраните объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="18402-147">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="18402-148">Пример</span><span class="sxs-lookup"><span data-stu-id="18402-148">Example</span></span>  
 <span data-ttu-id="18402-149">В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="18402-149">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="18402-150">Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="18402-150">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="18402-151">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="18402-151">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18402-152">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="18402-152">Compiling the Code</span></span>  
  
- <span data-ttu-id="18402-153">Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="18402-153">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="18402-154">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="18402-154">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="18402-155">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18402-155">.NET Framework Security</span></span>  
 <span data-ttu-id="18402-156">Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="18402-156">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="18402-157">Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="18402-157">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="18402-158">Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="18402-158">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="18402-159">Не следует внедрять ключ непосредственно в исходный код.</span><span class="sxs-lookup"><span data-stu-id="18402-159">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="18402-160">Встроенные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="18402-160">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="18402-161">После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.</span><span class="sxs-lookup"><span data-stu-id="18402-161">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="18402-162">Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.</span><span class="sxs-lookup"><span data-stu-id="18402-162">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18402-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="18402-163">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="18402-164">Практическое руководство. Расшифровывание XML-элементов с помощью асимметричных ключей</span><span class="sxs-lookup"><span data-stu-id="18402-164">How to: Decrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md)
