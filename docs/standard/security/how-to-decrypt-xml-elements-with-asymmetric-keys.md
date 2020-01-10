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
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Практическое руководство. Расшифровывание XML-элементов при помощи асимметричных ключей
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования и расшифровки элемента XML-документа.  Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.  Дополнительные сведения о стандарте шифрования XML см. в разделе рекомендации по [синтаксису XML-подписи](https://www.w3.org/TR/xmldsig-core/)консорциум W3C (W3C) и обработке.  
  
 В примере в этой процедуре выполняется расшифровка XML-элемента, который был зашифрован с помощью методов, описанных в разделе [инструкции. Шифрование XML-элементов с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Он находит элемент <`EncryptedData`>, расшифровывает элемент, а затем заменяет элемент исходным XML-элементом с открытым текстом.  
  
 Этот пример выполняет расшифровку XML-элемента с использованием двух ключей.  Он извлекает ранее созданный закрытый ключ RSA из контейнера ключей, а затем использует ключ RSA для расшифровки ключа сеанса, хранящегося в элементе <`EncryptedKey`> элемента <`EncryptedData`>.  После этого пример использует сеансовый ключ для расшифровки XML-элемента.  
  
 Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>Расшифровка XML-элемента с использованием асимметричного ключа  
  
1. Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. Извлеките ранее созданный асимметричный ключ из контейнера при помощи объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Этот ключ автоматически извлекается из контейнера ключей по имени при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. Создайте новый объект <xref:System.Security.Cryptography.Xml.EncryptedXml> для расшифровки документа.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. Добавьте сопоставление ключа и имени, чтобы связать ключ RSA с элементом в документе, который следует расшифровать.  Для ключа необходимо использовать то же имя, которое использовалось при шифровании документа.  Обратите внимание, что это имя отличается от имени, используемого для определения ключа в контейнере ключей, заданном на шаге 1.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. Вызовите метод <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, чтобы расшифровать <`EncryptedData`элемента >.  Этот метод использует ключ RSA для расшифровки сеансового ключа и автоматически использует этот сеансовый ключ для расшифровки XML-элемента.  Он также автоматически заменяет элемент <`EncryptedData`> исходным открытым текстом.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. Сохраните XML-документ.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Пример  
 В этом примере предполагается, что файл с именем `test.xml` существует в том же каталоге, что и скомпилированная программа.  Также предполагается, что `test.xml` содержит XML-элемент, который был зашифрован с помощью методов, описанных в разделе [как шифровать XML-элементы с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
- Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.  Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.  Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Не следует внедрять ключ непосредственно в исходный код.  Внедренные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.  
  
 После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.  Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Security.Cryptography.Xml>
- [Практическое руководство. Шифрование XML-элементов с помощью асимметричных ключей](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
