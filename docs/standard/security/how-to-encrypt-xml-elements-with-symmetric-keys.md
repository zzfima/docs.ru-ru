---
title: Практическое руководство. Шифрование XML-элементов при помощи симметричных ключей
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET Framework], symmetric keys
- encryption [.NET Framework], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Advanced Encryption Standard algorithm
- Rijndael
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
ms.openlocfilehash: cda5a32e9a7421cd65b2046b403fde9e05230493
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706088"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a>Практическое руководство. Шифрование XML-элементов при помощи симметричных ключей
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.  Шифрование XML-данных позволяет хранить или передавать важные XML-данные, не беспокоясь о том, что они могут быть прочитаны.  Эта процедура шифрует XML-элемент с помощью алгоритма AES (AES), также известного как Rijndael.  
  
 Дополнительные сведения о расшифровке XML-элемента, который был зашифрован с помощью этой процедуры, см. [в разделе как расшифровывать XML-элементы с симметричными ключами](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md).  
  
 При использовании симметричного алгоритма, такого как AES, для шифрования XML-данных необходимо использовать один и тот же ключ как для шифрования, так и для расшифровки XML-данных.  В этом примере предполагается, что зашифрованные XML-данные будут расшифровываться при помощи того же ключа и что стороны, выполняющие шифрование и расшифровку, согласуют между собой используемый алгоритм и ключ.  В этом примере ключ AES не сохраняется и не шифруется внутри зашифрованного XML-документа.  
  
 Этот пример подходит для ситуаций, где отдельному приложению требуется зашифровать данные на основе хранящегося в памяти сеансового ключа или на основе криптографически стойкого ключа, полученного из пароля.  В ситуациях, когда два приложения и более нуждаются в общем доступе к зашифрованным XML-данным, рекомендуется использовать схему шифрования, основанную на асимметричном алгоритме или сертификате X.509.  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a>Шифрование XML-элемента при помощи симметричного ключа  
  
1. Создайте симметричный ключ, используя класс <xref:System.Security.Cryptography.RijndaelManaged>.  Этот ключ будет использоваться для шифрования XML-элемента.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.  Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.  В этом примере выполняется шифрование элемента `"creditcard"`.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования <xref:System.Xml.XmlElement> при помощи симметричного ключа.  Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> возвращает зашифрованный элемент в виде массива зашифрованных байт.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. Создайте объект <xref:System.Security.Cryptography.Xml.EncryptedData> и заполните его идентификатором URL-адреса элемента XML-шифрования.  Этот идентификатор URL-адреса уведомляет сторону, выполняющую расшифровку, что XML-документ содержит зашифрованный элемент.  Для указания идентификатора URL-адреса можно использовать поле <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. Создайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod>, инициализируемый идентификатором URL-адреса криптографического алгоритма, который использовался для создания ключа.  Передайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod> в свойство <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. Добавьте зашифрованные данные элемента в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a>Пример  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
- Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Никогда не храните криптографический ключ в формате обычного текста и не передавайте этот ключ в таком формате между компьютерами.  Вместо этого для хранения криптографических ключей используйте безопасный контейнер ключей.  
  
 После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Security.Cryptography.Xml>
- [Практическое руководство. Расшифровка XML-элементов с помощью симметричных ключей](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md)
