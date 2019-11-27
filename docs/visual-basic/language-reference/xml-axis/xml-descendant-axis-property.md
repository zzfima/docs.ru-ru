---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349451"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Свойство дочерней оси XML (Visual Basic)

Предоставляет доступ к потомкам следующего: объекта <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> объекта, коллекции <xref:System.Xml.Linq.XElement> объектов или коллекции объектов <xref:System.Xml.Linq.XDocument>.

## <a name="syntax"></a>Синтаксис

```vb
object...<descendant>
```

## <a name="parts"></a>Части

`object` Обязательный. Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.

`...<` Обязательный. Обозначает начало свойства дочерней оси.

`descendant` Обязательный. Имя дочернего узла, к которому осуществляется доступ, в форме [`prefix:]name`.

|Отделение|Описание|
|----------|-----------------|
|`prefix`|Необязательный элемент. Префикс пространства имен XML для узла-потомка. Должно быть глобальным пространством имен XML, которое определяется с помощью инструкции `Imports`.|
|`name`|Обязательно. Локальное имя дочернего узла. См. [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Обязательный. Обозначает конец свойства дочерней оси.

## <a name="return-value"></a>Возвращаемое значение

Коллекция объектов <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Примечания

Свойство дочерней оси XML можно использовать для доступа к узлам-потомкам по имени из <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта или из коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>. Используйте свойство XML `Value` для доступа к значению первого дочернего узла в возвращаемой коллекции. Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).

Компилятор Visual Basic преобразует свойства оси потомков в вызовы метода <xref:System.Xml.Linq.XContainer.Descendants%2A>.

## <a name="xml-namespaces"></a>Пространства имен XML

Имя в свойстве дочерней оси может использовать только пространства имен XML, объявленные глобально с помощью инструкции `Imports`. Нельзя использовать пространства имен XML, объявленные локально в литералах XML-элементов. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Пример

В следующем примере показано, как получить доступ к значению первого узла-потомка с именем `name` и значения всех узлов-потомков с именем `phone` из объекта `contacts`.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Этот пример кода отображает следующий текст:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Пример

В следующем примере `ns` объявляется как префикс пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и доступа к значению первого дочернего узла с полным именем `ns:name`.

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Этот пример кода отображает следующий текст:

`Name: Patrick Hines`

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
