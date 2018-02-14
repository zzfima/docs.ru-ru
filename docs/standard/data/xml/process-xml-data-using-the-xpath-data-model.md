---
title: "Обработка XML-данных с использованием модели данных XPath"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9992efa209773a6e9f74050183260346f7f1f0ed
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="process-xml-data-using-the-xpath-data-model"></a>Обработка XML-данных с использованием модели данных XPath
Пространство имен <xref:System.Xml?displayProperty=nameWithType> обеспечивает программное представление XML-документов, фрагментов, узлов и наборов узлов в памяти с использованием классов <xref:System.Xml.XmlDocument> и <xref:System.Xml.XPath.XPathDocument>.  
  
 Класс <xref:System.Xml.XPath.XPathDocument> обеспечивает быстрое и доступное только для чтения представление XML-документа в памяти с использованием модели данных XPath. Класс <xref:System.Xml.XmlDocument> обеспечивает изменяемое в памяти представление XML-документа, реализующего модель W3C DOM базового уровня 1 и базового уровня 2. Оба класса реализуют интерфейс <xref:System.Xml.XPath.IXPathNavigable> и возвращают объект <xref:System.Xml.XPath.XPathNavigator>, предназначенный для выборки, вычисления, навигации и в некоторых случаях изменения базовых XML-данных.  
  
 В следующих разделах описывается функциональность класса <xref:System.Xml.XPath.XPathNavigator>, основанная на возвратившем его классе.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Чтение XML-данных с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 Описывается, как создать объект класса <xref:System.Xml.XPath.XPathDocument> только для чтения, чтобы считать XML-документ, и как создать редактируемый объект класса <xref:System.Xml.XmlDocument>, чтобы считать и изменить XML-документ. В этом разделе также описывается, как возвратить объект <xref:System.Xml.XPath.XPathNavigator> из каждого класса для просмотра и изменения XML-документа.  
  
 [Выбор, вычисление и отбор XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для выбора узлов в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument> с помощью запроса XPath, проверки и анализа результатов выражения XPath и определения соответствия узла в XML-документе данному выражению XPath.  
  
 [Доступ к XML-данным с помощью класса XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для перемещения по узлам извлечения XML-данных и доступа к XML-данным со строгой типизацией в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.  
  
 [Изменение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для вставки, изменения и удаления узлов и значений из XML-документа, который содержится в объекте <xref:System.Xml.XmlDocument>.  
  
 [Проверка по схеме с помощью XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Описываются способы проверки XML-содержимого объекта <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [Обработка XML-данных с использованием модели DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
