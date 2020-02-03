---
title: Использование System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 2ecb709684834a8280c841eb8eef4f024481f7a4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743580"
---
# <a name="systemxml-usage"></a>Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, находящихся в <xref:System.Xml?displayProperty=nameWithType> пространствах имен, которые могут использоваться для представления XML-данных.

 ❌ не используют <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Используйте экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>или подтипы <xref:System.Xml.Linq.XNode>. `XmlNode` и `XmlDocument` не предназначены для предоставления общедоступных интерфейсов API.

 ✔️ использовать `XmlReader`, `IXPathNavigable`или подтипы `XNode` в качестве входных или выходных данных членов, принимающих или возвращающих XML.

 Используйте эти абстракции вместо `XmlDocument`, `XmlNode`или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методы от конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальными источниками данных XML, которые предоставляют `XNode`, `XmlReader`или <xref:System.Xml.XPath.XPathNavigator>.

 ❌ не под`XmlDocument`, если необходимо создать тип, представляющий представление XML базовой объектной модели или источника данных.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также раздел

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
