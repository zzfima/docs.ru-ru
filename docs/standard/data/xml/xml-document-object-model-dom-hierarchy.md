---
title: Иерархия модели объектов (DOM) XML-документа
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 1193d7631816fe9fbf7aa1984d79ef8e61d5da80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709976"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Иерархия модели объектов (DOM) XML-документа
Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.  
  
 ![Иерархия &#40;XML&#41; модель DOM DOM](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Иерархия объектной модели (DOM) XML-документа  
  
 Следующие классы не наследуют от класса **XmlNode**:  
  
- **XmlImplementation**  
  
- **XmlNamedNodeMap**  
  
- **XmlNodeList**  
  
- **XmlNodeChangedEventArgs**  
  
 Класс **XmlImplementation** используется для создания XML-документа. Дополнительные сведения см. в статье [Создание XML-документа](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Класс **XmlNamedNodeMap** обрабатывает неупорядоченный набор узлов. Дополнительные сведения см. в статье [Неупорядоченное извлечение узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Класс **XmlNamedNodeMap** обрабатывает упорядоченный набор узлов. Дополнительные сведения см. в статье [Упорядоченное извлечение узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Класс **XmlNodeChangedEventArgs** управляет обработчиками событий, которые зарегистрированы в объекте **XmlDocument**. Дополнительные сведения см. в статье [Обработка событий в XML-документе с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Класс **XmlLinkedNode** наследует от класса **XmlNode**. Он предназначен для того, чтобы переопределять два метода **XmlNode**, а именно: **PreviousSibling** и **NextSibling**. Эти переопределенные методы затем наследуются и используются классами **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** и **XmlProcessingInstruction**, для которых существуют предыдущие и следующие одноуровневые элементы.  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
