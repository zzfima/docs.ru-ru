---
title: Свойство дочерней оси XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 862a9177d9e10e9561da389fdbffa3e35aa3b51a
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065938"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Свойство дочерней оси XML (Visual Basic)
Предоставляет доступ к потомкам из следующих: <xref:System.Xml.Linq.XElement> объекта, <xref:System.Xml.Linq.XDocument> объекта, коллекции <xref:System.Xml.Linq.XElement> объекты или коллекции <xref:System.Xml.Linq.XDocument> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательный. Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.  
  
 ...<  
 Обязательный. Обозначает начало свойства дочерней оси.  
  
 `descendant`  
 Обязательный. Имя узлов-потомков, чтобы открыть окно, в формате [`prefix:]name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный параметр. Префикс пространства имен XML для дочернего узла. Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции.|  
|`name`|Обязательный. Локальное имя узлов-потомков. См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Обязательный. Обозначает конец свойства дочерней оси.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Примечания  
 Свойство дочерней оси XML можно использовать для доступа к узлов-потомков по имени из <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта, или из коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объектов. Используйте код XML `Value` свойство для доступа к значению первого дочернего узла в возвращаемой коллекции. Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Компилятор Visual Basic преобразует свойства дочерней оси в вызовы <xref:System.Xml.Linq.XContainer.Descendants%2A> метод.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Имя в свойстве дочерней оси может использовать только пространства имен XML, объявленные глобально с помощью `Imports` инструкции. Он не может использовать пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить доступ к значению первого дочернего узла с именем `name` и значения всех узлов-потомков с именем `phone` из `contacts` объекта.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к значению первого дочернего узла с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
