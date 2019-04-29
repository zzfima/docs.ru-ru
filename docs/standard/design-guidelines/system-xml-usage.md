---
title: Использование System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fc94ac62d1f2413c5f51446a8f6d0a52d9151557
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650132"
---
# <a name="systemxml-usage"></a>Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, которая находится в <xref:System.Xml?displayProperty=nameWithType> пространства имен, который может использоваться для представления XML-данных.  
  
 **X DO NOT** использовать <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Предпочтительнее использовать экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, или подтипами <xref:System.Xml.Linq.XNode> вместо этого. `XmlNode` и `XmlDocument` не предназначены для предоставления общедоступных интерфейсов API.  
  
 **✓ DO** использовать `XmlReader`, `IXPathNavigable`, или подтип `XNode` как входной или выходной членов, которые принимают или возвращают XML-данные.  
  
 Используйте эти абстракции, а не `XmlDocument`, `XmlNode`, или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методов из конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальной источники XML-данных, которые предоставляют `XNode` , `XmlReader`, или <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** подкласс `XmlDocument` требуется создать тип, представляющий XML-представление базового источника данных или модели объекта.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
