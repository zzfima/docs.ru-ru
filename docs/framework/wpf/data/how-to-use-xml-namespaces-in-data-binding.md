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
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="ed1fa-102">Практическое руководство. Использование пространства имен XML при связывании данных</span><span class="sxs-lookup"><span data-stu-id="ed1fa-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="ed1fa-103">Пример</span><span class="sxs-lookup"><span data-stu-id="ed1fa-103">Example</span></span>
 <span data-ttu-id="ed1fa-104">В этом примере показано, как управлять пространствами имен, указанными в источнике привязки XML.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="ed1fa-105">Если XML-данные имеют следующее определение пространства имен XML:</span><span class="sxs-lookup"><span data-stu-id="ed1fa-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="ed1fa-106">Можно использовать элемент <xref:System.Windows.Data.XmlNamespaceMapping>, чтобы связать пространство имен с <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="ed1fa-107">Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для ссылки на пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="ed1fa-108"><xref:System.Windows.Controls.ListBox> в этом примере отображает *Title* и *DC: Date* для каждого *элемента*.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="ed1fa-109">Обратите внимание, что заданный <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> не обязательно должен совпадать с тем, который использовался в источнике XML. Если префикс изменяется в источнике XML, сопоставление по-прежнему работает.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="ed1fa-110">В этом конкретном примере данные XML поступают из веб-службы, но элемент <xref:System.Windows.Data.XmlNamespaceMapping> также работает с встроенными XML-данными или XML в внедренном файле.</span><span class="sxs-lookup"><span data-stu-id="ed1fa-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed1fa-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ed1fa-111">See also</span></span>

- [<span data-ttu-id="ed1fa-112">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="ed1fa-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="ed1fa-113">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="ed1fa-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ed1fa-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ed1fa-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
