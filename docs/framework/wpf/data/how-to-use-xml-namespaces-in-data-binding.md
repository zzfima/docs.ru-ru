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
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="8a5d6-102">Практическое руководство. Использование пространства имен XML при связывании данных</span><span class="sxs-lookup"><span data-stu-id="8a5d6-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="8a5d6-103">Пример</span><span class="sxs-lookup"><span data-stu-id="8a5d6-103">Example</span></span>
 <span data-ttu-id="8a5d6-104">В этом примере демонстрируется обработка пространств имен, указанных в источнике привязки [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a5d6-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>

 <span data-ttu-id="8a5d6-105">Если данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеют следующее определение пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a5d6-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="8a5d6-106">Можно использовать элемент <xref:System.Windows.Data.XmlNamespaceMapping>, чтобы связать пространство имен с <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8a5d6-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="8a5d6-107">Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для ссылки на пространство имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a5d6-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="8a5d6-108"><xref:System.Windows.Controls.ListBox> в этом примере отображает *Title* и *DC: Date* для каждого *элемента*.</span><span class="sxs-lookup"><span data-stu-id="8a5d6-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="8a5d6-109">Обратите внимание, что заданный <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> не обязательно должен совпадать с тем, который используется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Если префикс изменяется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], сопоставление по-прежнему работает.</span><span class="sxs-lookup"><span data-stu-id="8a5d6-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>

 <span data-ttu-id="8a5d6-110">В этом конкретном примере данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] поступают из веб-службы, но элемент <xref:System.Windows.Data.XmlNamespaceMapping> также работает со встроенными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] или [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данными во внедренном файле.</span><span class="sxs-lookup"><span data-stu-id="8a5d6-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a5d6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8a5d6-111">See also</span></span>

- [<span data-ttu-id="8a5d6-112">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="8a5d6-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="8a5d6-113">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="8a5d6-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8a5d6-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="8a5d6-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
