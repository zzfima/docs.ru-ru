---
title: "How to: Encrypt XML Elements with X.509 Certificates | Microsoft Docs"
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
  - "encryption [.NET Framework], X.509 certificates"
  - "cryptography [.NET Framework], X.509 certificates"
  - "System.Security.Cryptography.EncryptedXml class"
  - "XML encryption"
  - "System.Security.Cryptography.X509Certificate2 class"
  - "X.509 certificates"
  - "certificates, X.509 certificates"
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Encrypt XML Elements with X.509 Certificates
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML\-документа.  Шифрование XML\-данных — это стандартный способ обмена зашифрованными XML\-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.  Дополнительные сведения о стандарте XML\-шифрования см. в соответствующей спецификации консорциума W3C, которая находится по адресу http:\/\/www.w3.org\/TR\/xmldsig\-core\/.  
  
 При помощи шифрования XML\-данных можно заменить любой XML\-элемент или документ элементом \<`EncryptedData`\>, содержащим зашифрованные XML\-данные.  Элемент \<`EncryptedData`\> может включать в себя вложенные элементы, содержащие сведения о ключах и процессах, использованных при шифровании.  Шифрование XML\-данных позволяет документу содержать несколько зашифрованных элементов, а также позволяет шифровать элемент несколько раз.  В примере кода в данной процедуре показано создание элемента \<`EncryptedData`\> наряду с несколькими вложенными элементами, которые можно использовать позже при расшифровке.  
  
 Этот пример выполняет шифрование XML\-элемента с использованием двух ключей.  Он создает тестовый сертификат X.509 при помощи [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md) и сохраняет этот сертификат в хранилище сертификатов.  Затем пример программным образом получает сертификат и использует его для шифрования XML\-элемента при помощи метода <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>.  На внутреннем уровне метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> создает отдельный сеансовый ключ и использует его для шифрования XML\-документа.  Этот метод шифрует сеансовый ключ и сохраняет его вместе с зашифрованным XML\-элементом в новом элементе \<`EncryptedData`\>.  
  
 Для расшифровки XML\-элемента просто вызовите метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, который автоматически извлекает сертификат X.509 из хранилища сертификатов и выполняет необходимую расшифровку.  Дополнительные сведения о способах расшифровки XML\-элемента, зашифрованного при использовании этой процедуры, см. в разделе [How to: Decrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md).  
  
 Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.  
  
### Шифрование XML\-элемента с использованием сертификата X.509  
  
1.  Используйте [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md), чтобы создать тестовый сертификат X.509 и поместить его в хранилище локального пользователя.  Необходимо создать ключ обмена и сделать его экспортируемым.  Выполните следующую команду:  
  
    ```  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2.  Создайте объект <xref:System.Security.Cryptography.X509Certificates.X509Store> и инициализируйте его, чтобы открыть хранилище текущего пользователя.  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3.  Откройте хранилище в режиме только для чтения.  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4.  Инициализируйте <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> всеми сертификатами в хранилище.  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5.  Выполните перечисление сертификатов в хранилище, чтобы найти сертификат с соответствующим именем.  В этом примере сертификат имеет имя `"CN=XML_ENC_TEST_CERT"`.  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6.  Закройте хранилище после нахождения сертификата.  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7.  Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML\-файл с диска.  Объект <xref:System.Xml.XmlDocument> содержит XML\-элемент для шифрования.  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8.  Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.  В этом примере выполняется шифрование элемента `"creditcard"`.  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования указанного элемента при помощи сертификата X.509.  Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> возвращает зашифрованный элемент в виде объекта <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. Сохраните объект <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
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
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## Компиляция кода  
  
-   Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
-   Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## Безопасность платформы .NET Framework  
 Используемый в этом примере сертификат X.509 предназначен исключительно для тестирования.  Приложения должны использовать сертификат X.509, созданный доверенным центром сертификации или сервером сертификатов Microsoft Windows.  
  
## См. также  
 <xref:System.Security.Cryptography.Xml>   
 [How to: Decrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)