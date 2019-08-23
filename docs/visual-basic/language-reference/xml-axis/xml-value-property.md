---
title: Свойство значения XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942982"
---
# <a name="xml-value-property-visual-basic"></a>Свойство значения XML (Visual Basic)
Предоставляет доступ к значению первого элемента коллекции <xref:System.Xml.Linq.XElement> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`object`|Обязательный. Коллекция объектов <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `String` типа, содержащее значение первого элемента коллекции или `Nothing` , если коллекция пуста.  
  
## <a name="remarks"></a>Примечания  
 Свойство позволяет легко получить доступ к значению первого элемента в <xref:System.Xml.Linq.XElement> коллекции объектов. <xref:System.Xml.Linq.XElement.Value%2A> Это свойство сначала проверяет, содержит ли коллекция хотя бы один объект. Если коллекция пуста, это свойство возвращает `Nothing`значение. В противном случае это свойство возвращает значение <xref:System.Xml.Linq.XElement.Value%2A> свойства первого элемента в коллекции.  
  
> [!NOTE]
> При доступе к значению атрибута XML с помощью идентификатора "\@" значение атрибута возвращается в `String` виде, и вам не <xref:System.Xml.Linq.XAttribute.Value%2A> нужно явно указывать свойство.  
  
 Для доступа к другим элементам в коллекции можно использовать свойство индексатора расширения XML. Дополнительные сведения см. в разделе [свойство индексатора расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Наследование  
 Большинству пользователей не придется реализовывать <xref:System.Collections.Generic.IEnumerable%601>, и поэтому этот раздел можно игнорировать.  
  
 Свойство является свойством расширения для типов, реализующих `IEnumerable(Of XElement)`. <xref:System.Xml.Linq.XElement.Value%2A> Привязка этого свойства расширения похожа на привязку методов расширения: Если тип реализует один из интерфейсов и определяет свойство с именем "value", это свойство имеет приоритет над свойством расширения. Иными словами, это <xref:System.Xml.Linq.XElement.Value%2A> свойство можно переопределить, определив новое свойство в классе, реализующем интерфейс. `IEnumerable(Of XElement)`  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать <xref:System.Xml.Linq.XElement.Value%2A> свойство для доступа к первому узлу в <xref:System.Xml.Linq.XElement> коллекции объектов. В примере свойство дочерней оси используется для получения коллекции всех дочерних узлов, наименованных `phone` `contact` в объекте.  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить значение атрибута XML из коллекции <xref:System.Xml.Linq.XAttribute> объектов. В примере свойство оси атрибута используется для вывода значения `type` атрибута для всех `phone` элементов.  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 Этот пример кода отображает следующий текст:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Свойство индексатора расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [Свойство дочерней оси XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство оси атрибута XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
