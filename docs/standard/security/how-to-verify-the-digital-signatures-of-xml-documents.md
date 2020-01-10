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
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a>Практическое руководство. Проверка цифровых подписей XML-документов
Классы в пространстве имен <xref:System.Security.Cryptography.Xml> можно использовать для проверки XML-данных, подписанных цифровой подписью. Цифровые подписи XML (XMLDSIG) позволяют убедиться, что данные не были изменены после подписания. Дополнительные сведения о стандарте XMLDSIG см. в спецификации консорциум W3C (W3C) по адресу <https://www.w3.org/TR/xmldsig-core/>.
  
 В примере кода в этой процедуре показано, как проверить цифровую подпись XML, содержащуюся в элементе <`Signature`>.  Пример извлекает открытый ключ RSA из контейнера ключей и затем использует этот ключ для проверки подписи.  
  
 Сведения о том, как создать цифровую подпись, которую можно проверить с помощью этого метода, см. [в разделе как подписывать XML-документы с помощью цифровых подписей](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a>Проверка цифровой подписи XML-документа  
  
1. Чтобы проверить документ, необходимо использовать тот же асимметричный ключ, который использовался для подписи.  Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей, который использовался для подписи.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. Получите открытый ключ при помощи класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Этот ключ автоматически загружается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.  Объект <xref:System.Xml.XmlDocument> содержит подписанный XML-документ, подлежащий проверке.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. Создайте новый объект <xref:System.Security.Cryptography.Xml.SignedXml> и передайте в него объект <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. Найдите элемент <`signature`> и создайте новый объект <xref:System.Xml.XmlNodeList>.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. Загрузите XML-код первого <`signature`элемента > в объект <xref:System.Security.Cryptography.Xml.SignedXml>.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. Проверьте подпись, используя  метод <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> и открытый ключ RSA.  Этот метод возвращает логическое значение, указывающее на успешное выполнение или сбой операции.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a>Пример  
 В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.  Файл `"test.xml"` должен быть подписан с помощью методов, описанных в разделе [как подписывать XML-документы с помощью цифровых подписей](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
- Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.  Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Не следует внедрять закрытый ключ непосредственно в исходный код.  Встроенные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Security.Cryptography.Xml>
- [Практическое руководство. Подписание XML-документов с помощью цифровых подписей](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
