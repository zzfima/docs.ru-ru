---
title: Общие сведения об модели объектов XML-схемы
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
ms.openlocfilehash: 3ebf0cd06ebea3092ef8aa42debe0afeac9be4f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129147"
---
# <a name="xml-schema-object-model-overview"></a>Общие сведения об модели объектов XML-схемы
Модель SOM в Microsoft .NET Framework является богатым по возможностям API, позволяющим создавать, изменять и проверять схемы программным путем. Модель SOM работает в документах схемы XML так же, как модель DOM работает в XML-документах. Документы схемы XML - это допустимые XML-файлы, которые после загрузки в память делают осмысленными утверждения о структуре и правильности других XML-документов, соответствующих этой схеме.  
  
 Схема представляет собой XML-документ, который определяет класс XML-документов, указывая структуру или модель XML-документа для конкретной схемы. В схеме определяются ограничения на содержимое XML-документов и описывается словарь (правила или грамматика), которому должны следовать совместимые с ней XML-документы, чтобы считаться допустимыми для этой конкретной схемы. Проверка XML-документа - это процесс, обеспечивающий соответствие документа заданной схемой грамматике.  
  
 Ниже представлены способы, с помощью которых API модели SOM в платформе .NET Framework позволяет создавать, изменять и проверять схемы.  
  
- Загрузка допустимых схем из файлов и сохранение их в файл.  
  
- Создание в памяти схем, использующих классы со строгой типизацией.  
  
- Взаимодействие с классом <xref:System.Xml.Schema.XmlSchemaSet> для кэширования, компиляции и получения схем.  
  
- Взаимодействие с методом <xref:System.Xml.XmlReader.Create%2A> класса <xref:System.Xml.XmlReader> для проверки соответствия экземпляров XML-документов схемам.  
  
- Построение редакторов для создания и обслуживания схем.  
  
- Динамическое изменение схемы, которую можно скомпилировать и сохранить для использования в проверке экземпляров XML-документов.  
  
## <a name="the-schema-object-model"></a>Модель SOM  
 Модель SOM состоит из широкого набора классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, соответствующих элементам схемы XML. Например, элемент `<xsd:schema>...</xsd:schema>` сопоставляется с классом <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType>, а все данные, содержащиеся в элементе `<xsd:schema/>`, можно представить с помощью класса <xref:System.Xml.Schema.XmlSchema>. Точно так же элементы `<xsd:element>...</xsd:element>` и `<xsd:attribute>...</xsd:attribute>` сопоставляются с классами <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> и <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> соответственно. Это сопоставление выполняется для всех элементов схемы XML, создающих модели XML SOM в пространстве имен <xref:System.Xml.Schema>, как показано на следующей схеме.  
  
 ![Объектная модель System.Xml.Schema](./media/xml-schema-object-model-overview/xml-schema-object-model.gif)  
  
 Дополнительные сведения о каждом классе в пространстве имен <xref:System.Xml.Schema> см. в справочной документации для пространства имен <xref:System.Xml.Schema> в библиотеке классов платформы .NET Framework.  
  
## <a name="see-also"></a>См. также

- [Чтение и запись XML-схем](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Построение XML-схем](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Обход XML-схем](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Изменение XML-схем](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Включение или импорт XML-схем](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Набор сведений для постсхемной компиляции](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
