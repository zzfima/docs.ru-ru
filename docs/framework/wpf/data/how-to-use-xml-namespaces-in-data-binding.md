---
title: Практическое руководство. Использование пространства имен XML при связывании данных
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740573"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Практическое руководство. Использование пространства имен XML при связывании данных
## <a name="example"></a>Пример
 В этом примере показано, как управлять пространствами имен, указанными в источнике привязки XML.

 Если XML-данные имеют следующее определение пространства имен XML:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Можно использовать элемент <xref:System.Windows.Data.XmlNamespaceMapping>, чтобы связать пространство имен с <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере. Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для ссылки на пространство имен XML. <xref:System.Windows.Controls.ListBox> в этом примере отображает *Title* и *DC: Date* для каждого *элемента*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Обратите внимание, что заданный <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> не обязательно должен совпадать с тем, который использовался в источнике XML. Если префикс изменяется в источнике XML, сопоставление по-прежнему работает.

 В этом конкретном примере данные XML поступают из веб-службы, но элемент <xref:System.Windows.Data.XmlNamespaceMapping> также работает с встроенными XML-данными или XML в внедренном файле.

## <a name="see-also"></a>См. также

- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
