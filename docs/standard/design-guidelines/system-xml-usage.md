---
title: Использование System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709040"
---
# <a name="systemxml-usage"></a>Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, находящихся в <xref:System.Xml?displayProperty=nameWithType> пространствах имен, которые могут использоваться для представления XML-данных.  
  
 **X DO NOT** использовать <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Используйте экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>или подтипы <xref:System.Xml.Linq.XNode>. `XmlNode` и `XmlDocument` не предназначены для предоставления общедоступных интерфейсов API.  
  
 **✓ DO** использовать `XmlReader`, `IXPathNavigable`, или подтип `XNode` как входной или выходной членов, которые принимают или возвращают XML-данные.  
  
 Используйте эти абстракции вместо `XmlDocument`, `XmlNode`или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методы от конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальными источниками данных XML, которые предоставляют `XNode`, `XmlReader`или <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** подкласс `XmlDocument` требуется создать тип, представляющий XML-представление базового источника данных или модели объекта.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
