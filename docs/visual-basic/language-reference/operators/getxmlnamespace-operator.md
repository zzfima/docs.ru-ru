---
title: Оператор GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: e21cf160d10f308990894d1a85c4f5d05b90f68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Оператор GetXmlNamespace (Visual Basic)
Возвращает <xref:System.Xml.Linq.XNamespace> объекта, который соответствует указанным префиксом пространства имен XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательный. Строка, определяющая префикс пространства имен XML. Если указано, эта строка должна быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [имена из объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Если префикс не указан, возвращается пространство имен по умолчанию. Если пространство имен по умолчанию не задано, возвращается пустое пространство имен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XNamespace> Объект, соответствующий префикс пространства имен XML.  
  
## <a name="remarks"></a>Примечания  
 `GetXmlNamespace` Оператор возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий префикс пространства имен XML `xmlNamespacePrefix`.  
  
 Можно использовать префиксы пространства имен XML непосредственно в XML-литералы и свойства оси XML. Тем не менее, необходимо использовать `GetXmlNamespace` оператор преобразования префикс пространства имен для <xref:System.Xml.Linq.XNamespace> объекта перед его можно использовать в коде. После добавления имени неизвестного элемента для <xref:System.Xml.Linq.XNamespace> объекта для получения полного имени <xref:System.Xml.Linq.XName> объекта, который многие [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методы требуют.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется импорт `ns` как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом, который имеет полное имя `ns:phone`. Он затем передает этот дочерний узел для `ShowName` подпрограмму, которая создает полное имя с помощью `GetXmlNamespace` оператор. `ShowName` Подпрограммы полного имени, которое передает <xref:System.Xml.Linq.XNode.Ancestors%2A> метод нужно получить родительский `ns:contact` узла.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 При вызове `TestGetXmlNamespace.RunSample()`, он отображает окно сообщения, содержащее следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также  
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Доступ к XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
