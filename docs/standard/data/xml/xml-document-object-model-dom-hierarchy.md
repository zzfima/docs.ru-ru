---
title: "Иерархия модели объектов (DOM) XML-документа | Microsoft Docs"
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
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Иерархия модели объектов (DOM) XML-документа
Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.  
  
 ![Иерархия объектной модели &#40;DOM&#41; XML&#45;документа](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom\_class\_hierarchy")  
Иерархия объектной модели \(DOM\) XML\-документа  
  
 Следующие классы не наследуют от класса **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 Класс **XmlImplementation** используется для создания XML\-документа.  Дополнительные сведения см. в разделе [Создание XML\-документа](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Класс **XmlNamedNodeMap** обрабатывает неупорядоченный набор узлов.  Дополнительные сведения см. в разделе [Получение неупорядоченных узлов по имени и индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Класс **XmlNamedNodeMap** обрабатывает упорядоченный набор узлов.  Дополнительные сведения см. в разделе [Получение упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Класс **XmlNodeChangedEventArgs** работает с обработчиком события, зарегистрированного в объекте **XmlDocument**.  Дополнительные сведения см. в разделе [Обработка событий в XML\-документе с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Класс **XmlLinkedNode** наследует от класса **XmlNode**.  Предназначен для переопределения двух методов **XmlNode** \- **PreviousSibling** и **NextSibling**.  Эти переопределенные методы затем наследуются и используются классами **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** и **XmlProcessingInstruction**, которые имеют предыдущие и следующие одноуровневые элементы.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)