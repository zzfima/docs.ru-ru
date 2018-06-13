---
title: Практическое руководство. Расшифровывание XML-элементов с помощью асимметричного ключа
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
ms.openlocfilehash: 329569ea148542ff596057d9eb9efe2e95768341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589075"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Практическое руководство. Расшифровывание XML-элементов с помощью асимметричного ключа
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML-документа.  Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.  Дополнительные сведения о стандарте XML-шифрования см. в рекомендации консорциума World Wide Web (W3C) [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).  
  
 В этом примере расшифровка XML-элемента, зашифрованного с помощью методов, описанных в [как: шифрование XML-элементов с помощью асимметричного ключа](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Он производит поиск элемента <`EncryptedData`>, его расшифровку и замену исходным XML-элементом в формате простого текста.  
  
 Этот пример выполняет расшифровку XML-элемента с использованием двух ключей.  Он извлекает ранее созданный закрытый ключ RSA из контейнера ключей, а затем использует этот ключ RSA для расшифровки сеансового ключа, хранящегося в элементе <`EncryptedKey`> элемента <`EncryptedData`>.  После этого пример использует сеансовый ключ для расшифровки XML-элемента.  
  
 Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>Расшифровка XML-элемента с использованием асимметричного ключа  
  
1.  Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  Извлеките ранее созданный асимметричный ключ из контейнера при помощи объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Этот ключ автоматически извлекается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml> для расшифровки документа.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4.  Добавьте сопоставление ключа и имени, чтобы связать ключ RSA с элементом в документе, который следует расшифровать.  Для ключа необходимо использовать то же имя, которое использовалось при шифровании документа.  Обратите внимание, что это имя отличается от имени, используемого для определения ключа в контейнере ключей, заданном на шаге 1.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5.  Вызовите метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> для расшифровки элемента <`EncryptedData`>.  Этот метод использует ключ RSA для расшифровки сеансового ключа и автоматически использует этот сеансовый ключ для расшифровки XML-элемента.  Он также автоматически заменяет элемент <`EncryptedData`> исходным открытым текстом.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6.  Сохраните XML-документ.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Пример  
 В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.  Также предполагается, что `test.xml` содержит XML-элемент, который был зашифрован с помощью методик, описанных в [как: шифрование XML-элементов с помощью асимметричного ключа](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
-   Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.  Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.  Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Не следует внедрять ключ непосредственно в исходный код.  Внедренные ключи могут быть легко прочитаны из сборки с помощью [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, таком как Блокнот.  
  
 После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.  Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Cryptography.Xml>  
 [Практическое руководство. Шифрование XML-элементов с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
