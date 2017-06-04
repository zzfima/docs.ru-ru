---
title: "How to: Decrypt XML Elements with X.509 Certificates | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "System.Security.Cryptography.EncryptedXml class"
  - "XML encryption"
  - "System.Security.Cryptography.X509Certificate2 class"
  - "decryption"
  - "X.509 certificates"
  - "certificates, X.509 certificates"
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Decrypt XML Elements with X.509 Certificates
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML\-документа.  Шифрование XML\-данных — это стандартный способ обмена зашифрованными XML\-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.  Дополнительные сведения о стандарте XML\-шифрования см. в соответствующей спецификации консорциума W3C, которая находится по адресу http:\/\/www.w3.org\/TR\/xmldsig\-core\/.  
  
 В этом примере выполняется расшифровка XML\-элемента, который был зашифрован при помощи методов, описанных в разделе [How to: Encrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).  В нем производится поиск элемента \<`EncryptedData`\>, его расшифровка и замена исходным XML\-элементом в формате простого текста.  
  
 В примере кода этой процедуры выполняется расшифровка XML\-элемента при помощи сертификата X.509 из локального хранилища сертификатов текущей учетной записи пользователя.  В примере используется метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> для автоматического извлечения сертификата X.509 и расшифровки сеансового ключа, хранящегося в элементе \<`EncryptedKey`\> элемента \<`EncryptedData`\>.  После этого метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> автоматически использует сеансовый ключ для расшифровки XML\-элемента.  
  
 Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.  
  
### Расшифровка XML\-элемента с использованием сертификата X.509  
  
1.  Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML\-файл с диска.  Объект <xref:System.Xml.XmlDocument> содержит XML\-элемент для расшифровки.  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2.  Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml>, передав объект <xref:System.Xml.XmlDocument> в конструктор.  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3.  Выполните расшифровку XML\-документа при помощи метода <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4.  Сохраните объект <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## Пример  
 В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.  Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.  Можно поместить следующий XML\-код в файл с именем `test.xml` и использовать его вместе с данным примером.  
  
```  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## Компиляция кода  
  
-   Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
-   Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## Безопасность платформы .NET Framework  
 Используемый в этом примере сертификат X.509 предназначен исключительно для тестирования.  Приложения должны использовать сертификат X.509, созданный доверенным центром сертификации или сервером сертификатов Microsoft Windows.  
  
## См. также  
 <xref:System.Security.Cryptography.Xml>   
 [How to: Encrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)