---
title: Параметры вывода в классе XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
ms.openlocfilehash: 504057bd5e10498d39b2bce908742fc20b112c52
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710509"
---
# <a name="output-options-on-the-xslcompiledtransform-class"></a>Параметры вывода в классе XslCompiledTransform
В этом разделе рассматриваются доступные параметры вывода XSLT. Параметры вывода можно указать в таблице стилей или методе <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="xsloutput-element"></a>Элемент xsl:output  
 Элемент `xsl:output` указывает параметры вывода. Тип вывода, указанный методом <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>, определяет поведение параметров `xsl:output`.  
  
 В следующей таблице описано поведение каждого атрибута, доступного в элементе `xsl:output`, если тип вывода - поток или объект <xref:System.IO.TextWriter>.  
  
|Имя атрибута|Поведение|  
|--------------------|--------------|  
|method|Поддерживается.|  
|Версия|Пропускается. Версия всегда 1.0 для XML и 4.0 для HTML.|  
|encoding|Не учитывается при выводе в объект <xref:System.IO.TextWriter>. Вместо него используется свойство <xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType>.|  
|omit-xml-declaration|Поддерживается.|  
|standalone|Поддерживается.|  
|doctype-public|Поддерживается.|  
|doctype-system|Поддерживается.|  
|cdata-section-elements|Поддерживается.|  
|indent|Поддерживается.|  
|media-type|Поддерживается.|  
  
#### <a name="sending-output-to-an-xmlwriter"></a>Отправка выходных данных в XmlWriter  
 Если в таблице стилей используется элемент `xsl:output`, а тип вывода - объект <xref:System.Xml.XmlWriter>, нужно использовать свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> при создании объекта <xref:System.Xml.XmlWriter>. Свойство <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> возвращает объект <xref:System.Xml.XmlWriterSettings>, который содержит сведения, полученные из элемента `xsl:output` скомпилированной таблицы стилей. Этот объект <xref:System.Xml.XmlWriterSettings> можно передать в метод <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>, чтобы создать объект <xref:System.Xml.XmlWriter> с правильными настройками.  
  
## <a name="output-types"></a>Типы вывода  
 В следующем списке описаны типы вывода, доступные в команде <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
#### <a name="xmlwriter"></a>XmlWriter  
 Класс <xref:System.Xml.XmlWriter> записывает потоки или файлы XML. С помощью класса <xref:System.Xml.XmlWriter> можно указать возможности, поддерживающие объект <xref:System.Xml.XmlWriterSettings>, включая параметры вывода. Класс <xref:System.Xml.XmlWriter> представляет собой неотъемлемую часть платформы <xref:System.Xml>. Используйте этот тип вывода для передачи выходных результатов в другой процесс XML.  
  
#### <a name="string"></a>Строка  
 Используйте этот тип вывода, чтобы указать URI выходного файла.  
  
#### <a name="stream"></a>Stream  
 Поток - это абстракция последовательности байтов, например файла, устройства ввода-вывода, межпроцессного канала связи или сокета TCP/IP. Класс <xref:System.IO.Stream> и его производные классы обеспечивают универсальное представление различных типов ввода и вывода, изолируя программиста от конкретных особенностей операционной системы и базовых устройств.  
  
 Используйте этот тип вывода для пересылки данных в объекты <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> или выходной поток (`Response.OutputStream`).  
  
#### <a name="textwriter"></a>TextWriter  
 Объект <xref:System.IO.TextWriter> записывает последовательные символы. Он реализован в классах <xref:System.IO.StringWriter> и <xref:System.IO.StreamWriter>, которые записывают символы в строки и потоки соответственно. Используйте этот тип вывода, если нужно вывести строку.  
  
## <a name="notes"></a>Примечания  
  
- При записи пустых тегов между последним символом имени элемента и обратной косой чертой записывается пробел, например `<myElement />`. Это позволяет правильно отобразить сформированные HTML-страницы в старых браузерах.  
  
## <a name="see-also"></a>См. также:

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
