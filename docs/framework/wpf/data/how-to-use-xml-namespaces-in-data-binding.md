---
title: "Практическое руководство. Использование пространства имен XML при связывании данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f23e041a1e6b283cfe5308d6aef861f1fc757a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="c22a5-102">Практическое руководство. Использование пространства имен XML при связывании данных</span><span class="sxs-lookup"><span data-stu-id="c22a5-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="c22a5-103">Пример</span><span class="sxs-lookup"><span data-stu-id="c22a5-103">Example</span></span>  
 <span data-ttu-id="c22a5-104">В этом примере демонстрируется обработка пространств имен, указанных в источнике привязки [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c22a5-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="c22a5-105">Если данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеют следующее определение пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c22a5-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="c22a5-106">Можно использовать <xref:System.Windows.Data.XmlNamespaceMapping> элемент, чтобы сопоставить пространство имен <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c22a5-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="c22a5-107">Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для обращения к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c22a5-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="c22a5-108"><xref:System.Windows.Controls.ListBox> В этом примере отображается *заголовок* и *dc:date* каждого *элемент*.</span><span class="sxs-lookup"><span data-stu-id="c22a5-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="c22a5-109">Обратите внимание, что <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> укажите не должен совпадать с используемым в [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] источника; Если префикс изменяется в [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] источника, то сопоставление по-прежнему работает.</span><span class="sxs-lookup"><span data-stu-id="c22a5-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="c22a5-110">В данном конкретном примере [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные поступают из веб-службы, но <xref:System.Windows.Data.XmlNamespaceMapping> элемент также работает со встроенными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] или [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных во внедренном файле.</span><span class="sxs-lookup"><span data-stu-id="c22a5-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22a5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c22a5-111">See Also</span></span>  
 [<span data-ttu-id="c22a5-112">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="c22a5-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="c22a5-113">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="c22a5-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="c22a5-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="c22a5-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
