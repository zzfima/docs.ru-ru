---
title: "Использование System.Xml"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9bfa0f984f97e774d00a64fc3fd8489b3d5b40e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemxml-usage"></a>Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, хранящихся в <xref:System.Xml?displayProperty=nameWithType> пространства имен, который может использоваться для представления XML-данных.  
  
 **X не** использовать <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Предпочтительнее использовать экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, или подтип <xref:System.Xml.Linq.XNode> вместо него. `XmlNode`и `XmlDocument` не предназначены для предоставления в открытых интерфейсах API.  
  
 **СДЕЛАТЬ ✓** использовать `XmlReader`, `IXPathNavigable`, или подтип `XNode` как входной или выходной членов, которые принимают или возвращают XML-данные.  
  
 Используйте эти абстракции, а не `XmlDocument`, `XmlNode`, или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методов из определенных реализаций XML-документа в памяти и их можно работать с виртуальной источники XML-данных, которые предоставляют `XNode` , `XmlReader`, или <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X не** подкласс `XmlDocument` требуется создать тип, представляющий XML-представление базового источника данных или модели объекта.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Рекомендации по использованию](../../../docs/standard/design-guidelines/usage-guidelines.md)
