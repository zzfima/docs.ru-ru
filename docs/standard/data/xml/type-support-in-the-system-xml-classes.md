---
title: "Поддержка типов в классах System.Xml"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a>Поддержка типов в классах System.Xml
На платформе .NET Framework версии 2.0 основные классы XML были улучшены, чтобы включить возможности поддержки типов. Классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> включают функции поддержки типов, включая возможность преобразования между собой типов схемы XML и типов CLR.  
  
 На платформе .NET Framework версии 2.0 классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> были улучшены, чтобы включить функции поддержки типов.  
  
-   <xref:System.Xml.XmlReader> И <xref:System.Xml.XPath.XPathNavigator> каждого классам относятся **SchemaInfo** свойство, которое возвращает сведения о схеме на узле.  
  
-   **ReadContentAs** и **ReadElementContentAs** и методов для <xref:System.Xml.XmlReader> класс считывают текстовое значение и преобразовать его в значение CLR за один вызов метода.  
  
-   Метод <xref:System.Xml.XmlWriter.WriteValue%2A> класса <xref:System.Xml.XmlWriter> преобразует тип CLR в тип схемы XML при записи XML-документа.  
  
-   **ValueAs** и <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> свойства <xref:System.Xml.XPath.XPathNavigator> класс возвращает значение узла и преобразовать его в значение CLR за один вызов метода.  
  
> [!NOTE]
>  На платформе .NET Framework версии 1.0 класс <xref:System.Xml.XmlConvert> был нужен для взаимного преобразования типов схемы XML и типов CLR.  
  
## <a name="in-this-section"></a>Содержание  
 [Сопоставление типов данных XML с типами среды CLR](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 Описывает сопоставления типов данных XML и типов CLR по умолчанию.  
  
 [Примечания по реализации поддержки типов XML](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 Обсуждаются некоторые детали реализации поддержки типов.  
  
 [Преобразование типов данных XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 Описывает использование класса <xref:System.Xml.XmlConvert> для взаимного преобразования типов схемы XML и типов CLR.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Доступ к строго типизированным XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
