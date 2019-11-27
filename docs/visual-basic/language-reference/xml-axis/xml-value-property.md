---
title: Свойство значения XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 571d9130ef69df580bbba5d90bc8758b4b627196
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349420"
---
# <a name="xml-value-property-visual-basic"></a>Свойство значения XML (Visual Basic)

Предоставляет доступ к значению первого элемента коллекции <xref:System.Xml.Linq.XElement> объектов.

## <a name="syntax"></a>Синтаксис

```vb
object.Value
```

## <a name="parts"></a>Части

|Термин|Определение|  
|---|---|  
|`object`|Обязательно. Коллекция объектов <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Возвращаемое значение

 `String`, содержащий значение первого элемента коллекции, или `Nothing`, если коллекция пуста.

## <a name="remarks"></a>Примечания

 Свойство <xref:System.Xml.Linq.XElement.Value%2A> упрощает доступ к значению первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement>. Это свойство сначала проверяет, содержит ли коллекция хотя бы один объект. Если коллекция пуста, это свойство возвращает `Nothing`. В противном случае это свойство возвращает значение свойства <xref:System.Xml.Linq.XElement.Value%2A> первого элемента в коллекции.

> [!NOTE]
> При доступе к значению атрибута XML с помощью идентификатора "\@" значение атрибута возвращается как `String` и не требуется явно указывать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.

 Для доступа к другим элементам в коллекции можно использовать свойство индексатора расширения XML. Дополнительные сведения см. в разделе [свойство индексатора расширения](extension-indexer-property.md).

## <a name="inheritance"></a>Наследование

 Большинству пользователей не придется реализовывать <xref:System.Collections.Generic.IEnumerable%601>, поэтому этот раздел можно игнорировать.

 Свойство <xref:System.Xml.Linq.XElement.Value%2A> является свойством расширения для типов, реализующих `IEnumerable(Of XElement)`. Привязка этого свойства расширения похожа на привязку методов расширения: Если тип реализует один из интерфейсов и определяет свойство с именем "value", это свойство имеет приоритет над свойством расширения. Иными словами, это <xref:System.Xml.Linq.XElement.Value%2A> свойство может быть переопределено путем определения нового свойства в классе, реализующем `IEnumerable(Of XElement)`.

## <a name="example"></a>Пример

 В следующем примере показано, как использовать свойство <xref:System.Xml.Linq.XElement.Value%2A> для доступа к первому узлу в коллекции объектов <xref:System.Xml.Linq.XElement>. В примере свойство дочерней оси используется для получения коллекции всех дочерних узлов с именем `phone`, которые находятся в объекте `contact`.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Этот пример кода отображает следующий текст:

 `Phone number: 206-555-0144`

## <a name="example"></a>Пример

 В следующем примере показано, как получить значение атрибута XML из коллекции объектов <xref:System.Xml.Linq.XAttribute>. В примере свойство оси атрибута используется для вывода значения атрибута `type` для всех элементов `phone`.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Этот пример кода отображает следующий текст:

 ```console
 home
 work
```

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Свойства оси XML](index.md)
- [XML-литералы](../xml-literals/index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md)
- [Свойство индексатора расширения](extension-indexer-property.md)
- [Свойство дочерней оси XML](xml-child-axis-property.md)
- [Свойство оси атрибута XML](xml-attribute-axis-property.md)
