---
title: Результаты вывода XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 178b1e949868d3af893cbcb6df63590053341a3e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710496"
---
# <a name="outputs-from-an-xsltransform"></a>Результаты вывода XslTransform
Поскольку таблицы стилей могут определять формат вывода с помощью инструкции `<xsl:output>` с атрибутом `method`, в следующей таблице описан формат вывода при использовании для записи вывода метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> и объявлении этого формата как <xref:System.IO.Stream> или <xref:System.IO.TextWriter>.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Поскольку таблицы стилей могут определять формат вывода с помощью инструкции `<xsl:output>` с атрибутом `method`, в следующей таблице описан формат вывода при использовании для записи вывода метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> и объявлении этого формата как <xref:System.IO.Stream> или <xref:System.IO.TextWriter>. В следующей таблице показано, что происходит, если тип вывода декларирован методом <xref:System.Xml.Xsl.XslTransform.Transform%2A> в сочетании с инструкцией `<xsl:output>`.  
  
|\<xsl:output method = > attribute|Формат результата|  
|-----------------------------------------|-------------------|  
|method="xml"|XML|  
|method="html"|HTML|  
|method="text"|Текст|  
  
> [!NOTE]
> Примечание. Инструкция `<xsl:output>` не выполняется, если метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> возвращает <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlWriter>.  
  
 Следующие атрибуты поддерживаются, если выходными данными метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> является объект <xref:System.IO.Stream> или <xref:System.IO.TextWriter>:  
  
- encoding*  
  
- omit-xml-declaration  
  
- standalone  
  
- doctype-public  
  
- doctype-system  
  
- cdata-section-elements  
  
- indent  
  
    > [!NOTE]
    > \*Атрибут encoding пропускается, если метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> отправляет выходные данные в объект <xref:System.IO.TextWriter>. Вместо него в объекте <xref:System.IO.TextWriter> используется свойство encoding. 
  
 Следующий атрибут пропускается, если выходом метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> является <xref:System.IO.Stream>.  
  
- Версия: всегда используется версия 1.0  
  
- Тип носителя: используемый тип носителя  
  
## <a name="escaping-special-characters"></a>Экранирование специальных символов  
 Тег `<xsl:text disable-output-escaping>` используется для указания, следует ли экранировать специальные символы в XML-формате (например, использовать `<&lt>` вместо `"<"`) или оставлять их в текущем состоянии. Атрибут `disable-output-escaping` не учитывать при преобразовании в объект <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlWriter> и не влияет на специальные символы.  
  
## <a name="see-also"></a>См. также:

- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
