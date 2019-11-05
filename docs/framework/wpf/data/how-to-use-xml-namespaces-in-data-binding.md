---
title: Практическое руководство. Использование пространства имен XML при связывании данных
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460302"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Практическое руководство. Использование пространства имен XML при связывании данных
## <a name="example"></a>Пример
 В этом примере демонстрируется обработка пространств имен, указанных в источнике привязки [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].

 Если данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеют следующее определение пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Можно использовать элемент <xref:System.Windows.Data.XmlNamespaceMapping>, чтобы связать пространство имен с <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере. Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для ссылки на пространство имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. <xref:System.Windows.Controls.ListBox> в этом примере отображает *Title* и *DC: Date* для каждого *элемента*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Обратите внимание, что заданный <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> не обязательно должен совпадать с тем, который используется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Если префикс изменяется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], сопоставление по-прежнему работает.

 В этом конкретном примере данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] поступают из веб-службы, но элемент <xref:System.Windows.Data.XmlNamespaceMapping> также работает со встроенными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] или [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данными во внедренном файле.

## <a name="see-also"></a>См. также

- [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
