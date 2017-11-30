---
title: "Иерархия модели объектов (DOM) XML-документа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Иерархия модели объектов (DOM) XML-документа
Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.  
  
 ![Модель объектов XML-документов &#40; DOM &#41; Иерархия](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Иерархия объектной модели (DOM) XML-документа  
  
 Следующие классы не наследуют от **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 **XmlImplementation** класс используется для создания XML-документа. Дополнительные сведения см. в разделе [Создание XML-документа](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 **XmlNamedNodeMap** класс обрабатывает неупорядоченный набор узлов. Дополнительные сведения см. в разделе [получение неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 **XmlNodeList** класс обрабатывает неупорядоченный список узлов. Дополнительные сведения см. в разделе [получение упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 **XmlNodeChangedEventArgs** класс обрабатывает обработчики событий, зарегистрированных на **XmlDocument**. Дополнительные сведения см. в разделе [обработка событий в XML-документа с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 **XmlLinkedNode** класс наследует от **XmlNode**. Он предназначен для переопределения двух методов **XmlNode**: **PreviousSibling** и **NextSibling** методы. Эти переопределенные методы затем наследуются и используемые **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, и **XmlProcessingInstruction**, которые являются классы, которые имеют предыдущие и следующие одноуровневые элементы.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
