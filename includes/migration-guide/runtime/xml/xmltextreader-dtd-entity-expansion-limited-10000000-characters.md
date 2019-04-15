---
ms.openlocfilehash: 1f5bc43dcba15c28c179b23352558411f511c82f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235874"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>Развертывание сущностей DTD XmlTextReader не может превышать 10 000 000 символов

|   |   |
|---|---|
|Подробные сведения|Развертывание сущностей DTD теперь не может превышать 10 000 000 символов. Загрузка XML-файлов без развертывания сущностей DTD или с ограниченным развертыванием сущностей DTD не изменяется. Файлы с сущностями DTD, которые развертываются до более чем 10 000 000 символов, не загружаются и теперь вызывают исключение.|
|Предложение|Если ограничение развертывания сущностей DTD существенно ниже 10 000 000, значение может быть переопределено с помощью свойства <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>. <xref:System.Xml.XmlReaderSettings?displayProperty=name> с соответствующим значением <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=name> может передаваться в <code>XmlReader.Create</code>, который принимает <xref:System.Xml.XmlReaderSettings?displayProperty=name> (т. е. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)?displayProperty=nameWithType></li></ul>|
