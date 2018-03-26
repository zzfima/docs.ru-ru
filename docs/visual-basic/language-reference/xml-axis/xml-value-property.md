---
title: Свойство значения XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9294c2d1d83dce3bca2abc22ee9c70296fc8014
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="xml-value-property-visual-basic"></a>Свойство значения XML (Visual Basic)
Предоставляет доступ к значению первого элемента из коллекции <xref:System.Xml.Linq.XElement> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`object`|Обязательно. Коллекция объектов <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект `String` , содержащий значение первого элемента коллекции, или `Nothing` Если возвращается пустая коллекция.  
  
## <a name="remarks"></a>Примечания  
 <xref:System.Xml.Linq.XElement.Value%2A> Свойство позволяет легко обращаться к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Это свойство сначала проверяет, содержит ли коллекция хотя бы один объект. Если коллекция пуста, это свойство возвращает `Nothing`. В противном случае это свойство возвращает значение <xref:System.Xml.Linq.XElement.Value%2A> свойства первого элемента в коллекции.  
  
> [!NOTE]
>  При доступе к значение атрибута XML с помощью "@", значение атрибута возвращается идентификатор как `String` и вам не нужно явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.  
  
 Чтобы получить доступ к другим элементам в коллекции, можно использовать свойство-индексатор расширения XML. Дополнительные сведения см. в разделе [свойство-индексатор расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## <a name="inheritance"></a>Наследование  
 Большинство пользователей не будет реализовать <xref:System.Collections.Generic.IEnumerable%601>и поэтому может игнорировать в этом разделе.  
  
 <xref:System.Xml.Linq.XElement.Value%2A> Свойство расширения для типов, реализующих `IEnumerable(Of XElement)`. Привязка этого расширенного свойства — как привязка методов расширения: Если тип реализует один из интерфейсов и определяет свойство с именем «Значение», это свойство имеет приоритет над свойством расширения. Другими словами, это <xref:System.Xml.Linq.XElement.Value%2A> свойство может быть переопределено, определив новое свойство в класс, реализующий `IEnumerable(Of XElement)`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать <xref:System.Xml.Linq.XElement.Value%2A> свойство для доступа к первым узлом в коллекцию <xref:System.Xml.Linq.XElement> объектов. В примере используется свойство дочерней оси для получения коллекции всех дочерних узлов с именем `phone` , находящихся в `contact` объекта.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как получить значение атрибута XML из коллекции <xref:System.Xml.Linq.XAttribute> объектов. В примере используется свойство оси атрибута для отображения значения `type` атрибутов для всех `phone` элементов.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Свойство индексатора расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [Свойство дочерней оси XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Свойство оси атрибута XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
