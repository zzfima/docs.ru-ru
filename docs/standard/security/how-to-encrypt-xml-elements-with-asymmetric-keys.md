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
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a>Практическое руководство. Шифрование XML-элементов при помощи асимметричных ключей
Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.  Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.  Дополнительные сведения о стандарте шифрования XML см. в спецификации консорциум W3C (W3C) для XML-шифрования, расположенного по адресу <https://www.w3.org/TR/xmldsig-core/>.  
  
 При помощи шифрования XML-данных можно заменить любой XML-элемент или документ элементом <`EncryptedData`>, содержащим зашифрованные XML-данные.  Элемент <`EncryptedData`> может также содержать вложенные элементы, содержащие сведения о ключах и процессах, используемых при шифровании.  Шифрование XML-данных позволяет документу содержать несколько зашифрованных элементов, а также позволяет шифровать элемент несколько раз.  В примере кода в этой процедуре показано, как создать элемент <`EncryptedData`>, а также несколько других вложенных элементов, которые можно использовать позже во время расшифровки.  
  
 Этот пример выполняет шифрование XML-элемента с использованием двух ключей.  Он создает пару из открытого и закрытого ключей RSA и сохраняет ее в безопасном контейнере ключей.  Затем пример создает отдельный сеансовый ключ при помощи алгоритма AES, также известного как алгоритм Rijndael.  Пример использует сеансовый ключ AES для шифрования XML-документа,а затем использует открытый ключ RSA для шифрования сеансового ключа AES.  Наконец, в этом примере зашифрованный ключ сеанса AES и зашифрованные XML-данные сохраняются в XML-документе в новом <`EncryptedData`элемента >.  
  
 Чтобы расшифровать XML-элемент, необходимо извлечь из контейнера ключей закрытый ключ RSA, использовать его для расшифровки сеансового ключа и затем использовать сеансовый ключ для расшифровки документа.  Дополнительные сведения о расшифровке XML-элемента, который был зашифрован с помощью этой процедуры, см. [в разделе как расшифровывать XML-элементы с помощью асимметричных ключей](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md).  
  
 Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.  
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a>Шифрование XML-элемента с использованием асимметричного ключа  
  
1. Создайте объект <xref:System.Security.Cryptography.CspParameters> и укажите имя контейнера ключей.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. Создайте симметричный ключ, используя класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Этот ключ автоматически сохраняется в контейнер ключей при передаче объекта <xref:System.Security.Cryptography.CspParameters> в конструктор класса <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Этот ключ будет использоваться для шифрования сеансового ключа AES, а позднее может быть извлечен для его расшифровки.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.  Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4. Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать. В этом примере выполняется шифрование элемента `"creditcard"`.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5. Создайте новый сеансовый ключ при помощи класса <xref:System.Security.Cryptography.RijndaelManaged>.  Этот ключ будет использоваться для шифрования XML-элемента, а затем будет зашифрован и помещен в XML-документ.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6. Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования указанного элемента при помощи сеансового ключа.  Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> возвращает зашифрованный элемент в виде массива зашифрованных байт.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7. Создайте объект <xref:System.Security.Cryptography.Xml.EncryptedData> и заполните его идентификатором URL-адреса зашифрованного XML-элемента.  Этот идентификатор URL-адреса уведомляет сторону, выполняющую расшифровку, что XML-документ содержит зашифрованный элемент.  Для указания идентификатора URL-адреса можно использовать поле <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>.  XML-элемент с открытым текстом будет заменен элементом <`EncryptedData`>, инкапсулированным этим объектом <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8. Создайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod>, инициализируемый идентификатором URL-адреса криптографического алгоритма, который использовался для сеансового создания ключа.  Передайте объект <xref:System.Security.Cryptography.Xml.EncryptionMethod> в свойство <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. Создайте <xref:System.Security.Cryptography.Xml.EncryptedKey> объект, который будет содержать зашифрованный сеансовый ключ.  Расшифруйте сеансовый ключ, добавьте его в объект <xref:System.Security.Cryptography.Xml.EncryptedKey> и введите имя сеансового ключа и URL-адрес идентификатора ключа.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. Создайте новый объект <xref:System.Security.Cryptography.Xml.DataReference>, который сопоставляет зашифрованные данные с определенным сеансовым ключом.  Этот необязательный шаг позволяет легко указать, что несколько частей XML-документа были зашифрованы при помощи одного ключа.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. Добавьте зашифрованный ключ в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. Создайте новый объект <xref:System.Security.Cryptography.Xml.KeyInfo>, чтобы указать имя ключа RSA.  Добавьте его в объект <xref:System.Security.Cryptography.Xml.EncryptedData>. Это позволяет стороне, осуществляющей расшифровку, правильно определить асимметричный ключ, необходимый для расшифровки сеансового ключа.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. Добавьте зашифрованные данные элемента в объект <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. Сохраните объект <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a>Пример  
 В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.  Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.  Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.  
  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Чтобы скомпилировать этот пример, необходимо включить ссылку на `System.Security.dll`.  
  
- Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Никогда не храните симметричный криптографический ключ в формате обычного текста и не передавайте этот симметричный ключ в таком формате между компьютерами.  Кроме того, не следует хранить или передавать закрытый ключ из пары асимметричных ключей в виде обычного текста.  Дополнительные сведения о симметричных и асимметричных криптографических ключах см. в разделе [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Не следует внедрять ключ непосредственно в исходный код.  Встроенные ключи можно легко считывать из сборки с помощью [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем открытия сборки в текстовом редакторе, например в блокноте.  
  
 После завершения работы с криптографическим ключом очистите его из памяти, установив для каждого байта нулевое значение или вызвав метод <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> управляемого класса шифрования.  Иногда криптографические ключи можно считывать из памяти отладчиком или с жесткого диска, если область памяти выгружается на диск.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Security.Cryptography.Xml>
- [Практическое руководство. Расшифровывание XML-элементов с помощью асимметричных ключей](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md)
