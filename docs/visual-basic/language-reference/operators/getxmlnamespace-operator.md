---
title: "Оператор GetXmlNamespace (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetXmlNamespace"
  - "GetXmlNamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetXmlNamespace - ключевое слово"
  - "GetXmlNamespace - оператор"
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Оператор GetXmlNamespace (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Получает объект <xref:System.Xml.Linq.XNamespace>, соответствующий указанному префиксу пространства имен XML.  
  
## Синтаксис  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## Части  
 `xmlNamespacePrefix`  
 Необязательный.  Строка, определяющая префикс пространства имен XML.  Указанная строка должна быть допустимым идентификатором XML.  Дополнительные сведения см. в разделе [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  Если префикс не указан, то возвращается пространство имен по умолчанию.  Если не указано пространство имен по умолчанию, то возвращается пустое пространство имен.  
  
## Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XNamespace>, соответствующий указанному префиксу пространства имен XML.  
  
## Заметки  
 Оператор `GetXmlNamespace` получает объект <xref:System.Xml.Linq.XNamespace>, соответствующий указанному префиксу `xmlNamespacePrefix` пространства имен XML.  
  
 Можно использовать префиксы пространства имен XML непосредственно в XML\-литералах и свойствах XML оси.  Тем не менее необходимо использовать оператор `GetXmlNamespace` для преобразования префикса пространства имен к объекту <xref:System.Xml.Linq.XNamespace>, прежде чем можно будет использовать его в коде.  Можно добавить неполное имя элемента к объекту <xref:System.Xml.Linq.XNamespace> для получения полного объекта <xref:System.Xml.Linq.XName>, который требуется многим методам [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Пример  
 В следующем примере импортируется `ns` как префикс пространства имен XML.  Затем используется префикс пространства имен для создания литерала XML и доступа к первому дочернему узлу, имеющему полное имя `ns:phone`.  Он затем передает этот дочерний узел в подпрограмму `ShowName`, которая создает полное имя с помощью оператора `GetXmlNamespace`.  Подпрограмма `ShowName` затем передает полное имя в метод <xref:System.Xml.Linq.XNode.Ancestors%2A>, чтобы получить родительский узел `ns:contact`.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/getxmlnamespace-operator_1.vb)]  
  
 При вызове `TestGetXmlNamespace.RunSample()` отображается окно сообщения, содержащее следующий текст:  
  
 `Name: Patrick Hines`  
  
## См. также  
 [Оператор Imports \(пространство имен XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Доступ к XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)