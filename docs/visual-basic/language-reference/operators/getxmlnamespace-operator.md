---
title: "Оператор GetXmlNamespace (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
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
ms.openlocfilehash: 929ba4edae9e155245228670424a3898896da807
ms.lasthandoff: 03/13/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a>Оператор GetXmlNamespace (Visual Basic)
Возвращает <xref:System.Xml.Linq.XNamespace>объекта, который соответствует указанным префиксом пространства имен XML.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Части  
 `xmlNamespacePrefix`  
 Необязательный. Строка, определяющая префикс пространства имен XML. Если указано, эта строка должна быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Если префикс не указан, возвращается пространство имен по умолчанию. Если пространство имен по умолчанию не задано, возвращается пустое пространство имен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XNamespace>, Соответствующий префикс пространства имен XML.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="remarks"></a>Примечания  
 `GetXmlNamespace` Оператор возвращает <xref:System.Xml.Linq.XNamespace>, соответствующий префикс пространства имен XML `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace>  
  
 Можно использовать префиксы пространства имен XML непосредственно в XML-литералы и свойства оси XML. Тем не менее, необходимо использовать `GetXmlNamespace` оператор преобразования префикс пространства имен для <xref:System.Xml.Linq.XNamespace>объекта перед использованием в коде.</xref:System.Xml.Linq.XNamespace> После добавления имени неполное элемента для <xref:System.Xml.Linq.XNamespace>полное имя объекта <xref:System.Xml.Linq.XName>объекта, который многие [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] методы требуют.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется импорт `ns` как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом, который имеет полное имя `ns:phone`. Он затем передает этот дочерний узел для `ShowName` подпрограмму, которая создает полное имя с помощью `GetXmlNamespace` оператор. `ShowName` Подпрограммы передает проверенное имя <xref:System.Xml.Linq.XNode.Ancestors%2A>метод, чтобы получить родительский `ns:contact` узла.</xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
 [!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 При вызове метода `TestGetXmlNamespace.RunSample()`, отображается окно сообщения, содержащее следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также  
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Доступ к XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
