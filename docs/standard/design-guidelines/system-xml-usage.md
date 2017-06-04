---
title: "Использование System.Xml | Microsoft Docs"
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
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, размещенных в <xref:System.Xml?displayProperty=fullName> пространства имен, который может использоваться для представления XML\-данных.  
  
 **X не** используйте <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML\-данных. Предпочтительнее использовать экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, или подтипы <xref:System.Xml.Linq.XNode> вместо.`XmlNode` и `XmlDocument` не предназначены для предоставления общедоступных интерфейсов API.  
  
 **✓ сделать** использовать `XmlReader`, `IXPathNavigable`, или подтипы `XNode` как входной или выходной членов, которые принимают или возвращают XML.  
  
 Используйте эти абстракции, а не `XmlDocument`, `XmlNode`, или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методов из конкретных реализаций XML\-документа в памяти и позволяет им работать с виртуальной источники XML\-данных, которые предоставляют `XNode`, `XmlReader`, или <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X не** подкласс `XmlDocument` Если вы хотите создать тип, представляющий XML\-представление базового источника данных или модели объектов.  
  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)   
 [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)