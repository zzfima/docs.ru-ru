---
title: "Соответствие узлов с помощью XPathNavigator | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Соответствие узлов с помощью XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> содержит метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> для проверки совпадения узла и выражения XPath.  Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> принимает в качестве входного аргумента выражение XPath и возвращает значение типа <xref:System.Boolean>, указывающее, совпадает ли текущий узел с заданным выражением XPath или скомпилированным объектом <xref:System.Xml.XPath.XPathExpression>.  
  
## Совпадение узлов  
 Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> возвращает значение `true`, если текущий узел совпадает с заданным выражением XPath.  Например, в следующем примере кода метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> вернет значение `true`, если текущим узлом является элемент `b`, содержащий атрибут `c`.  
  
> [!NOTE]
>  Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> не изменяет состояние объекта <xref:System.Xml.XPath.XPathNavigator>.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## См. также  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [Обработка XML\-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [Выборка XML\-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)   
 [Вычисление выражения XPath с помощью класса XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [Типы узлов, распознаваемые запросами XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)   
 [Запросы XPath и пространства имен](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [Скомпилированные выражения XPath](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)