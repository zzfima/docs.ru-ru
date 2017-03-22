---
title: "Свойство дочерней оси XML (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 434dc90c643381bdc27b2da54a7418e39bf15e98
ms.lasthandoff: 03/13/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a>Свойство дочерней оси XML (Visual Basic)
Предоставляет доступ к потомкам из следующих: <xref:System.Xml.Linq.XElement>объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательный. <xref:System.Xml.Linq.XElement>Объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 ...<  
 Обязательный. Обозначает начало свойства оси-потомка.  
  
 `descendant`  
 Обязательный. Имя узлов-потомков для доступа, формы [`prefix``:`]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный. Префикс пространства имен XML для дочернего узла. Должно быть глобальное пространство имен XML, который определен с помощью `Imports` инструкции.|  
|`name`|Обязательный. Локальное имя узлов-потомков. В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Обязательный. Обозначает конец свойства дочерней оси.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>Примечания  
 Свойство дочерней оси XML можно использовать для доступа к узлов-потомков по имени из <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объект, или из коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Используйте XML `Value` свойства для доступа к значению первого дочернего узла в возвращаемой коллекции. Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует свойства оси-потомка в вызовы <xref:System.Xml.Linq.XContainer.Descendants%2A>метод.</xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Имя в свойстве дочерней оси может использовать только Пространства имен, объявленных глобально с `Imports` инструкции. Он не может использовать пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для доступа к значению первого дочернего узла с именем `name` и значения всех узлов-потомков с именем `phone` из `contacts` объекта.  
  
 [!code-vb[VbXMLSamples&#25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к значению первого дочернего узла с помощью полного имени `ns:name`.  
  
 [!code-vb[VbXMLSamples&#26;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
