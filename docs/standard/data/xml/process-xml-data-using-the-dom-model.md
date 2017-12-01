---
title: "Обработка XML-данных с использованием модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 06c8b2e130dbecaca4c08684d030c8dcef1cd5a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="process-xml-data-using-the-dom-model"></a>Обработка XML-данных с использованием модели DOM
Модель DOM рассматривает XML-данные как стандартный набор объектов и используется для обработки XML-данных в памяти. Пространство имен `System.Xml` обеспечивает программное представление XML-документов, фрагментов, узлов и наборов узлов. Оно основывается на рекомендациях базовой модели DOM уровня 1 и модели DOM уровня 2 консорциума W3C.  
  
 Класс <xref:System.Xml.XmlDocument> представляет XML-документ. Он включает элементы для получения и создания всех других XML-объектов. С помощью класса <xref:System.Xml.XmlDocument> и связанных с ним классов можно конструировать XML-документы, загружать и обращаться к данным, изменять данные и сохранять изменения.  
  
## <a name="in-this-section"></a>Содержание  
  
-   [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
-   [Типы XML-узлов](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
-   [Иерархия объектной модели (DOM) XML документа](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
-   [Сопоставление объектной иерархии с XML-данными](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
-   [Создание XML-документа](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
-   [Считывание XML-документа в DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
-   [Вставка узлов в XML-документа](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
-   [Удаление узлов, содержимого и значений из XML-документа](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
-   [Изменение узлов, содержимого и значений в XML-документа](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
-   [Проверка XML-документа в DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
-   [Сохранение и запись документа](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
-   [Выбор узлов с помощью XPath-навигации](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
-   [Разрешение внешних ресурсов](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
-   [Сравнение объекта с помощью класса XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
-   [Коллекции узлов в NamedNodeMap и nodelist](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
-   [Динамические обновления объектов nodelist и NamedNodeMap](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
-   [Поддержка пространств имен в модели DOM](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
-   [Обработка событий в XML-документа с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
-   [Расширение модели DOM](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Описывает обработку XML с использованием класса <xref:System.Xml.XPath.XPathNavigator>.
